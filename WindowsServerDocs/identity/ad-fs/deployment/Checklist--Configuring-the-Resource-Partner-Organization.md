---
ms.assetid: 80d50a9f-428e-40fe-b6b3-9837fd9a3efc
title: Checklist: Configuring the Resource Partner Organization
description:
author: billmath
manager: femila
ms.date: 09/12/2016
ms.topic: article
ms.prod: windows-server-threshold
ms.service: active-directory
ms.technology: identity-adfs
ms.author: billmath
---

# Checklist: Configuring the Resource Partner Organization

>Applies To: Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

The resource partner organization contains the Web servers hosting the Web\-based applications that will be accessed by users in the account partner. Administrators in this organization must use the AD FS Management snap\-in to create claims provider trusts to represent their trust relationships with account partner organizations. In turn, the account partner administrator must create relying party trusts for each account partner organization that they want to trust.  
  
This checklist includes the tasks that are necessary for deploying Active Directory Federation Services \(AD FS\) in the resource partner organization. It also includes tasks for configuring the components that are required to establish one\-half of a federation partnership.  
  
If you are deploying a [Web SSO Design](https://technet.microsoft.com/library/dd807033.aspx), you do not have to follow this checklist. However, you do have to complete the tasks in this checklist to successfully deploy a [Federated Web SSO Design](https://technet.microsoft.com/library/dd807050.aspx).  
  
> [!IMPORTANT]  
> Make sure that the administrator of the account partner organization follows the guidance in [Checklist: Configuring the Account Partner Organization](Checklist--Configuring-the-Account-Partner-Organization.md) to ensure that all necessary deployment tasks will be completed to successfully create the second half of the federation partnership  
  
> [!NOTE]  
> Complete the tasks in this checklist in order. When a reference link takes you to a procedure, return to this topic after you complete the steps in that procedure so that you can proceed with the remaining tasks in this checklist.  
  
![](media/2b05dce3-938f-4168-9b8f-1f4398cbdb9b.gif)**Checklist: Configuring the resource partner organization**  
  
||Task|Reference|  
|-|--------|-------------|  
|![](media/icon_checkboxo.gif)|If you have an existing AD FS 1.0 or 1.1 deployment in your production environment today, see the link to the right for information about how to migrate settings from your current Federation Service to a new AD FS Federation Service. If you are deploying AD FS for the first time in your organization using AD FS, you can skip this step and continue to the next task in this checklist for information about how to set up a new resource partner organization.|![](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Planning a Migration to AD FS](https://technet.microsoft.com/library/ff678044.aspx)|  
|![](media/icon_checkboxo.gif)|Based on your deployment goals, review information about the components that are required to provide users with access to the federated applications.|![](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Provide Your Active Directory Users Access to Your Claims-Aware Applications and Services](https://technet.microsoft.com/library/dd807071.aspx)<br /><br />![](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Provide Your Active Directory Users Access to the Applications and Services of Other Organizations](https://technet.microsoft.com/library/dd807123.aspx)<br /><br />![](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Provide Users in Another Organization Access to Your Claims-Aware Applications and Services](https://technet.microsoft.com/library/dd807099.aspx)|  
|![](media/icon_checkboxo.gif)|Determine which AD FS design this resource partner organization will be associated with.|![](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Web SSO Design](https://technet.microsoft.com/library/dd807033.aspx)<br /><br />![](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Federated Web SSO Design](https://technet.microsoft.com/library/dd807050.aspx)|  
|![](media/icon_checkboxo.gif)|Review the different application types, and decide which application to deploy.|![](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Determine Your Federated Application Strategy in the Resource Partner](https://technet.microsoft.com/library/dd807077.aspx)|  
|![](media/icon_checkboxo.gif)|Before you begin deploying your AD FS servers, review the; 1.\) advantages and disadvantages of choosing either Windows Internal Database \(WID\) or SQL Server to store the AD FS configuration database 2.\) AD FS deployment topology types and their associated server placement and network layout recommendations.|![](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Determine Your AD FS Deployment Topology](https://technet.microsoft.com/library/gg982491.aspx)<br /><br />![](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[AD FS Deployment Topology Considerations](https://technet.microsoft.com/library/gg982489.aspx)|  
|![](media/icon_checkboxo.gif)|Review AD FS capacity planning guidance to determine the proper number of federation server and federation server proxy servers you should use in your production environment.|![](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Planning for AD FS Server Capacity](https://technet.microsoft.com/library/gg749899.aspx)|  
|![](media/icon_checkboxo.gif)|To effectively plan and implement the physical topology for the account partner deployment, determine whether your AD FS design requires one or more federation servers or federation server proxies.|![](media/bc6cea1a-1c6c-4124-8c8f-1df5adfe8c88.gif)[Checklist: Setting Up a Federation Server](Checklist--Setting-Up-a-Federation-Server.md)<br /><br />![](media/bc6cea1a-1c6c-4124-8c8f-1df5adfe8c88.gif)[Checklist: Setting Up a Federation Server Proxy](Checklist--Setting-Up-a-Federation-Server-Proxy.md)|  
|![](media/icon_checkboxo.gif)|Determine the type of attribute store that you want to add to AD FS. Then, add the attribute store using the AD FS Management snap\-in.|![](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[The Role of Attribute Stores](../../ad-fs/technical-reference/The-Role-of-Attribute-Stores.md)<br /><br />![](media/15dd35b6-6cc6-421f-93f8-7109920e7144.gif)[Add an Attribute Store](../../ad-fs/operations/Add-an-Attribute-Store.md)|  
|![](media/icon_checkboxo.gif)|If you will need to send claims to or consume claims from an account partner who is using either an AD FS 1.0 or 1.1 Federation Service, see the link to the right for information about how to configure AD FS to interoperate with previous versions of AD FS. If the account partner organization is also using AD FS to send or consume claims to your organization, you can skip this step and continue with the next task in this checklist.|![](media/faa393df-4856-4431-9eda-4f4e5be72a90.gif)[Planning for Interoperability with AD FS 1.x](https://technet.microsoft.com/library/ff678040.aspx)|  
|![](media/icon_checkboxo.gif)|After you deploy the first federation server in the resource partner organization, create a claims provider trust relationship by using the AD FS Management snap\-in. You can create a claims provider trust by entering data about an account partner manually or by using a federation metadata URL that the administrator of the account partner organization provides to you. You can use the federation metadata to retrieve the data for the resource partner automatically. **Note:** If the account partner publishes its federation metadata or can provide a file copy of it for you to use, we recommend that you retrieve the data automatically because it can save time.|![](media/15dd35b6-6cc6-421f-93f8-7109920e7144.gif)[Create a Relying Party Trust Manually](../../ad-fs/operations/Create-a-Relying-Party-Trust.md)<br /><br />![](media/15dd35b6-6cc6-421f-93f8-7109920e7144.gif)[Create a Relying Party Trust Using Federation Metadata](../../ad-fs/operations/Create-a-Relying-Party-Trust.md)|  
|![](media/icon_checkboxo.gif)|Depending on the needs of your organization, create one or more claim rule sets for each claims provider trust that is specified in the AD FS Management snap\-in so that incoming claims will be passed through, transformed, or mapped appropriately to corresponding claims in the resource partner.|![](media/bc6cea1a-1c6c-4124-8c8f-1df5adfe8c88.gif)[Checklist: Creating Claim Rules for a Claims Provider Trust](Checklist--Creating-Claim-Rules-for-a-Claims-Provider-Trust.md)|  
|![](media/icon_checkboxo.gif)|\(Optional\) A claim description may have to be created if one does not already exist that will fulfill the needs of your organization. AD FS includes a default set of claim descriptions that are exposed in the AD FS Management snap\-in.|![](media/15dd35b6-6cc6-421f-93f8-7109920e7144.gif)[Add a Claim Description](../../ad-fs/operations/Add-a-Claim-Description.md)|  