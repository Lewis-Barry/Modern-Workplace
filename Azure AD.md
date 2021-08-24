---
title: Azure AD
parent: Identity 👨‍💼
has_children: false
nav_order: 1
---

## Azure Active Directory is not Active Directory

I bet you've heard that one before. It's one of those learning curves that is most off-putting for those used to on-prem _Active Directory Users and Computers._

Azure Active Directory is an **identity management and authentication platform.** It grants people access to things via their user account and group privileges. In our case it will be the lock on M365, but it can be used in conjunction with many other external apps and services.

_See [Microsoft Docs](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis) for more information._ 💡

### Azure AD does not manage computers

This is the confusing bit for newcomers. While Azure AD can list what device someone is using, it's doing so in the context of tracking how they accessed a resource. To manage a computer, we'd use Microsoft Intune (also part of M365 BP).

This terminology is slightly more modern than what you might be used to; Intune is an MDM (mobile device management) platform. This means that as long as an endpoint has an internet connection, it can be administered from M365.

For example, instead of a device having to look at an on-premises AD server to get the login information, it looks at your Azure AD tenant in the Microsoft Cloud. No more password desync or _"your domain isn't available"_ messages to worry about. 😉

### What does M365 BP unlock in Azure AD? 🔑

The short answer is: **Azure AD Premium P1**

The standout features available with Azure AD P1 include:

- Unlimited Directory Objects
- Conditional Access
- SharePoint access control
- MFA with additional auth methods (call + SMS alongside the app)
- MFA for on-premises stuff (we won't cover that on this site)
- Dynamic Groups and set expiration policies
- Banned password list
- Custom Terms of use