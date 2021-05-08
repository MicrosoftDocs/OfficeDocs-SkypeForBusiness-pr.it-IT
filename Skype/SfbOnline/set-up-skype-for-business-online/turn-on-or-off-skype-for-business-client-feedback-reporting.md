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
description: È possibile consentire agli utenti Skype for Business utenti di usare lo strumento di feedback dell'app Skype for Business incorporato per consentire agli utenti di segnalare i problemi e fornire feedback direttamente a Microsoft sulla loro esperienza.
ms.openlocfilehash: 151ba9ee82c95f088f5c7fc87de3a06ce609ab01
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239099"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="55635-103">Attivare o disattivare i report di feedback client di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="55635-103">Turn on or off Skype for Business client feedback reporting</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="55635-104">È possibile consentire agli utenti di Skype for Business Online di usare lo strumento di feedback dell'app Skype for Business incorporato per consentire agli utenti di segnalare i problemi e inviare feedback direttamente a Microsoft sulla loro esperienza.</span><span class="sxs-lookup"><span data-stu-id="55635-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Icona Fornisci feedback](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="55635-106">Usando questo strumento, un utente può copiare i log dall'app nel dispositivo per consentire a Microsoft di analizzare e risolvere meglio i problemi che potrebbero verificarsi.</span><span class="sxs-lookup"><span data-stu-id="55635-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Segnalare un problema con l'icona Impostazioni](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="55635-108">Puoi anche utilizzare l'impostazione  _EnableOnlineFeedbackScreenshot_ in modo che gli utenti possano includere una schermata del proprio dispositivo nel loro feedback.</span><span class="sxs-lookup"><span data-stu-id="55635-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="55635-110">I log raccolti dallo strumento di feedback dell'app verranno archiviati fino a un massimo di 90 giorni negli Stati Uniti durante l'analisi del problema.</span><span class="sxs-lookup"><span data-stu-id="55635-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="55635-111">Per questo motivo, non abilitare questo strumento di feedback se questo viola i criteri di protezione dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="55635-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="55635-112">Avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55635-112">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="55635-113">Skype for Business Online Connector fa attualmente parte dell'Teams di PowerShell più recente.</span><span class="sxs-lookup"><span data-stu-id="55635-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="55635-114">Se si usa la versione pubblica più recente Teams PowerShell, non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="55635-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="55635-115">Installare il [modulo Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="55635-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="55635-116">Aprire un Windows PowerShell prompt dei comandi ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="55635-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   <span data-ttu-id="55635-117">Per altre informazioni sull'avvio di Windows PowerShell, vedere Connessione a tutti i servizi Microsoft 365 o Office 365 in un'unica finestra [di Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell .</span><span class="sxs-lookup"><span data-stu-id="55635-117">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="55635-118">Attiva i report di feedback dell'applicazione client per tutti gli utenti dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="55635-118">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="55635-119">Per abilitare la segnalazione di feedback per gli utenti dell'organizzazione e consentire loro di inviare screenshot del dispositivo, esegui:</span><span class="sxs-lookup"><span data-stu-id="55635-119">To enable feedback reporting for users in your organization and allow them to submit device screenshots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="55635-120">Vuoi saperne di più su Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="55635-120">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="55635-121">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="55635-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="55635-122">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business Online usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando è necessario eseguire più attività.</span><span class="sxs-lookup"><span data-stu-id="55635-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="55635-123">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="55635-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="55635-124">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="55635-124">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="55635-125">Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="55635-125">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="55635-126">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="55635-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="55635-127">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="55635-127">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="55635-128">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="55635-128">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="55635-129">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="55635-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="55635-130">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="55635-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="55635-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="55635-131">Related topics</span></span>
[<span data-ttu-id="55635-132">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="55635-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="55635-133">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="55635-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
