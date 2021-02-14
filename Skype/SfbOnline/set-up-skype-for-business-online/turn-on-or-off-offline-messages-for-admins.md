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
ms.openlocfilehash: 12d5a6c736616cb9448dc1f75a6f67424d940d7f
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814605"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="78eb0-103">Attivare o disattivare i messaggi offline per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="78eb0-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="78eb0-p101">È possibile inviare messaggi automatici di Skype for Business ai propri contatti anche se non hanno eseguito l'accesso. Questa funzione consente di far sapere ai contatti che si sta tentando di raggiungerli. Non è necessario aspettare che un utente sia online prima di inviarle un messaggio.</span><span class="sxs-lookup"><span data-stu-id="78eb0-p101">You can send Skype for Business IMs to your contacts even if they aren't signed in. This feature lets your contacts know that you have been trying to reach them. You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="78eb0-107">Per i messaggi offline, è importante sapere:</span><span class="sxs-lookup"><span data-stu-id="78eb0-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="78eb0-108">I messaggi offline non verranno archiviati nella cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="78eb0-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="78eb0-109">I messaggi offline verranno inviati alla cassetta postale dell'utente e l'utente riceverà una notifica quando accede a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="78eb0-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="78eb0-110">Se lo stato del destinatario  del messaggio è impostato su Non disturbare o Presentazione **in** corso, riceverà un messaggio perso inviato dal client Skype for Business del destinatario.</span><span class="sxs-lookup"><span data-stu-id="78eb0-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="78eb0-111">Per ulteriori informazioni, consulta [Utilizzare la messaggistica offline in Skype for Business.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)</span><span class="sxs-lookup"><span data-stu-id="78eb0-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="78eb0-112">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="78eb0-112">To get you started</span></span>

## #

 <span data-ttu-id="78eb0-113">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="78eb0-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="78eb0-114">A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="78eb0-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="78eb0-115">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="78eb0-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="78eb0-116">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78eb0-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="78eb0-117">Vedere [Windows Management Framework 4.0 per](https://go.microsoft.com/fwlink/?LinkId=716845) scaricare e aggiornare Windows PowerShell alla versione 4.0.</span><span class="sxs-lookup"><span data-stu-id="78eb0-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="78eb0-118">Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="78eb0-118">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="78eb0-119">Dovrai inoltre installare il modulo Windows PowerShell per Teams che ti consente di creare una sessione Windows PowerShell remota che si connette a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="78eb0-119">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>

<span data-ttu-id="78eb0-120">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="78eb0-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="78eb0-121">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="78eb0-121">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="78eb0-122">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="78eb0-122">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="78eb0-123">Nella finestra **Windows PowerShell** connessione a Microsoft 365 o Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="78eb0-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>

   > [!NOTE]
   > <span data-ttu-id="78eb0-124">Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="78eb0-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   >
   > <span data-ttu-id="78eb0-125">Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="78eb0-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

  ```PowerShell
  Import-Module -Name MicrosoftTeams
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="78eb0-126">Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi di [Office 365 in](https://technet.microsoft.com/library/dn568015.aspx) un'unica finestra di Windows PowerShell o configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78eb0-126">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="78eb0-127">Attivazione o disattivazione della messaggistica offline</span><span class="sxs-lookup"><span data-stu-id="78eb0-127">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="78eb0-128">I messaggi  offline sono disponibili solo nell'ultima versione del client Skype for Business A scelta e non sono disponibili quando si usa una versione precedente di Skype for Business A scelta o se è stato usato un file \*.msi per installare il client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="78eb0-128">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="78eb0-129">Per abilitare o disabilitare l'invio di messaggi offline per gli utenti dell'organizzazione, impostare  _EnableIMAutoArchiving_ su `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="78eb0-129">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="78eb0-130">Per impostazione predefinita, è impostato su `True` .</span><span class="sxs-lookup"><span data-stu-id="78eb0-130">By default, this is set to `True`.</span></span>

<span data-ttu-id="78eb0-131">Per disattivarli, utilizzare il cmdlet **Set-CsClientPolicy** ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="78eb0-131">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="78eb0-132">Per abilitare o disabilitare l'invio di messaggi offline per un utente, impostare  _EnableIMAutoArchiving_ su `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="78eb0-132">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="78eb0-133">Per impostazione predefinita, è impostato su  `True`.</span><span class="sxs-lookup"><span data-stu-id="78eb0-133">By default, this is set to  `True`.</span></span> <span data-ttu-id="78eb0-134">È possibile usare criteri esistenti o crearne uno come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="78eb0-134">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="78eb0-135">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78eb0-135">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="78eb0-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="78eb0-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="78eb0-137">Con Windows PowerShell puoi gestire Microsoft 365 o Office 365 e Skype for Business online tramite un unico punto di amministrazione, che ti semplifica il lavoro quotidiano, quando hai più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="78eb0-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="78eb0-138">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="78eb0-138">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="78eb0-139">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="78eb0-139">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="78eb0-140">Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="78eb0-140">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="78eb0-141">Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="78eb0-141">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="78eb0-142">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="78eb0-142">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="78eb0-143">Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78eb0-143">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="78eb0-144">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="78eb0-144">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="78eb0-145">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="78eb0-145">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="78eb0-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="78eb0-146">Related topics</span></span>
[<span data-ttu-id="78eb0-147">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="78eb0-147">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="78eb0-148">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="78eb0-148">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


