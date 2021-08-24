---
title: Windows Hello
parent: Autopilot
grand_parent: Devices
has_children: false
nav_order: 1
---

## Windows Hello for Business 👋

To simplify the login experience for end users, you may wish to configure a Windows Hello profile. The Windows Hello authentication method is device specific, meaning a potential attacker would need physical access to your device as well as the PIN, your fingerprint, or face to access (some of those are less likely than others).

The idea behind this is that you can keep access to the device as easy as possible, while retaining a strong password to the actual Microsoft 365 account which you won't have to enter as often.

To configure from [Endpoint Manager](https://endpoint.microsoft.com) go to Devices -> Windows Enrollment -> Windows Hello for Business

As this is Windows Hello *for business* you have the option of enforcing TPM requirements, in the event that the device is tampered with, Hello access is automatically refused. ❗