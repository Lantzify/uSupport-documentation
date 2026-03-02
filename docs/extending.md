---
layout: default
title: Extending
nav_order: 7
---

# Extending

uSupport publishes Umbraco notifications when tickets, types, statuses, and comments change. This is the main extension point for adding custom behavior such as extra emails, external integrations, or audit hooks.

## Tickets

* **CreateTicketNotification**: published when a ticket is created
* **DeleteTicketNotification**: published when a ticket is deleted
* **UpdateTicketNotification**: published when a ticket is updated
* **UpdateTicketSendEmailNotification**: published when a ticket update also sends an email
* **UpdateTicketResolvedNotification**: published when a ticket is moved to a non-active status
* **TicketHistoryNotification**: published during ticket create and update flows and used by the built-in history handler

## Ticket types

* **CreateTicketTypeNotification**: published when a type is created
* **DeleteTicketTypeNotification**: published when a type is deleted
* **UpdateTicketTypeNotification**: published when a type is updated

## Ticket statuses

* **CreateTicketStatusNotification**: published when a status is created
* **DeleteTicketStatusNotification**: published when a status is deleted
* **UpdateTicketStatusNotification**: published when a status is updated

## Comments

* **AddTicketCommentNotification**: published when a comment is added to a ticket

## Built-in history handling

uSupport registers a handler for `TicketHistoryNotification`. That handler creates history entries with action types such as `Created`, `Updated`, and `Resolved`, based on changes to:

* Ticket type
* Ticket status
* Internal comment

## Usage

`DoStuff.cs`

```c#
using uSupport.Notifications;
using uSupport.Services.Interfaces;
using Umbraco.Cms.Core.Events;

public class DoStuff : INotificationHandler<CreateTicketNotification>
{
    private readonly IuSupportSettingsService _uSupportSettingsService;

    public DoStuff(IuSupportSettingsService uSupportSettingsService)
    {
        _uSupportSettingsService = uSupportSettingsService;
    }

    public void Handle(CreateTicketNotification notification)
    {
        _uSupportSettingsService.SendEmail(
            "support@example.com",
            "Ticket received",
            "/App_Plugins/uSupport/templates/NewTicketEmail.cshtml",
            notification.Ticket);
    }
}
```

`MyComposer.cs`

```c#
using uSupport.Notifications;
using Umbraco.Cms.Core.Composing;
using Umbraco.Cms.Core.DependencyInjection;
using Umbraco.Cms.Core.Events;

public class MyComposer : IComposer
{
    public void Compose(IUmbracoBuilder builder)
    {
        builder.AddNotificationHandler<CreateTicketNotification, DoStuff>();
    }
}
```
