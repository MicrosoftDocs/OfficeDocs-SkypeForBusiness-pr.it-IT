---
title: Creare amministratori del pannello di controllo di Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: "Per concedere l'accesso a Skype for Business Server, eseguire le operazioni seguenti:"
ms.openlocfilehash: cb1449aa4fcca534e01b4d8a47a7ac9c39cd64c7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824966"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="e4adf-103">Creare amministratori del pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e4adf-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="e4adf-104">Per concedere l'accesso a Skype for Business Server, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4adf-104">To grant access to the Skype for Business Server, do the following:</span></span>
  
1. <span data-ttu-id="e4adf-105">Eseguire l'accesso come membri del gruppo Domain Admins o del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e4adf-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="e4adf-106">Aprire **Utenti e computer di Active Directory**, espandere il proprio dominio, fare clic con il pulsante destro del mouse sul contenitore degli \*\*\*\* utenti e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e4adf-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="e4adf-107">Nelle \*\*\*\* proprietà di CSAdministrators fare clic sulla scheda **Membri**.</span><span class="sxs-lookup"><span data-stu-id="e4adf-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="e4adf-p101">Nella scheda Membri fare clic su **Aggiungi**. In **Seleziona utenti, contatti, computer, account di servizio o gruppi** individuare **Immettere i nomi degli oggetti da selezionare**. Digitare i nomi degli utenti o dei gruppi da aggiungere al gruppo CSAdministrators. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4adf-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="e4adf-p102">Nella scheda Membri verificare che siano presenti gli utenti o i gruppi selezionati. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4adf-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="e4adf-114">Il pannello di controllo di Skype for Business Server è uno strumento di controllo di accesso basato sui ruoli.</span><span class="sxs-lookup"><span data-stu-id="e4adf-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="e4adf-115">L'appartenenza al gruppo CsAdministrator fornisce a un utente che utilizza il controllo completo del pannello di controllo di Skype for Business Server per tutte le funzioni di configurazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="e4adf-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="e4adf-116">Vi sono inoltre altri ruoli per funzioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="e4adf-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="e4adf-117">Gli utenti non devono essere abilitati per Skype for Business Server per essere resi membri dei gruppi di gestione.</span><span class="sxs-lookup"><span data-stu-id="e4adf-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="e4adf-118">Altri ruoli includono:</span><span class="sxs-lookup"><span data-stu-id="e4adf-118">Other roles include:</span></span>
  
- <span data-ttu-id="e4adf-119">**CsArchiving:** I membri di questo gruppo possono eseguire tutte le funzioni di archiviazione, ad esempio la configurazione e la gestione del ruolo del server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e4adf-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="e4adf-p104">**CsHelpDesk:** i membri di questo gruppo possono visualizzare la configurazione e la distribuzione, inclusi i criteri e le proprietà degli utenti. Tali membri possono inoltre eseguire attività di risoluzione dei problemi specifiche.</span><span class="sxs-lookup"><span data-stu-id="e4adf-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="e4adf-p105">**CsLocationAdministrator:** i membri di questo gruppo dispongono dei diritti utente minimi associati alla gestione del servizio per le chiamate di emergenza. Possono creare posizioni e identificatori di rete per tale servizio e associarli nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e4adf-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="e4adf-124">**CsResponseGroupAdministrator:** i membri di questo gruppo possono gestire e configurare il servizio Response Group.</span><span class="sxs-lookup"><span data-stu-id="e4adf-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="e4adf-125">**CsServerAdministrator:** I membri possono gestire, monitorare e risolvere i problemi relativi a tutti i server che eseguono Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e4adf-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="e4adf-126">**CsUserAdministrator:** i membri di questo gruppo possono gestire, abilitare e disabilitare gli utenti e assegnare criteri esistenti agli utenti.</span><span class="sxs-lookup"><span data-stu-id="e4adf-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="e4adf-127">**CsViewOnlyAdministrator:** I membri possono visualizzare la distribuzione e la configurazione delle informazioni sul server.</span><span class="sxs-lookup"><span data-stu-id="e4adf-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="e4adf-128">Questa appartenenza consente a un membro di monitorare l'integrità dei server che eseguono Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e4adf-128">This membership enables a member to monitor the health of the servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="e4adf-129">**CsVoiceAdministrator:** I membri possono creare, configurare e gestire le impostazioni vocali in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e4adf-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="e4adf-130">Per mantenere la sicurezza e l'integrità del controllo di accesso basato sui ruoli, aggiungere gli utenti ai gruppi che definiscono il ruolo eseguito dall'utente nella gestione della distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e4adf-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

