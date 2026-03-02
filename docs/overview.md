---
layout: default
title: Overview
nav_order: 2
---

# Overview

uSupport targets modern Umbraco installs and adds both an editor-facing ticket dashboard and a support-focused backoffice section.

## Requirements

The current package targets `net8.0` and references Umbraco `13.0.3`. In practice, this documentation should be treated as documentation for the Umbraco 13 version of uSupport.

## What gets installed

When the package starts, it registers:

* A `uSupport` section protected by section access
* Trees for **Tickets**, **Ticket types**, **Ticket statuses**, and **Settings**
* A dashboard in the Content section where editors can create and review tickets
* Database migrations for `uSupportTicket`, `uSupportTicketType`, `uSupportTicketStatus`, `uSupportTicketComment`, and `uSupportTicketHistory`

The initial migration also seeds default ticket types and statuses so the package is usable immediately after installation.

## Configuration

uSupport binds its settings from `uSupport:Settings:Tickets` in `appsettings.json`.

```json
{
  "uSupport": {
    "Settings": {
      "Tickets": {
        "SendEmailOnTicketCreated": true,
        "TicketUpdateEmail": "support@example.com",
        "EmailSubjectNewTicket": "A new ticket '{ExternalTicketId}' has been created",
        "EmailSubjectUpdateTicket": "Ticket '{ExternalTicketId}' has been updated",
        "EmailTemplateNewTicketPath": "/App_Plugins/uSupport/templates/NewTicketEmail.cshtml",
        "EmailTemplateUpdateTicketPath": "/App_Plugins/uSupport/templates/UpdateTicketEmail.cshtml"
      }
    }
  }
}
```

## Default data

Default ticket types:

* Page error
* System error
* General question

Default ticket statuses:

* New
* In progress
* Answered
* Resolved

## Versioning
uSupport follows semantic versioning ([semver.org](https://semver.org/)). Each release number indicates the expected scope of change so upgrades are easier to evaluate before you install them.

| Major        | Minor        | Patch |
|:-------------|:------------------|:------|
| A release that includes breaking or incompatible changes. | A release that adds new features in a backward-compatible way. | A release that contains backward-compatible fixes and small improvements. |
