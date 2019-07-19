---
title: Impostazione dei criteri di conferenza per la propria organizzazione
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Le conferenze sono una parte importante di Skype for Business online: le conferenze consentono a gruppi di utenti di incontrarsi online per visualizzare diapositive e video, condividere applicazioni, scambiare file e comunicare e collaborare in altro modo.'
ms.openlocfilehash: d20b1a39f83a875d255a812fd86160445691ae2f
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792476"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="c27a3-103">Impostazione dei criteri di conferenza per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="c27a3-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="c27a3-104">[] Le conferenze sono una parte importante di Skype for Business online: le conferenze consentono a gruppi di utenti di incontrarsi online per visualizzare diapositive e video, condividere applicazioni, scambiare file e comunicare e collaborare in altro modo.</span><span class="sxs-lookup"><span data-stu-id="c27a3-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="c27a3-p101">È importante mantenere il controllo sulle conferenze e sulle impostazioni di conferenza. In alcuni casi, ci possono essere problemi di sicurezza: per impostazione predefinita chiunque, compresi gli utenti non autenticati, può partecipare alle riunioni e salvare qualsiasi diapositiva o dispensa distribuita durante tali riunioni. Inoltre, ci potrebbero essere preoccupazioni di carattere legale. Per esempio, per impostazione predefinita i partecipanti sono autorizzati a fare annotazioni sui contenuti condivisi; tuttavia, queste annotazioni non vengono salvate quando viene archiviata la riunione. Se è necessario che l'organizzazione tenga un registro di tutte le comunicazioni elettroniche, può essere utile disabilitare le annotazioni.</span><span class="sxs-lookup"><span data-stu-id="c27a3-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="c27a3-p102">In Skype for Business online, le conferenze vengono gestite tramite criteri di conferenza. I criteri di conferenza determinano le caratteristiche e le funzionalità che possono essere utilizzate in una conferenza, dalla possibilità di includere audio e video via IP nella conferenza al numero massimo di persone che possono partecipare a una riunione. I criteri di conferenza possono essere configurati in ambito globale o per ciascun utente. Questo dà agli amministratori moltissima flessibilità quando si tratta di decidere quali funzionalità saranno messe a disposizione di quali gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c27a3-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="c27a3-114">Le impostazioni dei criteri possono essere configurate al momento della creazione di un criterio; alternativamente, è possibile usare il cmdlet **Set-CsConferencingPolicy** per modificare le impostazioni di un criterio esistente.</span><span class="sxs-lookup"><span data-stu-id="c27a3-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="c27a3-115">Impostare i criteri di conferenza</span><span class="sxs-lookup"><span data-stu-id="c27a3-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="c27a3-116">Per tutte le impostazioni dei criteri di conferenza in Skype for Business online è necessario utilizzare Windows PowerShell e **non è possibile** utilizzare l' **interfaccia di amministrazione di Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c27a3-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="c27a3-117">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c27a3-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="c27a3-118">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="c27a3-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="c27a3-119">A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c27a3-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c27a3-120">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c27a3-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="c27a3-121">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c27a3-121">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="c27a3-122">Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0.</span><span class="sxs-lookup"><span data-stu-id="c27a3-122">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="c27a3-123">Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="c27a3-123">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="c27a3-p104">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="c27a3-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="c27a3-127">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="c27a3-127">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="c27a3-128">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c27a3-128">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="c27a3-129">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c27a3-129">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c27a3-130">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="c27a3-130">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c27a3-131">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="c27a3-131">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="c27a3-132">Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c27a3-132">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="c27a3-133">Bloccare i trasferimenti di file e la condivisione del desktop durante le riunioni</span><span class="sxs-lookup"><span data-stu-id="c27a3-133">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="c27a3-134">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c27a3-134">To create a new policy for these settings, run:</span></span>
  > 
  > ```
  > New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  > ```
  > <span data-ttu-id="c27a3-135">Per altre informazioni, vedere il cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c27a3-135">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="c27a3-136">Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c27a3-136">To grant the new policy you created to all users in your organization, run:</span></span>
  > 
  > ```
  > Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  > ```
  > <span data-ttu-id="c27a3-137">Per altre informazioni, vedere il cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c27a3-137">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="c27a3-138">Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) per apportare modifiche al criterio esistente, quindi utilizzare il cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) per applicare le impostazioni ai propri utenti.</span><span class="sxs-lookup"><span data-stu-id="c27a3-138">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="c27a3-139">Bloccare la registrazione di conferenze e impedire che utenti anonimi partecipino alle riunioni</span><span class="sxs-lookup"><span data-stu-id="c27a3-139">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="c27a3-140">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c27a3-140">To create a new policy for these settings, run:</span></span> 
  > 
  > ```
  > New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  > ```
  > <span data-ttu-id="c27a3-141">Per altre informazioni, vedere il cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c27a3-141">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="c27a3-142">Per assegnare il criterio creato ad Amos Marble, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c27a3-142">To grant the new policy you created to Amos Marble, run:</span></span>
  > 
  > ```
  >  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  > ```
  > <span data-ttu-id="c27a3-143">Per altre informazioni, vedere il cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c27a3-143">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="c27a3-144">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) per applicare le impostazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c27a3-144">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="c27a3-145">Impedire ai partecipanti anonimi di registrare le riunioni e agli utenti esterni di salvare il contenuto delle riunioni</span><span class="sxs-lookup"><span data-stu-id="c27a3-145">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="c27a3-146">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c27a3-146">To create a new policy for these settings, run:</span></span>  
  > 
  > ```
  > New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  > ```
  > <span data-ttu-id="c27a3-147">Per altre informazioni, vedere il cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c27a3-147">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="c27a3-148">Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c27a3-148">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```
>   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
>   ```

<span data-ttu-id="c27a3-149">Per altre informazioni, vedere il cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c27a3-149">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="c27a3-150">Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) per apportare modifiche al criterio esistente, quindi utilizzare il cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) per applicare le impostazioni ai propri utenti.</span><span class="sxs-lookup"><span data-stu-id="c27a3-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c27a3-151">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c27a3-151">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="c27a3-152">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="c27a3-152">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c27a3-153">È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="c27a3-153">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c27a3-154">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="c27a3-154">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c27a3-155">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c27a3-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c27a3-156">Sei motivi per cui potresti voler usare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="c27a3-156">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="c27a3-157">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c27a3-157">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c27a3-158">Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c27a3-158">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c27a3-159">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="c27a3-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c27a3-160">Usare Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c27a3-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c27a3-161">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c27a3-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="c27a3-162">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c27a3-162">Related topics</span></span>
[<span data-ttu-id="c27a3-163">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="c27a3-163">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="c27a3-164">Bloccare i trasferimenti di file Point-to-Point</span><span class="sxs-lookup"><span data-stu-id="c27a3-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="c27a3-165">Impostazione dei criteri client per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="c27a3-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
