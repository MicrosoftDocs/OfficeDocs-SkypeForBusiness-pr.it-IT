---
title: Attivare o disattivare i messaggi offline per gli amministratori
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
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
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: ec5aad56ef7557c9b7854c6844d65ff3799d1d1c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568756"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="6d62b-103">Attivare o disattivare i messaggi offline per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="6d62b-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="6d62b-104">È possibile inviare messaggi automatici di Skype for Business ai propri contatti anche se non hanno effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6d62b-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="6d62b-105">Questa funzione consente di far sapere ai contatti che si sta tentando di mettersi in contatto con loro.</span><span class="sxs-lookup"><span data-stu-id="6d62b-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="6d62b-106">Non è necessario attendere che gli utenti siano online prima di inviare loro un messaggio.</span><span class="sxs-lookup"><span data-stu-id="6d62b-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="6d62b-107">Per i messaggi offline, è importante sapere:</span><span class="sxs-lookup"><span data-stu-id="6d62b-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="6d62b-108">I messaggi offline non verranno archiviati nella cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6d62b-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="6d62b-109">I messaggi offline verranno inviati alla cassetta postale dell'utente e l'utente riceverà una notifica quando accede a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6d62b-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="6d62b-110">Se lo stato del destinatario  del messaggio è impostato su Non disturbare o Presentazione **in** corso, riceverà un messaggio perso inviato dal client Skype for Business del destinatario.</span><span class="sxs-lookup"><span data-stu-id="6d62b-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="6d62b-111">Per ulteriori informazioni, consulta [Utilizzare la messaggistica offline in Skype for Business.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)</span><span class="sxs-lookup"><span data-stu-id="6d62b-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="6d62b-112">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="6d62b-112">To get you started</span></span>

> [!NOTE]
> <span data-ttu-id="6d62b-113">Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="6d62b-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="6d62b-114">Se si usa la versione pubblica più recente di Teams PowerShell, non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="6d62b-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="6d62b-115">Installare il [modulo Teams di PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="6d62b-115">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="6d62b-116">Aprire un Windows PowerShell comando ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d62b-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
<span data-ttu-id="6d62b-117">Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi di [Office 365 in](https://technet.microsoft.com/library/dn568015.aspx) un'unica finestra di Windows PowerShell o configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d62b-117">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="6d62b-118">Attivazione o disattivazione della messaggistica offline</span><span class="sxs-lookup"><span data-stu-id="6d62b-118">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="6d62b-119">I messaggi  offline sono disponibili solo nell'ultima versione del client Skype for Business A scelta e non sono disponibili quando si usa una versione precedente di Skype for Business A scelta o se è stato usato un file \*.msi per installare il client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6d62b-119">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="6d62b-120">Per abilitare o disabilitare l'invio di messaggi offline per gli utenti dell'organizzazione, impostare  _EnableIMAutoArchiving_ su `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="6d62b-120">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="6d62b-121">Per impostazione predefinita, è impostato su `True` .</span><span class="sxs-lookup"><span data-stu-id="6d62b-121">By default, this is set to `True`.</span></span>

<span data-ttu-id="6d62b-122">Per disattivarli, utilizzare il cmdlet **Set-CsClientPolicy** ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="6d62b-122">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="6d62b-123">Per abilitare o disabilitare l'invio di messaggi offline per un utente, impostare  _EnableIMAutoArchiving_ su `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="6d62b-123">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="6d62b-124">Per impostazione predefinita, è impostato su  `True`.</span><span class="sxs-lookup"><span data-stu-id="6d62b-124">By default, this is set to  `True`.</span></span> <span data-ttu-id="6d62b-125">È possibile usare criteri esistenti o crearne uno come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6d62b-125">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6d62b-126">Per saperne di più su Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6d62b-126">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="6d62b-127">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="6d62b-127">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6d62b-128">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business online con un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="6d62b-128">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="6d62b-129">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="6d62b-129">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="6d62b-130">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6d62b-130">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="6d62b-131">Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="6d62b-131">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="6d62b-132">Windows PowerShell offre molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="6d62b-132">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6d62b-133">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="6d62b-133">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="6d62b-134">Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="6d62b-134">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="6d62b-135">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="6d62b-135">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="6d62b-136">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="6d62b-136">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="6d62b-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6d62b-137">Related topics</span></span>
[<span data-ttu-id="6d62b-138">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="6d62b-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="6d62b-139">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="6d62b-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
