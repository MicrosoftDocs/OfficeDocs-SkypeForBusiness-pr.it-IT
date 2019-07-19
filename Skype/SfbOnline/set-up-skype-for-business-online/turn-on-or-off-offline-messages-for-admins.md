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
f1keywords: None
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 85e8378c41f3d2398982bacee3c568291903ccce
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792995"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="aafd9-103">Attivare o disattivare i messaggi offline per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="aafd9-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="aafd9-104">È possibile inviare messaggi istantanei di Skype for business ai contatti anche se non sono stati registrati.</span><span class="sxs-lookup"><span data-stu-id="aafd9-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="aafd9-105">Questa funzione consente di far sapere ai contatti che si sta tentando di mettersi in contatto con loro.</span><span class="sxs-lookup"><span data-stu-id="aafd9-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="aafd9-106">Non è necessario attendere che gli utenti siano online prima di inviare loro un messaggio.</span><span class="sxs-lookup"><span data-stu-id="aafd9-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="aafd9-107">Per i messaggi offline, è importante sapere:</span><span class="sxs-lookup"><span data-stu-id="aafd9-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="aafd9-108">I messaggi offline non verranno archiviati nella cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="aafd9-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="aafd9-109">I messaggi offline verranno inviati alla cassetta postale dell'utente e l'utente riceverà una notifica quando accederà a Skype for business.</span><span class="sxs-lookup"><span data-stu-id="aafd9-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="aafd9-110">Se lo stato del destinatario del messaggio è impostato su **non disturbare** o **presentare**, riceverà un messaggio perso inviato dal client Skype for business del destinatario.</span><span class="sxs-lookup"><span data-stu-id="aafd9-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="aafd9-111">Per altre informazioni, vedere [usare la messaggistica offline in Skype for business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span><span class="sxs-lookup"><span data-stu-id="aafd9-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="aafd9-112">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="aafd9-112">To get you started</span></span>

## #

 <span data-ttu-id="aafd9-113">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="aafd9-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="aafd9-114">A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="aafd9-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="aafd9-115">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="aafd9-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="aafd9-116">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aafd9-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="aafd9-117">Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0.</span><span class="sxs-lookup"><span data-stu-id="aafd9-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="aafd9-118">Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="aafd9-118">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="aafd9-p103">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="aafd9-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>

<span data-ttu-id="aafd9-122">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="aafd9-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="aafd9-123">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="aafd9-123">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="aafd9-124">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="aafd9-124">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="aafd9-125">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="aafd9-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="aafd9-126">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="aafd9-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="aafd9-127">Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="aafd9-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="aafd9-128">Attivazione o disattivazione della messaggistica offline</span><span class="sxs-lookup"><span data-stu-id="aafd9-128">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="aafd9-129">I messaggi offline sono disponibili **solo** nella versione più recente del client Skype for business a portata di clic e non sono disponibili quando viene usato un file \*. msi o un vecchio click-to-Run per installare il client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="aafd9-129">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="aafd9-130">Per abilitare o disabilitare i messaggi offline, inviare messaggi offline per gli utenti dell'organizzazione __ , impostare `True` EnableIMAutoArchiving `False`su or.</span><span class="sxs-lookup"><span data-stu-id="aafd9-130">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="aafd9-131">Per impostazione predefinita, questa opzione è `True`impostata su.</span><span class="sxs-lookup"><span data-stu-id="aafd9-131">By default, this is set to `True`.</span></span>

<span data-ttu-id="aafd9-132">Per disattivarli, utilizzare il cmdlet **Set-CsClientPolicy** ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="aafd9-132">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="aafd9-133">Per abilitare o disabilitare i messaggi offline, inviare messaggi offline per un utente __ , impostare `True` EnableIMAutoArchiving `False`su or.</span><span class="sxs-lookup"><span data-stu-id="aafd9-133">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="aafd9-134">Per impostazione predefinita, è impostato su  `True`.</span><span class="sxs-lookup"><span data-stu-id="aafd9-134">By default, this is set to  `True`.</span></span> <span data-ttu-id="aafd9-135">Puoi usare un criterio esistente o crearne uno simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="aafd9-135">You can use an existing policy or create one like the example below.</span></span>


  ```
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="aafd9-136">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aafd9-136">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="aafd9-137">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="aafd9-137">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="aafd9-138">È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="aafd9-138">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="aafd9-139">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="aafd9-139">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="aafd9-140">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="aafd9-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="aafd9-141">Sei motivi per cui potresti voler usare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="aafd9-141">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="aafd9-142">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="aafd9-142">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="aafd9-143">Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="aafd9-143">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="aafd9-144">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="aafd9-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="aafd9-145">Usare Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="aafd9-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="aafd9-146">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="aafd9-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="aafd9-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="aafd9-147">Related topics</span></span>
[<span data-ttu-id="aafd9-148">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="aafd9-148">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="aafd9-149">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="aafd9-149">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


