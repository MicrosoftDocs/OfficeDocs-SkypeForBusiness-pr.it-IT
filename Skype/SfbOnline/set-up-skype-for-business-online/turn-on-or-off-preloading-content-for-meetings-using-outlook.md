---
title: Attivare o disattivare il precaricamento dei contenuti delle riunioni tramite Outlook
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: ff0603ca68f4e828fc3b6977065ac9ec3ca6a33d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103802"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="1921b-103">Attivare o disattivare il precaricamento dei contenuti delle riunioni tramite Outlook</span><span class="sxs-lookup"><span data-stu-id="1921b-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="1921b-104">Gli utenti possono precaricare contenuti, file o allegati a una convocazione di riunione di Outlook a una riunione Skype for Business online, ma è possibile attivarla o disattivarla.</span><span class="sxs-lookup"><span data-stu-id="1921b-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="1921b-105">È attivato per impostazione predefinita per tutte le organizzazioni che usano Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="1921b-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="1921b-106">Vedere come [Precaricare gli allegati per una riunione Skype for Business](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span><span class="sxs-lookup"><span data-stu-id="1921b-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1921b-107">Attualmente non sono disponibili cmdlet in Skype for Business online per l'impostazione o la visualizzazione dei valori online per _MaxContentStorageMB_ _e MaxUploadFileMB._</span><span class="sxs-lookup"><span data-stu-id="1921b-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="1921b-108">Sono disponibili solo per le distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="1921b-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="1921b-109">È importante sapere che il contenuto non verrà caricato in una riunione se il contenuto allegato supera _maxUploadFileSizeMB_ o se viene raggiunto il limite _MaxContentStorageMB._</span><span class="sxs-lookup"><span data-stu-id="1921b-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="1921b-110">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="1921b-110">To get you started</span></span>

## <a name="start-windows-powershell"></a><span data-ttu-id="1921b-111">Avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1921b-111">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="1921b-112">Skype for Business Online Connector fa attualmente parte dell'ultimo modulo di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="1921b-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="1921b-113">Se si usa l'ultima versione pubblica di Teams PowerShell, non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="1921b-113">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="1921b-114">Installare il [modulo di PowerShell di Teams.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="1921b-114">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="1921b-115">Aprire un Windows PowerShell comando ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1921b-115">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

<span data-ttu-id="1921b-116">Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi [di Microsoft 365 o Office 365 in](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) un'unica finestra di Windows PowerShell o Configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell .</span><span class="sxs-lookup"><span data-stu-id="1921b-116">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="1921b-117">Attivazione o disattivazione del precaricamento</span><span class="sxs-lookup"><span data-stu-id="1921b-117">Turning it on or off</span></span>

<span data-ttu-id="1921b-118">La possibilità di precaricare il contenuto allegato a un invito a una riunione di Outlook per le riunioni Skype for Business Online è attivata per impostazione predefinita, ma potrebbe essere necessario impedire agli utenti dell'organizzazione di precaricare il contenuto nelle riunioni.</span><span class="sxs-lookup"><span data-stu-id="1921b-118">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1921b-119">Questa impostazione può essere attivata o disattivata solo per l'intera organizzazione. non è possibile attivarla o disattivarla per un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="1921b-119">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="1921b-120">**Per disattivarla, aprire Windows PowerShell e procedere come segue:**</span><span class="sxs-lookup"><span data-stu-id="1921b-120">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="1921b-121">**Se si desidera riattivarla, aprire Windows PowerShell e procedere come segue:**</span><span class="sxs-lookup"><span data-stu-id="1921b-121">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1921b-122">Per saperne di più sulle Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1921b-122">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="1921b-123">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="1921b-123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1921b-124">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business online con un unico punto di amministrazione che può semplificare il lavoro quotidiano, quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="1921b-124">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1921b-125">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="1921b-125">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1921b-126">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1921b-126">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="1921b-127">Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="1921b-127">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="1921b-128">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="1921b-128">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1921b-129">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="1921b-129">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="1921b-130">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="1921b-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="1921b-131">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="1921b-131">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="1921b-132">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="1921b-132">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="1921b-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1921b-133">Related topics</span></span>
[<span data-ttu-id="1921b-134">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="1921b-134">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="1921b-135">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="1921b-135">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
