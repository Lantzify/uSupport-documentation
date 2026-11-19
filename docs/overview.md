---
layout: default
title: Overview
nav_order: 2
---

# Overview

uSupport targets modern Umbraco installs and adds both an editor-facing ticket dashboard and a support-focused backoffice section.

## Requirements

| uSupport | Umbraco | .NET |
|:---------|:--------|:-----|
| 17.x | 17 | `net10.0` |
| 2.x | 13 | `net8.0` |

This documentation covers uSupport 17 for Umbraco 17. Sites still on Umbraco 13 should stay on uSupport 2.x.

### Upgrading from 2.x

On startup, uSupport 17 runs a migration that links existing ticket types to their data types by key. Tickets, types, statuses, comments, history, and settings are kept.

If you use custom email templates or call `SendEmail` from your own code, see the [17.0.0 changelog](/uSupport-documentation/docs/changelog#1700) for breaking changes.

## What gets installed

When the package starts, it registers:

* A `uSupport` section protected by section access, granted to the Administrators group automatically
* Menu items for **Tickets**, **Ticket types**, **Ticket statuses**, and **Settings**
* A dashboard in the Content section where editors can create and review tickets
* Database migrations for `uSupportTicket`, `uSupportTicketType`, `uSupportTicketStatus`, `uSupportTicketComment`, `uSupportTicketHistory`, and `uSupportSettings`

The initial migration also seeds default ticket types and statuses so the package is usable immediately after installation.

## Configuration

Settings are stored in the database and edited in the backoffice under **uSupport > Settings**. They are not read from `appsettings.json`. See [Settings](/uSupport-documentation/docs/features/settings) for every option.

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
uSupport follows semantic versioning ([semver.org](https://semver.org/)). Each release number indicates the expected scope of change so upgrades are easier to evaluate before you install them. From uSupport 17, the major version matches the supported Umbraco major.

| Major        | Minor        | Patch |
|:-------------|:------------------|:------|
| A release that includes breaking or incompatible changes. | A release that adds new features in a backward-compatible way. | A release that contains backward-compatible fixes and small improvements. |
