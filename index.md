---
title: Home
layout: home
nav_order: 1
---

<img src="/uSupport-documentation/assets/usupport.svg" alt="logotype" style="height: 110px; margin: 0 auto; display: block;">

---

## What is uSupport
uSupport is a ticketing package for Umbraco that keeps support work inside the backoffice. Editors can create and follow tickets from the Content section, while support staff manage the full workflow from the dedicated `uSupport` section.

## Why uSupport
The package is built around a simple idea: keep the issue, its status, its comments, and its history in one place. Instead of chasing old emails, support teams can work from searchable ticket lists, and editors can track progress without leaving Umbraco.

## Key features

* Content dashboard for creating and following tickets
* Dedicated `uSupport` section for support staff
* Customizable ticket [types](/uSupport-documentation/docs/features/ticketType) and [statuses](/uSupport-documentation/docs/features/ticketStatus)
* Ticket [comments](/uSupport-documentation/docs/features/comment), internal notes, and history tracking
* Email notifications
* Searchable active and resolved ticket lists

## How to create a ticket

**Step 1**. Open the dashboard in the Content section and click **Create ticket**.
<img src="/uSupport-documentation/assets/createTicket/step1.png">

---

**Step 2**. Choose a [ticket type](/uSupport-documentation/docs/features/ticketType).
<img src="/uSupport-documentation/assets/createTicket/step2.png">

---

**Step 3**. If the selected ticket type includes an Umbraco property, such as the default `Page error` type, complete the extra field that appears. If not, continue to step 4.
<img src="/uSupport-documentation/assets/createTicket/step3.png">

---

**Step 4**. Enter the ticket details and create the ticket. uSupport generates an external ticket ID automatically.
<img src="/uSupport-documentation/assets/createTicket/step4.PNG">

---

**Step 5**. The ticket is created with the default [ticket status](/uSupport-documentation/docs/features/ticketStatus).

---

**Step 6**. If `TicketUpdateEmail` and your SMTP settings are configured, a notification email is sent to the address defined in that setting.
 <img src="/uSupport-documentation/assets/createTicket/step6.PNG">

---

**Step 7**. Support staff can now manage the ticket in the `uSupport` section, add comments, update the status, and optionally send update emails to the ticket author.
 <img src="/uSupport-documentation/assets/createTicket/step7.PNG">
