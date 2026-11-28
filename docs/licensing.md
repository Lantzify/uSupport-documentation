---
layout: default
title: uSupport Hub licensing
permalink: /docs/licensing/
nav_order: 12
---

# uSupport Hub licensing

A uSupport Hub license is a file tied to one domain. Upload it on the hub's **License** tab. Without a file, the hub runs as a Trial that connects 1 site.

## What a license covers

- **One domain**, with or without `www.`: a license for `example.com` also covers `www.example.com`, and the other way round. A subdomain is another domain: `example.com` doesn't cover `hub.example.com`.
- **`localhost` always passes**, so you can try a license on your own machine.
- **Sites**: a Trial connects 1 site. Every other license connects any number.
- **An expiry date, or none**. After the date, the hub is read-only until you upload a new license. A license that never expires shows **Never** on the **License** tab.

The domain is the one you open the hub's backoffice on.

## Buy or renew a license

{: .warning }
TODO: where to buy and renew a license. There's no purchase address yet.

Renew before the license expires: upload the new file and it replaces the old one straight away.

## Upload a license

1. Open **uSupport**, then the **License** tab.
2. Select **Upload license** and pick the license file (`.xml`).

The hub checks the file before saving it. If it's accepted, you see "License uploaded" and the tab shows the new license. It replaces the current one on every server running the hub.

Upload the file from the backoffice on the license's own domain. A license for `example.com` uploaded on another domain is turned down.

## When an upload is turned down

The current license stays, and a message says why:

- **isn't a uSupport Hub license file**: the file isn't genuine, isn't a license, or is for another product. Check that you picked the file you were sent, unchanged.
- **has expired**: the license's expiry date has passed. Renew it and upload the new file.
- **is for another domain**: the license is for a different domain than the backoffice you're on. Upload it from the backoffice on that domain.
- **is larger than 16 KB**: a license file is much smaller, so this is the wrong file.

If the message gives no reason, the upload itself failed. Try again.

## Trial

With no license file, the hub is a Trial. Everything works, for 1 site. To connect more, upload a license.

## Read-only

A license file that's expired, for another domain, or not genuine makes the hub read-only. It doesn't fall back to the Trial. The **License** tab shows the reason as the Status: **Expired**, **Wrong domain** or **Not genuine**.

While the hub is read-only:

- **Still works**: lists; reading tickets, comments and history; ticket types and statuses, connection checks, and editing or removing a site.
- **Turned off**: saving a ticket, commenting, adding a site, and adding, changing or removing ticket types and statuses.

Upload a valid license to turn these back on.
