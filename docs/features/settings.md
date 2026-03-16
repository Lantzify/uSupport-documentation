---
layout: default
title: Settings
parent: Features
nav_order: 5
---

# Settings

For email delivery to work, Umbraco also needs working global SMTP configuration. The service specifically checks the configured SMTP `From` address before sending.

## SendEmailOnTicketCreated
Controls whether an email should be sent when a new ticket is created.
<br />
Default value: **true**

```
"SendEmailOnTicketCreated": bool
```

## SendEmailOnTicketComment
Controls whether an email should be sent when a new ticket comment is created.
<br />
Default value: **true**

```
"SendEmailOnTicketComment": bool
```

## TicketUpdateEmail
When a new ticket is created or a comment is added, update emails are sent to this address. You can provide a comma-separated list.
<br />
Default value: **None**
```
"TicketUpdateEmail": string
```

## EmailSubjectNewTicket
Subject line used for new ticket emails. You can add ticket properties by adding {} around the property name (e.g., `{ExternalTicketId}`, `{Title}`, `{Status.Name}`, `{Type.Name}`)
<br />
Default value: **A new ticket '{ExternalTicketId}' has been created**
```
"EmailSubjectNewTicket": string
```

## EmailSubjectUpdateTicket
Subject line used for ticket update emails. You can add ticket properties by adding {} around the property name (e.g., `{ExternalTicketId}`, `{Title}`, `{Status.Name}`, `{Type.Name}`)
<br />
Default value: **Ticket '{ExternalTicketId}' has been updated**
```
"EmailSubjectUpdateTicket": string
```

## EmailTemplateNewTicketPath
Path to the template used for new ticket emails.
<br />
Default value: **/App_Plugins/uSupport/templates/NewTicketEmail.cshtml**
```
"EmailTemplateNewTicketPath": string
```

## EmailTemplateUpdateTicketPath
Path to the template used for ticket update emails.
<br />
Default value: **/App_Plugins/uSupport/templates/UpdateTicketEmail.cshtml**
```
"EmailTemplateUpdateTicketPath": string
```

## Email behavior summary

The package uses these settings in three different flows:

* **Create ticket**: if `SendEmailOnTicketCreated` is `true`, an email is sent to `TicketUpdateEmail`
* **Add comment**: an update email is sent to `TicketUpdateEmail`
* **Save and send email** in the admin ticket editor: an update email is sent directly to the ticket author

## References
- [IuSupportSettingsService](/uSupport-documentation/docs/references/services#iusupportsettingsservice)
