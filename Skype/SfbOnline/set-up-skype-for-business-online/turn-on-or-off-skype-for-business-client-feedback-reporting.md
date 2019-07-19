---
title: Attivare o disattivare i report di feedback client di Skype for Business
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
description: Puoi consentire agli utenti di Skype for business di usare lo strumento di feedback delle app Skype for business predefinito per consentire agli utenti di segnalare problemi e inviare commenti e suggerimenti direttamente a Microsoft sulle loro esperienze.
ms.openlocfilehash: d7d80110be63b60fcfa1581c806d01ab0f056077
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792668"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="f18c7-103">Attivare o disattivare i report di feedback client di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f18c7-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="f18c7-104">Puoi consentire agli utenti di Skype for business online di usare lo strumento di feedback delle app Skype for business predefinito per consentire agli utenti di segnalare problemi e inviare commenti e suggerimenti direttamente a Microsoft sulle loro esperienze.</span><span class="sxs-lookup"><span data-stu-id="f18c7-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="f18c7-106">Usando questo strumento, un utente può copiare i log dall'app nel dispositivo per aiutare Microsoft a individuare e risolvere i problemi che potrebbero avere.</span><span class="sxs-lookup"><span data-stu-id="f18c7-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="f18c7-108">Puoi anche utilizzare l'impostazione  _EnableOnlineFeedbackScreenshot_ in modo che gli utenti possano includere una schermata del proprio dispositivo nel loro feedback.</span><span class="sxs-lookup"><span data-stu-id="f18c7-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="f18c7-110">I log raccolti dallo strumento di feedback dell'app verranno archiviati fino a un massimo di 90 giorni negli Stati Uniti durante l'analisi del problema.</span><span class="sxs-lookup"><span data-stu-id="f18c7-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="f18c7-111">Per questo motivo, non abilitare questo strumento di feedback se questo viola i criteri di protezione dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f18c7-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="f18c7-112">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f18c7-112">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="f18c7-113">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="f18c7-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="f18c7-114">A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f18c7-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="f18c7-115">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f18c7-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="f18c7-116">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f18c7-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="f18c7-117">Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0.</span><span class="sxs-lookup"><span data-stu-id="f18c7-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="f18c7-118">Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="f18c7-118">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="f18c7-p103">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="f18c7-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="f18c7-122">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="f18c7-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="f18c7-123">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f18c7-123">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="f18c7-124">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f18c7-124">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="f18c7-125">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="f18c7-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f18c7-126">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="f18c7-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
 
   ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   <span data-ttu-id="f18c7-127">Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o[configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f18c7-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="f18c7-128">Attiva i report di feedback dell'applicazione client per tutti gli utenti dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f18c7-128">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="f18c7-129">Per abilitare la segnalazione di feedback per gli utenti dell'organizzazione e consentire loro di inviare le schermate del dispositivo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="f18c7-129">To enable feedback reporting for users in your organization and allow them to submit device screen shots, run:</span></span>
 
  ```
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f18c7-130">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f18c7-130">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="f18c7-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="f18c7-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f18c7-132">È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="f18c7-132">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="f18c7-133">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="f18c7-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f18c7-134">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f18c7-134">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f18c7-135">Sei motivi per cui potresti voler usare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="f18c7-135">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="f18c7-136">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="f18c7-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f18c7-137">Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f18c7-137">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f18c7-138">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="f18c7-138">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="f18c7-139">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f18c7-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f18c7-140">Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f18c7-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="f18c7-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f18c7-141">Related topics</span></span>
[<span data-ttu-id="f18c7-142">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="f18c7-142">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="f18c7-143">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="f18c7-143">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
