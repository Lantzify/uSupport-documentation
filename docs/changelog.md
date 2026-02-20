---
layout: default
title: Changelog
nav_order: 8
---

# Changelog

## 2.1.1

Added
{: .label .label-purple }
- Added [notifications event](/uSupport-documentation/docs/extending/) for "save and send email" ticket

Changes
{: .label .label-blue }
- Changed Tree access for `Ticket`, `Ticket type`, `Ticket status` and `Settings` from  `AuthorizationPolicies.TreeAccessDocumentTypes` to `uSupportSectionAccess`

---

## 2.1.0

Added
{: .label .label-purple }
- Added support for comma seperated list of emails for `TicketUpdateEmail` setting

Changes
{: .label .label-blue }
- Changed project structure to use RCL

Fixes
{: .label .label-green }
- Comments now displays correct "comment user" and not just ticket author

Removed
{: .label .label-red }
- Removed support for Umbraco 8, 10, 11 & 12

---

## 2.0.0

Added
{: .label .label-purple }
- Added support for  `Umbraco.MediaPicker3`
- Added [notifications event](/uSupport-documentation/docs/extending/)

Changes
{: .label .label-blue }
- Now the uSupport section gets added automatically

Fixes
{: .label .label-green }
- Fixed invalid build targets file with invalid command
- The full ticket now gets returned on Update ticket

---

## Release 1.2.0 - Database compatibility
SQLite compatibility has been added. Since uniqueidentifier isn't a thing in SQLite the queries has been adjusted.

Changes
{: .label .label-blue }
- Removed use of uniqueidentifier
- Added new item to the migration plan
- Removed CSS white text from .control-label 
- Changed IEmailSender to EmailSender for Umbraco v8

Fixes
{: .label .label-green }
- **Ticket statuses**
- Ticket statuses now redirects to overview path on delete
- Adjusted save object when creating a new status
- **Ticket types**
- Ticket type now loads if it doesn't have a property
- Correctly saves property description
- Adjusted save object when creating a new ticket type

---

## Release 1.1.0 - Umbraco v11 support 

Added
{: .label .label-purple }
- Added support for Umbraco v11

---

## Release 1.0.1 - Content apps added & fixes for ticket statuses
This release is a preparation for uSupport hub & node. We've added content apps to ticket, ticket status & type.

Fixes
{: .label .label-green }
- Ticket statuses now display correct behavior for the "default" property
- Ticket statuses no longer copies values after visiting a status.
