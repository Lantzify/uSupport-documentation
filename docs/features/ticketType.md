---
layout: default
title: Ticket type
parent: Features
nav_order: 2
---

{: .note }
The documentation is still a work in progress. More details is coming soon.

# Ticket types
Ticket types are used to better categorzie tickets.

## Overview
Ticket types can eaither just be regular type. Or it can contain Umbraco property.

### Default types
- System error
- Page error
- General question

### Umbraco property
You can add a Umbraco data type to a ticket type if you want the user to provide more structured data. Like eg "Page error" instead of making the user explain what page their having trouble with. They can just pick it with a content picker.

{: .warning }
>  Unsupported data types:
> - Umbraco.MultiNodeTreePicker
> - Umbraco.MemberGroupPicker
> - Umbraco.NestedContent
> - Umbraco.MemberPicker
> - Umbraco.UserPicker
> - Umbraco.BlockList
> - Umbraco.ListView
> - Umbraco.Label
> - Umbraco.Grid

## Notifications
[Read more about notifications](/uSupport-documentation/docs/extend.html#extend)

## References
- [Properties](//uSupport-documentationdocs/references/tables.html#usupporttickettype)
- [uSupportTicketTypeService](/uSupport-documentation/docs/references/services.html#usupporttickettypeservice)

## Screenshots

<img src="/uSupport-documentation/assets/ticketTypes.PNG">
