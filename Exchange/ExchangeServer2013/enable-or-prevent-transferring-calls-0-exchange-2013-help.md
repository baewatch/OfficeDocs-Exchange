---
title: 'Enable or prevent transferring calls from an auto attendant: Exchange 2013 Help'
TOCTitle: Enable or prevent transferring calls from an auto attendant
ms.author: serdars
author: msdmaguire
manager: serdars
ms.reviewer:
ms.assetid: ca961cc8-cc24-4e05-b72d-79979c155cf9
f1.keywords:
- NOCSH
mtps_version: v=EXCHG.150
---

# Enable or prevent transferring calls from an auto attendant in Exchange Server

_**Applies to:** Exchange Server 2013, Exchange Server 2016_

You can enable callers to transfer calls to users through an auto attendant, or prevent them from doing so. By default this option is enabled, and lets callers transfer calls to UM-enabled users in the Unified Messaging (UM) dial plan that's associated with the UM auto attendant.

For additional management tasks related to UM auto attendants, see [UM auto attendant procedures](um-auto-attendant-procedures-exchange-2013-help.md).

## What do you need to know before you begin?

- Estimated time to complete: Less than 1 minute.

- You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "UM auto attendants" entry in the [Unified Messaging permissions](unified-messaging-permissions-exchange-2013-help.md) topic.

- Before you perform these procedures, confirm that a UM dial plan has been created. For detailed steps, see [Create a UM dial plan](create-um-dial-plan-exchange-2013-help.md).

- Before you perform these procedures, confirm that a UM auto attendant has been created. For detailed steps, see [Create a UM auto attendant](create-a-um-auto-attendant-exchange-2013-help.md).

- For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange 2013](keyboard-shortcuts-in-the-exchange-admin-center-2013-help.md).

> [!TIP]
> Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://social.technet.microsoft.com/forums/office/home?category=exchangeserver).

## Use the EAC to enable or prevent call transfers to users from a UM auto attendant

1. In the EAC, navigate to **Unified Messaging** \> **UM dial plans**. In the list view, select the UM dial plan you want to change, and then click **Edit** ![Edit icon](images/ITPro_EAC_EditIcon.gif).

2. On the **UM Dial Plan** page, under **UM Auto Attendants**, select the UM auto attendant for which you want to configure call transfer, and then click **Edit** ![Edit icon](images/ITPro_EAC_EditIcon.gif).

3. On the **UM Auto Attendant** page \> **Address book and operator access**, under **Options for contacting users**, select the check box next to **Allow callers to dial users** to enable calls to be transferred. To prevent call transfers, clear the check box.

4. Click **Save**.

> [!NOTE]
> If you clear this check box and also clear the **Allow callers to leave voice messages for users** check box, the **Options for searching the address book** are disabled.

## Use the Shell to enable or prevent call transfers to users from a UM auto attendant

This example prevents call transfers on a UM auto attendant named `MyUMAutoAttendant`.

```powershell
Set-UMAutoAttendant -Identity MyUMAutoAttendant -AllowDialPlanSubscribers $false
```

This example enables call transfers on a UM auto attendant named `MyUMAutoAttendant`.

```powershell
Set-UMAutoAttendant -Identity MyUMAutoAttendant -AllowDialPlanSubscribers $true
```
