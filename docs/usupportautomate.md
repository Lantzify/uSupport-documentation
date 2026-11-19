---
layout: default
title: uSupport Automate
nav_order: 10
---

# uSupport Automate

uSupport Automate connects uSupport to [Umbraco Automate](https://github.com/umbraco/Umbraco.Automate). It adds uSupport triggers and actions to Automate, so you can build automations around your tickets in the backoffice without writing code.

For example, you can:

* Reply to every new ticket with a "Thanks, we're on it" comment
* Post to Slack when a ticket is resolved
* Open a ticket when a monitoring tool calls a webhook
* Email the author for feedback once their ticket is resolved

## Triggers

| Trigger | Fires when |
|:--------|:-----------|
| Ticket Created | A ticket is created |
| Ticket Updated | A ticket is saved, including when a comment is added to it |
| Ticket Status Changed | A ticket moves to another status |
| Ticket Resolved | An open ticket moves to a resolved status |
| Ticket Comment Added | A comment is added to a ticket |
| Ticket Deleted | A ticket is deleted |

Every trigger passes the ticket on to later steps: its ID and ticket number (e.g. `ABC-DEFG-123`), title, summary, type, status, whether it's resolved, the author's name and email, and its dates.

* **Ticket Status Changed** and **Ticket Resolved** also pass the previous status.
* **Ticket Comment Added** also passes the comment and who wrote it.

## Actions

| Action | What it does |
|:-------|:-------------|
| Create Ticket | Creates a ticket from a title, summary and [ticket type](/uSupport-documentation/docs/features/ticketType). It gets the default [status](/uSupport-documentation/docs/features/ticketStatus). |
| Add Ticket Comment | Adds a [comment](/uSupport-documentation/docs/features/comment) to a ticket |
| Change Ticket Status | Moves a ticket to another status, e.g. Resolved |
| Get Ticket | Loads a ticket so later steps can use its fields |

Changes made by an automation show up in the ticket history like any other change.

Useful links:

* [Umbraco Marketplace](https://marketplace.umbraco.com/package/usupport.automate)
* [GitHub repository](https://github.com/Lantzify/uSupport-Automate)
