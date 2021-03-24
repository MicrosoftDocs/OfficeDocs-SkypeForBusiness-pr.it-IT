---
title: Impostazione dei criteri client per la propria organizzazione
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '[] I criteri client aiutano a determinare le funzioni di Skype for Business online messe a disposizione degli utenti; per esempio, si potrebbe dare ad alcuni utenti il diritto di trasferire i file negando lo stesso diritto ad altri utenti.'
ms.openlocfilehash: 3706e6b4fafe15aa8b799170001af61b837968da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100532"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="bedd6-103">Impostazione dei criteri client per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="bedd6-103">Set up client policies for your organization</span></span>

<span data-ttu-id="bedd6-104">[] I criteri client aiutano a determinare le funzioni di Skype for Business online messe a disposizione degli utenti; per esempio, si potrebbe dare ad alcuni utenti il diritto di trasferire i file negando lo stesso diritto ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="bedd6-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="bedd6-105">Le impostazioni dei criteri client possono essere configurate al momento della creazione di un criterio oppure è possibile usare il cmdlet **Set-CsClientPolicy** per modificare le impostazioni di un criterio esistente.</span><span class="sxs-lookup"><span data-stu-id="bedd6-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="bedd6-106">Impostare i criteri client</span><span class="sxs-lookup"><span data-stu-id="bedd6-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="bedd6-107">Per tutte le impostazioni dei criteri client in Skype for Business online, è necessario usare Windows PowerShell e non è possibile usare **l'interfaccia** di amministrazione **di Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="bedd6-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="bedd6-108">Avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bedd6-108">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="bedd6-109">Skype for Business Online Connector fa attualmente parte dell'ultimo modulo di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="bedd6-109">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="bedd6-110">Se si usa l'ultima versione pubblica di Teams PowerShell, non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="bedd6-110">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="bedd6-111">Installare il [modulo di PowerShell di Teams.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="bedd6-111">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="bedd6-112">Aprire un Windows PowerShell comando ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bedd6-112">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="bedd6-113">Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi [di Microsoft 365 o Office 365 in](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) un'unica finestra di Windows PowerShell o Configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell .</span><span class="sxs-lookup"><span data-stu-id="bedd6-113">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="bedd6-114">Disabilitare le emoticon e le notifiche sulla presenza e impedire il salvataggio di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="bedd6-114">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="bedd6-115">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="bedd6-115">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="bedd6-116">Per altre informazioni, vedere il cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="bedd6-116">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="bedd6-117">Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="bedd6-117">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="bedd6-118">Per altre informazioni, vedere il cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="bedd6-118">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="bedd6-119">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) per applicare le impostazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="bedd6-119">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="bedd6-120">Abilitare URL o collegamenti ipertestuali perché siano cliccabili nei messaggi istantanei</span><span class="sxs-lookup"><span data-stu-id="bedd6-120">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="bedd6-121">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="bedd6-121">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="bedd6-122">Per altre informazioni, vedere il cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="bedd6-122">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="bedd6-123">Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="bedd6-123">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="bedd6-124">Per altre informazioni, vedere il cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="bedd6-124">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="bedd6-125">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) per applicare le impostazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="bedd6-125">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="bedd6-126">Impedire di mostrare i contatti recenti</span><span class="sxs-lookup"><span data-stu-id="bedd6-126">Prevent showing recent contacts</span></span>

- <span data-ttu-id="bedd6-127">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="bedd6-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="bedd6-128">Per altre informazioni, vedere il cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="bedd6-128">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="bedd6-129">Per assegnare il criterio creato ad Amos Marble, eseguire:</span><span class="sxs-lookup"><span data-stu-id="bedd6-129">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="bedd6-130">Per altre informazioni, vedere il cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="bedd6-130">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="bedd6-131">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) per applicare le impostazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="bedd6-131">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bedd6-132">Per saperne di più sulle Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bedd6-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="bedd6-133">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="bedd6-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bedd6-134">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business online con un unico punto di amministrazione che può semplificare il lavoro quotidiano, quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="bedd6-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="bedd6-135">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="bedd6-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bedd6-136">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bedd6-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="bedd6-137">Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="bedd6-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="bedd6-138">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="bedd6-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="bedd6-139">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="bedd6-139">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="bedd6-140">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="bedd6-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="bedd6-141">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="bedd6-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="bedd6-142">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="bedd6-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="bedd6-143">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bedd6-143">Related topics</span></span>
[<span data-ttu-id="bedd6-144">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="bedd6-144">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="bedd6-145">Bloccare i trasferimenti di file punto a punto</span><span class="sxs-lookup"><span data-stu-id="bedd6-145">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="bedd6-146">Configurare i criteri di conferenza nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="bedd6-146">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
