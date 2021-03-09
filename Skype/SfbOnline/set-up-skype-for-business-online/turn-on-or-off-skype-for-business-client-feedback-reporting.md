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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: È possibile consentire agli utenti di Skype for Business di utilizzare lo strumento di feedback integrato nell'app Skype for Business per consentire agli utenti di segnalare problemi e fornire feedback direttamente a Microsoft sulla loro esperienza.
ms.openlocfilehash: 9b9134f857be540a528ca12b51a4793c01f70fa4
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569002"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="be305-103">Attivare o disattivare i report di feedback client di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="be305-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="be305-104">È possibile consentire agli utenti di Skype for Business online di utilizzare lo strumento di feedback app Skype for Business integrato per consentire agli utenti di segnalare problemi e fornire feedback direttamente a Microsoft sulla loro esperienza.</span><span class="sxs-lookup"><span data-stu-id="be305-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Icona Fornisci feedback](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="be305-106">Usando questo strumento, un utente può copiare i log dall'app nel proprio dispositivo per consentire a Microsoft di analizzare meglio e risolvere i problemi che potrebbe avere.</span><span class="sxs-lookup"><span data-stu-id="be305-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Segnalare un problema usando l'icona Impostazioni](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="be305-108">Puoi anche utilizzare l'impostazione  _EnableOnlineFeedbackScreenshot_ in modo che gli utenti possano includere una schermata del proprio dispositivo nel loro feedback.</span><span class="sxs-lookup"><span data-stu-id="be305-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="be305-110">I log raccolti dallo strumento di feedback dell'app verranno archiviati per un massimo di 90 giorni negli Stati Uniti durante l'analisi del problema.</span><span class="sxs-lookup"><span data-stu-id="be305-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="be305-111">Per questo motivo, non abilitare questo strumento di feedback se questo viola i criteri di protezione dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="be305-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="be305-112">Iniziare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be305-112">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="be305-113">Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="be305-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="be305-114">Se si usa la versione pubblica più recente di Teams PowerShell, non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="be305-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="be305-115">Installare il [modulo Teams di PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="be305-115">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="be305-116">Aprire un Windows PowerShell comando ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="be305-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   <span data-ttu-id="be305-117">Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in](https://technet.microsoft.com/library/dn568015.aspx) un'unica finestra di Windows PowerShell oppure configurare il computer per [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="be305-117">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="be305-118">Attiva i report di feedback dell'applicazione client per tutti gli utenti dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="be305-118">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="be305-119">Per abilitare i report di feedback per gli utenti dell'organizzazione e consentire loro di inviare screenshot del dispositivo, esegui:</span><span class="sxs-lookup"><span data-stu-id="be305-119">To enable feedback reporting for users in your organization and allow them to submit device screenshots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="be305-120">Per saperne di più su Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="be305-120">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="be305-121">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="be305-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="be305-122">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business online con un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="be305-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="be305-123">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="be305-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="be305-124">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="be305-124">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="be305-125">Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="be305-125">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="be305-126">Windows PowerShell offre molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="be305-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="be305-127">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="be305-127">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="be305-128">Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="be305-128">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="be305-129">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="be305-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="be305-130">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="be305-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="be305-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="be305-131">Related topics</span></span>
[<span data-ttu-id="be305-132">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="be305-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="be305-133">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="be305-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
