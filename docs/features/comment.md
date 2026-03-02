---
layout: default
title: Comment
parent: Features
nav_order: 4
---

# Comment
Comments make it possible to continue the conversation after a ticket has been created. They are useful for follow-up questions, clarifications, and adding new information without creating a separate ticket.

## Overview

Comments are stored against a specific ticket and returned in reverse chronological order, with the newest comment first.

When a comment is added:

* The ticket's `LastUpdatedBy` value is updated
* The ticket's `LastUpdated` timestamp is refreshed
* uSupport can send an update email to the address configured in [TicketUpdateEmail](/uSupport-documentation/docs/features/settings/#ticketupdateemail)

Comments are the public conversation attached to a ticket. Staff-only notes belong in the ticket's `InternalComment` field instead.

## Notifications
[Read more about notifications](/uSupport-documentation/docs/extending)

## References
- [Properties](/uSupport-documentation/docs/references/tables#usupportticketcomment)
- [IuSupportTicketCommentService](/uSupport-documentation/docs/references/services#iusupportticketcommentservice)
