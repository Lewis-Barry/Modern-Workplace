---
title: Terms of use
parent: Conditional Access
grand_parent: Identity 👨‍💼
has_children: false
nav_order: 1
---

## Azure AD Terms of use 📑

You may wish to present some formal information to users before they can access their online services. 

Azure AD Terms of Use is how you'd do that.

First prepare a PDF with the relevant company information, then head over to your Conditional Access blade which is where you'll find the Terms of Use configuration. 

> 💡 Each ToU must be tied to a Conditional Access policy

![Azure AD Terms of Use](Images/ToUconfig.png)

You may wish to have an explicit Conditional Access policy just for your terms of use. In which case, configure one with the following settings:

- All users and groups (except service accounts)
- All cloud apps
- Any Device
- Grant: All Users

For end users it looks like:

![ToU end-user](Images/ToUEnduser.png)

For more detail, check out the [Microsoft Docs ToU guide](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/terms-of-use)