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
ms.openlocfilehash: bee2d4094e1a85db39514e0757e58092544653a1
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164085"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="51fba-103">Attivare o disattivare il precaricamento dei contenuti delle riunioni tramite Outlook</span><span class="sxs-lookup"><span data-stu-id="51fba-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="51fba-104">Gli utenti possono precaricare il contenuto, i file o gli allegati associati a un invito a una riunione di Outlook a una riunione Skype for business online, ma è possibile attivarla o disattivarla.</span><span class="sxs-lookup"><span data-stu-id="51fba-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="51fba-105">È attivata per impostazione predefinita per tutte le organizzazioni che usano Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="51fba-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="51fba-106">Vedere come [Precaricare gli allegati per una riunione Skype for Business](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span><span class="sxs-lookup"><span data-stu-id="51fba-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="51fba-107">Attualmente non sono disponibili cmdlet in Skype for business online per l'impostazione o la visualizzazione di valori online per _MaxContentStorageMB_ e _MaxUploadFileMB_.</span><span class="sxs-lookup"><span data-stu-id="51fba-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="51fba-108">Sono disponibili solo per le distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="51fba-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="51fba-109">È importante sapere che il contenuto non verrà caricato in una riunione se il contenuto allegato supera il _MaxUploadFileSizeMB_ o se viene raggiunto il limite di _MaxContentStorageMB_ .</span><span class="sxs-lookup"><span data-stu-id="51fba-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="51fba-110">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="51fba-110">To get you started</span></span>

### 

 <span data-ttu-id="51fba-111">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="51fba-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="51fba-112">A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="51fba-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="51fba-113">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="51fba-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="51fba-114">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51fba-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="51fba-115">Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0.</span><span class="sxs-lookup"><span data-stu-id="51fba-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="51fba-116">Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="51fba-116">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="51fba-p104">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="51fba-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="51fba-120">Per saperne di più, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="51fba-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="51fba-121">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="51fba-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="51fba-122">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="51fba-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="51fba-123">Nella finestra di **Windows PowerShell** connettersi a Microsoft 365 o Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="51fba-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51fba-124">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="51fba-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
```PowerShell
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

<span data-ttu-id="51fba-125">Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="51fba-125">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="51fba-126">Attivazione o disattivazione del precaricamento</span><span class="sxs-lookup"><span data-stu-id="51fba-126">Turning it on or off</span></span>

<span data-ttu-id="51fba-127">La possibilità di precaricare il contenuto allegato a un invito a una riunione di Outlook a riunioni Skype for business online è attivata per impostazione predefinita, ma potrebbe essere necessario impedire agli utenti dell'organizzazione di precaricare il contenuto nelle riunioni.</span><span class="sxs-lookup"><span data-stu-id="51fba-127">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="51fba-128">Questa impostazione può essere attivata o disattivata solo per l'intera organizzazione; non è possibile attivarlo o disattivarlo per un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="51fba-128">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="51fba-129">**Per disattivarla, aprire Windows PowerShell e procedere come segue:**</span><span class="sxs-lookup"><span data-stu-id="51fba-129">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="51fba-130">**Se si desidera riattivarla, aprire Windows PowerShell e procedere come segue:**</span><span class="sxs-lookup"><span data-stu-id="51fba-130">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="51fba-131">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51fba-131">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="51fba-132">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="51fba-132">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="51fba-133">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 e Skype for business online con un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="51fba-133">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="51fba-134">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="51fba-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="51fba-135">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="51fba-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="51fba-136">Sei motivi per cui potresti voler usare Windows PowerShell per gestire Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="51fba-136">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="51fba-137">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="51fba-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="51fba-138">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="51fba-138">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="51fba-139">Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51fba-139">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="51fba-140">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="51fba-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="51fba-141">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="51fba-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="51fba-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="51fba-142">Related topics</span></span>
[<span data-ttu-id="51fba-143">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="51fba-143">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="51fba-144">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="51fba-144">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
