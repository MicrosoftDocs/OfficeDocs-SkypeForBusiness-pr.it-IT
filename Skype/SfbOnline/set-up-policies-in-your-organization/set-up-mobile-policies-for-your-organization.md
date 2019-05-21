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
f1keywords: None
ms.custom:
- Setup
description: Puoi configurare il modo in cui gli utenti si connettono a Skype for business online con l'app Skype for business su dispositivi mobili, ad esempio una funzionalità che consente agli utenti di effettuare e ricevere chiamate telefoniche sul proprio telefono cellulare usando il proprio numero di telefono aziendale anziché il telefono cellulare nu Mbera. I criteri di mobilità possono essere utilizzati anche per richiedere la presenza di connessioni Wi-Fi quando si effettuano o ricevono chiamate.
ms.openlocfilehash: 844328425daa8076f0d861911ba989594ff832e6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297699"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="4be7e-104">Impostazione dei criteri per dispositivi mobili per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="4be7e-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="4be7e-105">Puoi configurare il modo in cui gli utenti si connettono a Skype for business online con l'app Skype for business su dispositivi mobili, ad esempio una funzionalità che consente agli utenti di effettuare e ricevere chiamate telefoniche sul proprio telefono cellulare usando il proprio numero di telefono aziendale anziché il telefono cellulare nu Mbera.</span><span class="sxs-lookup"><span data-stu-id="4be7e-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="4be7e-106">I criteri di mobilità possono essere utilizzati anche per richiedere la presenza di connessioni Wi-Fi quando si effettuano o ricevono chiamate.</span><span class="sxs-lookup"><span data-stu-id="4be7e-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="4be7e-107">Le impostazioni dei criteri per dispositivi mobili possono essere configurate al momento della creazione di un criterio oppure puoi usare il cmdlet **Set-CsMobilityPolicy** per modificare le impostazioni di un criterio esistente.</span><span class="sxs-lookup"><span data-stu-id="4be7e-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="4be7e-108">Impostare i criteri di mobilità</span><span class="sxs-lookup"><span data-stu-id="4be7e-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="4be7e-109">Per tutte le impostazioni dei criteri per dispositivi mobili in Skype for business online, è necessario utilizzare Windows PowerShell e non è possibile **usare** l'interfaccia di **amministrazione di Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="4be7e-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="4be7e-110">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4be7e-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="4be7e-111">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="4be7e-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="4be7e-112">A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4be7e-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4be7e-113">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4be7e-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="4be7e-p103">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="4be7e-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="4be7e-p104">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="4be7e-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="4be7e-120">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="4be7e-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="4be7e-121">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4be7e-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="4be7e-122">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4be7e-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4be7e-123">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="4be7e-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4be7e-124">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="4be7e-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="4be7e-125">Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4be7e-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="4be7e-126">Richiedere una connessione Wi-Fi per il video per un utente</span><span class="sxs-lookup"><span data-stu-id="4be7e-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="4be7e-127">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4be7e-127">To create a new policy for these settings, run:</span></span>
  > 
  > ```
  > New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  > ```
  > <span data-ttu-id="4be7e-128">Per altre informazioni, vedere il cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4be7e-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="4be7e-129">Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4be7e-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
  > 
  > ```
  > Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  > ```
  > <span data-ttu-id="4be7e-130">Per altre informazioni, vedere il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4be7e-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="4be7e-131">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) per applicare l'impostazione agli utenti.</span><span class="sxs-lookup"><span data-stu-id="4be7e-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="4be7e-132">Impedire a un utente di usare l'app di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4be7e-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="4be7e-133">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4be7e-133">To create a new policy for these settings, run:</span></span>
  ```
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="4be7e-134">Per altre informazioni, vedere il cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4be7e-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="4be7e-135">Per assegnare il criterio creato ad Amos Marble, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4be7e-135">To grant the new policy you created to Amos Marble, run:</span></span>  
  > 
  > ```
  > Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  > ```
  > <span data-ttu-id="4be7e-136">Per altre informazioni, vedere il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4be7e-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="4be7e-137">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) per applicare l'impostazione agli utenti.</span><span class="sxs-lookup"><span data-stu-id="4be7e-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="4be7e-138">Impedire a un utente di effettuare chiamate voice over IP utilizzando un dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="4be7e-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="4be7e-139">Per creare un nuovo criterio per queste impostazioni, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4be7e-139">To create a new policy for these settings, run:</span></span>
  > 
  > ```
  > New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  > ```
  > <span data-ttu-id="4be7e-140">Per altre informazioni, vedere il cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4be7e-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="4be7e-141">Per assegnare il criterio creato a tutti gli utenti dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4be7e-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
  > 
  > ```
  > Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  > ```

  <span data-ttu-id="4be7e-142">Per altre informazioni, vedere il cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4be7e-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="4be7e-143">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) per applicare l'impostazione agli utenti.</span><span class="sxs-lookup"><span data-stu-id="4be7e-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4be7e-144">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4be7e-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="4be7e-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="4be7e-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4be7e-146">È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="4be7e-146">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4be7e-147">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="4be7e-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4be7e-148">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4be7e-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4be7e-149">Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="4be7e-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="4be7e-p106">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4be7e-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4be7e-152">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="4be7e-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="4be7e-153">Usare Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="4be7e-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4be7e-154">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="4be7e-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="4be7e-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4be7e-155">Related topics</span></span>
[<span data-ttu-id="4be7e-156">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="4be7e-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="4be7e-157">Bloccare i trasferimenti di file Point-to-Point</span><span class="sxs-lookup"><span data-stu-id="4be7e-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="4be7e-158">Impostazione dei criteri client per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="4be7e-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="4be7e-159">Configurare i criteri di conferenza nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4be7e-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
