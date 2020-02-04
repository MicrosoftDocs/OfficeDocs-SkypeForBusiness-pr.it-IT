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
description: I criteri client aiutano a determinare le funzioni di Skype for Business online messe a disposizione degli utenti; per esempio, si potrebbe dare ad alcuni utenti il diritto di trasferire i file negando lo stesso diritto ad altri utenti.
ms.openlocfilehash: 0d92e9d4aab477cdcb010b4840d43a622f28b8cf
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693001"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="9fbf0-103">Impostazione dei criteri client per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="9fbf0-103">Set up client policies for your organization</span></span>

<span data-ttu-id="9fbf0-104">[] I criteri client aiutano a determinare le funzioni di Skype for Business online messe a disposizione degli utenti; per esempio, si potrebbe dare ad alcuni utenti il diritto di trasferire i file negando lo stesso diritto ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="9fbf0-105">Le impostazioni dei criteri client possono essere configurate al momento della creazione di un criterio oppure puoi usare il cmdlet **Set-CsClientPolicy** per modificare le impostazioni di un criterio esistente.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="9fbf0-106">Impostare i criteri client</span><span class="sxs-lookup"><span data-stu-id="9fbf0-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="9fbf0-107">Per tutte le impostazioni dei criteri client in Skype for business online, è necessario utilizzare Windows PowerShell e non è possibile **usare** l'interfaccia di **amministrazione di Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="9fbf0-108">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fbf0-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="9fbf0-109">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="9fbf0-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="9fbf0-110">A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9fbf0-111">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="9fbf0-p101">Se non si ha la versione 3,0 o successiva, è necessario scaricare e installare gli aggiornamenti in Windows PowerShell. Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0. Riavviare il computer quando viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="9fbf0-p102">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="9fbf0-118">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="9fbf0-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="9fbf0-119">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9fbf0-119">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="9fbf0-120">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9fbf0-121">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="9fbf0-121">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9fbf0-122">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="9fbf0-123">Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="9fbf0-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="9fbf0-124">Disabilitare emoticon e notifiche di presenza e impedire il salvataggio di messaggi istantanei</span><span class="sxs-lookup"><span data-stu-id="9fbf0-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="9fbf0-125">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="9fbf0-125">To create a new policy for these settings, run:</span></span>
    
> 
>   ```PowerShell
>   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
>   ```

  <span data-ttu-id="9fbf0-126">Per altre informazioni, vedere il cmdlet [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9fbf0-126">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="9fbf0-127">Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="9fbf0-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```PowerShell
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
>   ```

  <span data-ttu-id="9fbf0-128">Per altre informazioni, vedere il cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9fbf0-128">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="9fbf0-129">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) per applicare le impostazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="9fbf0-130">Abilitare URL o collegamenti ipertestuali perché siano cliccabili nei messaggi istantanei</span><span class="sxs-lookup"><span data-stu-id="9fbf0-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="9fbf0-131">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="9fbf0-131">To create a new policy for these settings, run:</span></span>
    
> 
>   ```PowerShell
>   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
>   ```

  <span data-ttu-id="9fbf0-132">Per altre informazioni, vedere il cmdlet [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9fbf0-132">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="9fbf0-133">Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="9fbf0-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```PowerShell
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
>   ```

  <span data-ttu-id="9fbf0-134">Per altre informazioni, vedere il cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9fbf0-134">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="9fbf0-135">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) per applicare le impostazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="9fbf0-136">Impedire di mostrare i contatti recenti</span><span class="sxs-lookup"><span data-stu-id="9fbf0-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="9fbf0-137">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="9fbf0-137">To create a new policy for these settings, run:</span></span>
  > 
  > ```PowerShell
  > New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  > ```

  <span data-ttu-id="9fbf0-138">Per altre informazioni, vedere il cmdlet [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9fbf0-138">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="9fbf0-139">Per assegnare il criterio creato ad Amos Marble, eseguire:</span><span class="sxs-lookup"><span data-stu-id="9fbf0-139">To grant the new policy you created to Amos Marble, run:</span></span>
  > 
  > ```PowerShell
  > Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  > ```

  <span data-ttu-id="9fbf0-140">Per altre informazioni, vedere il cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9fbf0-140">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="9fbf0-141">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) per applicare le impostazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9fbf0-142">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fbf0-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="9fbf0-143">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-143">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9fbf0-144">È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-144">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9fbf0-145">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="9fbf0-145">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9fbf0-146">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9fbf0-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="9fbf0-147">Sei motivi per cui potresti voler usare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="9fbf0-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="9fbf0-148">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9fbf0-148">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9fbf0-149">Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9fbf0-149">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="9fbf0-150">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="9fbf0-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="9fbf0-151">Usare Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="9fbf0-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9fbf0-152">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="9fbf0-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="9fbf0-153">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9fbf0-153">Related topics</span></span>
[<span data-ttu-id="9fbf0-154">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="9fbf0-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="9fbf0-155">Bloccare i trasferimenti di file Point-to-Point</span><span class="sxs-lookup"><span data-stu-id="9fbf0-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="9fbf0-156">Configurare i criteri di conferenza nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="9fbf0-156">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
