---
layout: default
title: Changelog
nav_order: 8
---

# Changelog

## 2.4.0
Added
{: .label .label-purple }
- Pagination for ticket history and comments [#54](https://github.com/Lantzify/uSupport/pull/54) 
- Send email now gets added to ticket history [#54](https://github.com/Lantzify/uSupport/pull/54) 
- Comment now gets added to ticket history [#54](https://github.com/Lantzify/uSupport/pull/54)  
- Added setting for sending mail on comment
- Notification for when email is sent. `EmailSendingNotification` [#54](https://github.com/Lantzify/uSupport/pull/54)

Changes
{: .label .label-blue }
- Replaced Appsettings with DB settings [#57](https://github.com/Lantzify/uSupport/pull/54)  
- Made whole table row clickable, changed overview fields [#50](https://github.com/Lantzify/uSupport/pull/54) 
- Replaced ticket summary from textarea to RTE 
- Updated default email styles
- LastUpdatedBy now gets assigned when ticket is created
- Added more null checks

Fixes
{: .label .label-green }
 - Changed to correct user for commenting instead of ticket author #44
- Fixed default template path not working [#54](https://github.com/Lantzify/uSupport/pull/54)  
- Fixed dirty check for comment textarea
- Fixed default sorting now sorts correctly

Removed
{: .label .label-red }
- Schema generator

---

## 2.3.0
Added
{: .label .label-purple }
- Added searching [#21](https://github.com/Lantzify/uSupport/issues/21)
- Disabled comment button if no text in it [#27](https://github.com/Lantzify/uSupport/issues/27)
- Added several links for Downloadable email templates [#24](https://github.com/Lantzify/uSupport/issues/24)
- Added ticket history [#22](https://github.com/Lantzify/uSupport/issues/22)
- Added migration to remove orphan ticket comments
- Added sorting to tickets [#28](https://github.com/Lantzify/uSupport/issues/28)
- Added Schema generator [#23](https://github.com/Lantzify/uSupport/issues/23)
- Added internal comment [#36](https://github.com/Lantzify/uSupport/issues/36)
- Added ability to use ticket values in subject [#40](https://github.com/Lantzify/uSupport/issues/40) 

Changes
{: .label .label-blue }
- Method `GetPagedResolvedTickets `  is now gets `totalItems `same as `GetPagedActiveTickets`
- Made Base method `Delete` virtual
- Moved `DeleteTicketNotification `into service
- On comment now uses Update email settings instead of new
- "Comment on ticket" now count as a update ticket
- Newest comments is now displayed first
- Adjusted sorting for `ResolvedTickets `and `ActiveTickets` [#32](https://github.com/Lantzify/uSupport/issues/32) 
- On comment, checks if EmailSetting exists before sending email
- Moved CreateTicketNotification and into Update service
- Moved `UpdateTicketNotification` and `TicketHistoryNotification` into Create service

Fixes
{: .label .label-green }
- Fixed delete all comments for ticket when ticket gets deleted [#29](https://github.com/Lantzify/uSupport/issues/29) 


Removed
{: .label .label-red }
- removed unwanted caching

---

## 2.2.0

Added
{: .label .label-purple }
- Added  [notification events](/uSupport-documentation/docs/extending/) for using Umbraco UI actions

Changes
{: .label .label-blue }
- Changed scoping to check if scope exists else create it.
- Changed service from AddScoped to AddTransient


Fixes
{: .label .label-green }
- Fixed GetTypeIdFromName to get correct type

---

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
- Added support for comma-separated lists of emails for the `TicketUpdateEmail` setting

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
