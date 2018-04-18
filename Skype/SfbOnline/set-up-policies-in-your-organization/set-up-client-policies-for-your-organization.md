---
title: Impostare i criteri client per l'organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: I criteri client aiutano a determinare le funzioni di Skype for Business online messe a disposizione degli utenti; per esempio, si potrebbe dare ad alcuni utenti il diritto di trasferire i file negando lo stesso diritto ad altri utenti.
ms.openlocfilehash: 98bf7f0dba39e7fd56a0b6dd79600245eec4b7da
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="74eb9-103">Impostare i criteri client per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="74eb9-103">Set up client policies for your organization</span></span>

<span data-ttu-id="74eb9-104">[] I criteri client aiutano a determinare le funzioni di Skype for Business online messe a disposizione degli utenti; per esempio, si potrebbe dare ad alcuni utenti il diritto di trasferire i file negando lo stesso diritto ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="74eb9-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="74eb9-105">Impostazioni dei criteri client possono essere configurate durante la creazione di un criterio oppure è possibile utilizzare il cmdlet **Set-CsClientPolicy** per modificare le impostazioni di un criterio esistente.</span><span class="sxs-lookup"><span data-stu-id="74eb9-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="74eb9-106">Impostare i criteri client</span><span class="sxs-lookup"><span data-stu-id="74eb9-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="74eb9-107">Per tutte le impostazioni dei criteri client in Skype Business online, è necessario utilizzare Windows PowerShell e non è **possibile utilizzare** **Skype per interfaccia di amministrazione di Business**.</span><span class="sxs-lookup"><span data-stu-id="74eb9-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="74eb9-108">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74eb9-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="74eb9-109">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="74eb9-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="74eb9-110">A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="74eb9-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="74eb9-111">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="74eb9-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="74eb9-p101">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="74eb9-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="74eb9-p102">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="74eb9-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="74eb9-118">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="74eb9-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="74eb9-119">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="74eb9-119">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="74eb9-120">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="74eb9-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="74eb9-121">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="74eb9-121">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="74eb9-122">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="74eb9-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="74eb9-123">Se si desiderano ulteriori informazioni sull'avvio di Windows PowerShell, vedere [Connect a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connecting to Skype Business online tramite Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="74eb9-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="74eb9-124">Disattivare le notifiche di presenza e le emoticon e impedire il salvataggio dei messaggi immediati</span><span class="sxs-lookup"><span data-stu-id="74eb9-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="74eb9-125">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="74eb9-125">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  <span data-ttu-id="74eb9-126">Vedere ulteriori informazioni sui cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="74eb9-126">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="74eb9-127">Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="74eb9-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  <span data-ttu-id="74eb9-128">Vedere ulteriori informazioni sui cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="74eb9-128">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="74eb9-129">Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) per applicare le impostazioni per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="74eb9-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="74eb9-130">Abilitare URL o collegamenti ipertestuali perché siano cliccabili nei messaggi istantanei</span><span class="sxs-lookup"><span data-stu-id="74eb9-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="74eb9-131">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="74eb9-131">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  <span data-ttu-id="74eb9-132">Vedere ulteriori informazioni sui cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="74eb9-132">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="74eb9-133">Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="74eb9-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  <span data-ttu-id="74eb9-134">Vedere ulteriori informazioni sui cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="74eb9-134">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="74eb9-135">Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) per applicare le impostazioni per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="74eb9-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="74eb9-136">Impedire di mostrare i contatti recenti</span><span class="sxs-lookup"><span data-stu-id="74eb9-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="74eb9-137">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="74eb9-137">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  <span data-ttu-id="74eb9-138">Vedere ulteriori informazioni sui cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="74eb9-138">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="74eb9-139">Per assegnare il criterio creato ad Amos Marble, eseguire:</span><span class="sxs-lookup"><span data-stu-id="74eb9-139">To grant the new policy you created to Amos Marble, run:</span></span>
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  <span data-ttu-id="74eb9-140">Vedere ulteriori informazioni sui cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="74eb9-140">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="74eb9-141">Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) per applicare le impostazioni per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="74eb9-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="74eb9-142">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74eb9-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="74eb9-p103">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="74eb9-p103">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="74eb9-146">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="74eb9-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="74eb9-147">Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="74eb9-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="74eb9-p104">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="74eb9-p104">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="74eb9-150">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="74eb9-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="74eb9-151">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="74eb9-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="74eb9-152">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="74eb9-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="74eb9-153">See also</span><span class="sxs-lookup"><span data-stu-id="74eb9-153">Related topics</span></span>
[<span data-ttu-id="74eb9-154">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="74eb9-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="74eb9-155">Trasferimenti di file bloccati punto-punto</span><span class="sxs-lookup"><span data-stu-id="74eb9-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="74eb9-156">Impostare i criteri relativi alle conferenze nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="74eb9-156">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 