---
title: Azure AD
parent: Identity
has_children: false
nav_order: 1
---

## Azure Active Directory is not Active Directory

I bet you've heard that one before. It's one of those learning curves that is most off-putting for those used to on-prem _Active Directory Users and Computers._

Azure Active Directory is an **identity management and authentication platform.** It grants people access to things via their user account and group privileges. In our case it will be the lock on M365, but it can be used in conjunction with many other external apps and services.

_See [Microsoft Docs](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis) for more information._ 💡

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