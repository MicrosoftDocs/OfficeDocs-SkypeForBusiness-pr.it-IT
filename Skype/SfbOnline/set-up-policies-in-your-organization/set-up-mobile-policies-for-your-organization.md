---
title: Impostazione dei criteri per dispositivi mobili per la propria organizzazione
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Puoi configurare il modo in cui gli utenti si connettono a Skype for business online usando l'app Skype for business su dispositivi mobili, ad esempio una funzionalità che consente agli utenti di effettuare e ricevere chiamate telefoniche sul proprio telefono cellulare usando il proprio numero di telefono aziendale anziché il numero di cellulare. I criteri di mobilità possono essere usati anche per richiedere connessioni Wi-Fi durante la creazione o la ricezione di chiamate.
ms.openlocfilehash: 5094a536a636300ea70a7d358e24ee5c0f511379
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814745"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="3b2c7-104">Impostazione dei criteri per dispositivi mobili per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="3b2c7-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="3b2c7-p102">Puoi configurare il modo in cui gli utenti si connettono a Skype for business online usando l'app Skype for business su dispositivi mobili, ad esempio una funzionalità che consente agli utenti di effettuare e ricevere chiamate telefoniche sul proprio telefono cellulare usando il proprio numero di telefono aziendale anziché il numero di cellulare. I criteri di mobilità possono essere usati anche per richiedere connessioni Wi-Fi durante la creazione o la ricezione di chiamate.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="3b2c7-107">Le impostazioni dei criteri per dispositivi mobili possono essere configurate al momento della creazione di un criterio oppure puoi usare il cmdlet **Set-CsMobilityPolicy** per modificare le impostazioni di un criterio esistente.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="3b2c7-108">Impostare i criteri di mobilità</span><span class="sxs-lookup"><span data-stu-id="3b2c7-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="3b2c7-109">Per tutte le impostazioni dei criteri per dispositivi mobili in Skype for business online, è necessario utilizzare Windows PowerShell e non è possibile **usare** l'interfaccia di **amministrazione di Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="3b2c7-110">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b2c7-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="3b2c7-111">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="3b2c7-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="3b2c7-112">A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="3b2c7-113">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="3b2c7-p103">Se non si ha la versione 3,0 o successiva, è necessario scaricare e installare gli aggiornamenti in Windows PowerShell. Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0. Riavviare il computer quando viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="3b2c7-117">Sarà inoltre necessario installare il modulo di Windows PowerShell per Teams che consente di creare una sessione remota di Windows PowerShell che si connette a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-117">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="3b2c7-118">Per saperne di più, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="3b2c7-118">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="3b2c7-119">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3b2c7-119">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="3b2c7-120">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="3b2c7-121">Nella finestra di **Windows PowerShell** connettersi a Microsoft 365 o Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="3b2c7-121">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
       > [!NOTE]
       > <span data-ttu-id="3b2c7-122">Skype for Business Online Connector fa attualmente parte del modulo di PowerShell più recente di teams.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-122">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
       >
       > <span data-ttu-id="3b2c7-123">Se si usa l'ultima [versione pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/), non è necessario installare il connettore Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-123">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="3b2c7-124">Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3b2c7-124">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="3b2c7-125">Richiedere una connessione Wi-Fi per il video per un utente</span><span class="sxs-lookup"><span data-stu-id="3b2c7-125">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="3b2c7-126">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3b2c7-126">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="3b2c7-127">Per altre informazioni, vedere il cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3b2c7-127">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="3b2c7-128">Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3b2c7-128">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="3b2c7-129">Per altre informazioni, vedere il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3b2c7-129">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="3b2c7-130">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) per applicare l'impostazione agli utenti.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-130">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="3b2c7-131">Impedire a un utente di usare l'app di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3b2c7-131">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="3b2c7-132">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3b2c7-132">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="3b2c7-133">Per altre informazioni, vedere il cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3b2c7-133">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="3b2c7-134">Per assegnare il criterio creato ad Amos Marble, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3b2c7-134">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="3b2c7-135">Per altre informazioni, vedere il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3b2c7-135">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="3b2c7-136">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) per applicare l'impostazione agli utenti.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-136">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="3b2c7-137">Impedire a un utente di effettuare chiamate voice over IP utilizzando un dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="3b2c7-137">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="3b2c7-138">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3b2c7-138">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="3b2c7-139">Per altre informazioni, vedere il cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3b2c7-139">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="3b2c7-140">Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3b2c7-140">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="3b2c7-141">Per altre informazioni, vedere il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3b2c7-141">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="3b2c7-142">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) per applicare l'impostazione agli utenti.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-142">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3b2c7-143">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b2c7-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="3b2c7-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3b2c7-145">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 e Skype for business online con un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="3b2c7-146">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="3b2c7-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3b2c7-147">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3b2c7-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3b2c7-148">Sei motivi per cui potresti voler usare Windows PowerShell per gestire Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="3b2c7-148">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="3b2c7-149">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3b2c7-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3b2c7-150">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="3b2c7-150">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="3b2c7-151">Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b2c7-151">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="3b2c7-152">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="3b2c7-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3b2c7-153">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="3b2c7-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="3b2c7-154">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3b2c7-154">Related topics</span></span>
[<span data-ttu-id="3b2c7-155">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="3b2c7-155">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="3b2c7-156">Bloccare i trasferimenti di file Point-to-Point</span><span class="sxs-lookup"><span data-stu-id="3b2c7-156">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="3b2c7-157">Impostazione dei criteri client per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="3b2c7-157">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="3b2c7-158">Configurare i criteri di conferenza nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3b2c7-158">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
