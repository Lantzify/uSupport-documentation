---
layout: default
title: Settings
parent: Features
nav_order: 5
---

# Settings

## SendEmailOnTicketCreated
Controls if an email should be sent when a new ticket is created.
<br />
Default value: **true**

```
"SendEmailOnTicketCreated": bool
```

## TicketUpdateEmail
When a new ticket is created or when a comment is added to a ticket. Update emails will be sent to this adress. Can be a comma seperated list.
<br />
Default value: **None**
```
"SendEmailOnTicketCreated": string
```

## EmailSubjectNewTicket
Subject of the email when a new ticket is created.
<br />
Default value: **A new ticket has been created**
```
"EmailSubjectNewTicket": string
```

## EmailSubjectUpdateTicket
Subject of the email when a ticket is updated.
<br />
Default value: **Your ticket has been updated**
```
"EmailSubjectUpdateTicket": string
```

## EmailTemplateNewTicketPath
Path to the email template that will used when new ticket is created.
<br />
Default value: **/App_Plugins/uSupport/templates/NewTicketEmail.cshtml**
```
"EmailTemplateNewTicketPath": string
```

## EmailTemplateUpdateTicketPath
Path to the email template that will used when new ticket is updated.
<br />
Default value: **/App_Plugins/uSupport/templates/UpdateTicketEmail.cshtml**
```
"EmailTemplateUpdateTicketPath": string
```
       
## References
- [uSupportSettingsService](/uSupport-documentation/docs/references/services#usupportsettingsservice)
