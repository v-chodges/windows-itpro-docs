---
title: Document your app list (Windows)
description: This planning topic describes the app information that you should document when you create a list of apps for AppLocker policies.
ms.assetid: b155284b-f75d-4405-aecf-b74221622dc0
ms.reviewer: 
ms.author: dansimp
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 09/21/2017
ms.technology: windows-sec
---

# Document your app list

**Applies to**

- Windows 10
- Windows 11
- Windows Server 2016 and above

>[!NOTE]
>Some capabilities of Windows Defender Application Control are only available on specific Windows versions. Learn more about the [Windows Defender Application Control feature availability](/windows/security/threat-protection/windows-defender-application-control/feature-availability).

This planning topic describes the app information that you should document when you create a list of apps for AppLocker policies.

## Record your findings

**Apps**

Record the name of the app, whether it is signed as indicated by the publisher's name, and whether it is a mission critical, business productivity, optional, or personal app. Later, as you manage your rules, AppLocker displays this information in the format shown in the following example: *MICROSOFT OFFICE INFOPATH signed by O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US*.

**Installation path**

Record the installation path of the apps. For example, Microsoft Office 2016 installs files to *%programfiles%\\Microsoft Office\\Office16\\*, which is *C:\\Program Files\\Microsoft Office\\Office16\\* on most devices.

The following table provides an example of how to list applications for each business group at the early stage of designing your application control policies. Eventually, as more planning information is added to the list, the information can be used to build AppLocker rules.

|Business group|Organizational unit|Implement AppLocker?|Apps|Installation path|
|--- |--- |--- |--- |--- |
|Bank Tellers|Teller-East and Teller-West|Yes|Teller Software|C:\Program Files\Woodgrove\Teller.exe|
||||Windows files|C:\Windows|
|Human Resources|HR-All|Yes|Check Payout|C:\Program Files\Woodgrove\HR\Checkcut.exe|
||||Time Sheet Organizer|C:\Program Files\Woodgrove\HR\Timesheet.exe|
||||Internet Explorer 7|C:\Program Files\Internet Explorer</p>|
||||Windows files|C:\Windows|

>[!NOTE]
>AppLocker only supports publisher rules for Universal Windows apps. Therefore, collecting the installation path information for Universal Windows apps is not necessary.
 
<b>Event processing</b>

As you create your list of apps, you need to consider how to manage the events that are generated by user access, or you need to deny running those apps to make your users as productive as possible. The following list is an example of what to consider and what to record:

-   Will event forwarding be implemented for AppLocker events?
-   What is the location of the AppLocker event collection?
-   Should an event archival policy be implemented?
-   Will the events be analyzed and how often?
-   Should a security policy be in place for event collection?

**Policy maintenance**

As you create your list of apps, you need to consider how to manage and maintain the policies that you will eventually create. The following list is an example of what to consider and what to record:

-   How will rules be updated for emergency app access and permanent access?
-   How will apps be removed?
-   How many older versions of the same app will be maintained?
-   How will new apps be introduced?

## Next steps

After you have created the list of applications, the next step is to identify the rule collections, which will become the application control policies. This information can be added to the table under the following columns:

-   Use default rule or define new rule condition
-   Allow or deny
-   GPO name

To identify the rule collections, see the following topics:

-   [Select the types of rules to create](select-types-of-rules-to-create.md)
-   [Determine Group Policy structure and rule enforcement](determine-group-policy-structure-and-rule-enforcement.md)
