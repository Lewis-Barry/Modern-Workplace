---
title: Autopilot
parent: Devices
has_children: false
nav_order: 1
---

## Windows Autopilot ✈️

When the Windows 10 OOBE initiates on a PC, it does a check to see if it belongs to an M365 tenant Autopilot configuration profile. If it does, then pre-configured policies will take over that are set by a M365 administrator. If it doesn't, then the normal manual experience will kick in.

### What does Autopilot do, and why is it different to Azure AD Join?

Autopilot gives administrators the ability to control which devices can be a part of their endpoint management and what the out-of-box experience should look like for their end users. Autopilot can be totally self-deploying for Kiosks, or user-driven if it's an assigned device. Administrators can specify to skip certain steps to ease the OOBE for the end-user.

> 💡 For a high-security approach, you should prevent users from joining devices to Azure AD (From Azure AD Portal) go to: Users -> Devices -> Device Settings -> Users may join devices to Azure AD = None

A crucial setting in the Autopilot profile is defining the local account type of the user who registers with the device. You want to set this to Standard User. With Azure AD join, the first account becomes local admin - not suitable for a corporately owned device.

### How to assign a device to a tenant.

Some vendors are able to supply you with the Autopilot hash when you buy equipment from them, but if they don't, here's how you can get them from your devices.


**Manually from each device**

Run the following in an elevated PowerShell window

```
New-Item -Type Directory -Path "C:\HWID"
Set-Location -Path "C:\HWID"
Set-ExecutionPolicy -Scope Process -ExecutionPolicy RemoteSigned
Install-Script -Name Get-WindowsAutoPilotInfo
Get-WindowsAutoPilotInfo -OutputFile AutoPilotHWID.csv
```

If you have RMM software you could write something fancy to collect many at once.

📔 The generated CSV can then be uploaded into either the Partner Centre:

**Partner Portal -> CSP -> Customers -> Contoso -> Devices -> Add Devices**

💻 Or into Endpoint Manager:

**Devices -> Enroll -> Devices -> Import**

## Creating an Autopilot Profile

From [Endpoint Manager](https://endpoint.microsoft.com) go to Devices -> Enroll Devices -> Deployment Profiles -> Create

Here is an example of a configured profile that I've set to assign to all devices:

| Configuration                             | Option          |
|-------------------------------------------|-----------------|
| Name                                      | Win10_AP        |
| Convert all targeted devices to Autopilot | Yes             |
| Device Type                               | Windows PC      |
| Deployment Mode                           | User-Driven     |
| Join to Azure AD as                       | Azure AD Joined |
| Language                                  | English         |
| Automatically configure keyboard          | Yes             |
| Microsoft Software License Terms          | Hide            |
| Privacy Settings                          | Hide            |
| Hide change account options               | Hide            |
| User account type                         | Standard        |
| Allow White Glove OOBE                    | No              |
| Apply Device name template                | No              |

These are the initial settings, but you can also apply some verbose loading options too by going to Devices -> Enrollment Status Page.

You'll see a default policy there already which you can change to prevent the device being used until all specified apps are installed (Setting name: Show app and profile configuration progress).

If you want to go a step further, go to Azure AD -> Company Branding -> Configure. From here you can upload custom images and select colours that customise the sign in process across Azure services, including Autopilot registration.