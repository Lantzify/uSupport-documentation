---
layout: default
title: Extending
nav_order: 7
---

{: .note }
The documentation is still a work in progress. More details is coming soon.

# Extending

If you want something to happen when a ticket is created? Like send additional email. As of uSupport version **2.0.0** we've added Notifications

## Tickets

- **CreateTicketNotification** - Runs when a ticket is **created**
- **DeleteTicketNotification** - Runs when a ticket is **deleted**
- **UpdateTicketNotification** - Runs when a ticket is **updated**
- **UpdateTicketSendEmailNotification** - Runs when a ticket is **updated** and has sent email
- **UpdateTicketResolvedNotification** - Runs when a ticket get the status of 'resolved'


## Types
- **CreateTicketTypeNotification** - Runs when a type is **created**
- **DeleteTicketTypeNotification** - Runs when a type is **deleted**
- **DeleteTicketTypeNotification** - Runs when a type is **updated**

## Statuses
- **CreateTicketStatusNotification** - Runs when a status is **created**
- **DeleteTicketStatusNotification** - Runs when a status is **deleted**
- **UpdateTicketStatusNotification** - Runs when a status is **updated**

## Comments
- **AddTicketCommentNotification** - Runs when a **comment is added** to a ticket

# Usage
DoStuff.cs
```c#
using uSupport.Notifications;
using uSupport.Services.Interfaces;

    public class DoStuff : INotificationHandler<CreateTicketNotification>
    {
        private readonly IuSupportSettingsService _uSupportSettingsService;

        public DoStuff(IuSupportSettingsService uSupportSettingsService)
        {
            _uSupportSettingsService = uSupportSettingsService;
        }

        public void Handle(CreateTicketNotification notification)
        {
            //Do Stuff
            _uSupportSettingsService.SendEmail("toAdress", "subject", "templateViewPath", notification.Ticket);
        }
    }
```

MyComposer.cs
```c#
using uSupport.Notifications;

    public class MyComposer : IComposer
    {
        public void Compose(IUmbracoBuilder builder)
        {
            builder.AddNotificationHandler<CreateTicketNotification, DoStuff>();
        }
    }
```