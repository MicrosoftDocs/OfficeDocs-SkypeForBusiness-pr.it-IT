---
title: Reimpostare un ID conferenza per un utente in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: "Informazioni sulla procedura per reimpostare l'ID conferenza di una riunione di un utente in Skype for Business online e ottenere collegamenti agli strumenti di aggiornamento e migrazione delle riunioni. "
ms.openlocfilehash: 424b0dfb24d6034af20c18a0172221a09bef5ecd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114212"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="9ca92-103">Reimpostare un ID conferenza per un utente in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="9ca92-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="9ca92-104">Per informazioni sulla reimpostazione di un ID conferenza su Microsoft Teams, consulta [Reimpostare un ID conferenza per un utente su Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="9ca92-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="9ca92-105">Un ID conferenza dinamico è incluso nella parte inferiore degli inviti alle riunioni insieme ai numeri di telefono di accesso esterno che possono essere usati dai chiamanti per accedere a una riunione.</span><span class="sxs-lookup"><span data-stu-id="9ca92-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="9ca92-106">Quando l'utente compone il numero di telefono, l'operatore automatico della riunione chiederà al chiamante di immettere questo ID conferenza in modo che possa partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="9ca92-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ca92-107">Se il provider di conferenza è Microsoft, gli ID conferenza degli utenti sono impostati su Solo dinamico.</span><span class="sxs-lookup"><span data-stu-id="9ca92-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="9ca92-108">Non è possibile modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="9ca92-108">This cannot be changed.</span></span> <span data-ttu-id="9ca92-109">Gli ID conferenza vengono impostati automaticamente solo per gli utenti di Skype for Business abilitati per Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="9ca92-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="9ca92-110">Reimpostazione dell'ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="9ca92-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="9ca92-111">**Nell'interfaccia di amministrazione di Skype for Business** fare clic su Utenti di **audioconferenza,** selezionare un utente e quindi nel riquadro Azioni in ID conferenza fare clic su  >   **Reimposta.** </span><span class="sxs-lookup"><span data-stu-id="9ca92-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="9ca92-112">Nella finestra **Reimposta ID conferenza?** fare clic su **Sì.**</span><span class="sxs-lookup"><span data-stu-id="9ca92-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="9ca92-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="9ca92-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="9ca92-114">Per impostazione predefinita, i messaggi di posta elettronica vengono inviati agli utenti, ma possono essere disattivati.</span><span class="sxs-lookup"><span data-stu-id="9ca92-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9ca92-115">Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="9ca92-115">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="9ca92-116">Questo messaggio di posta elettronica verrà inviato all'indirizzo di posta elettronica principale, in molti casi, alla cassetta postale di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ca92-116">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="9ca92-117">Nell'e-mail è contenuto il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso esterno e alcune istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business, che consente di aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="9ca92-117">The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="9ca92-118">Quali altre informazioni sono necessarie?</span><span class="sxs-lookup"><span data-stu-id="9ca92-118">What else should I know?</span></span>

- <span data-ttu-id="9ca92-119">È possibile inviare tutte le informazioni di conferenza all'utente in un messaggio  di posta elettronica che include l'ID conferenza e i numeri di telefono per l'accesso esterno facendo clic su Invia informazioni conferenza tramite posta elettronica per l'utente nel riquadro Azioni.</span><span class="sxs-lookup"><span data-stu-id="9ca92-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="9ca92-120">Il PIN non è incluso.</span><span class="sxs-lookup"><span data-stu-id="9ca92-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="9ca92-121">Un ID conferenza conterrà 7 cifre e non è possibile modificarne la lunghezza nell'interfaccia di amministrazione di Skype for Business o usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ca92-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="9ca92-122">Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="9ca92-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="9ca92-123">L'ID conferenza di un utente per le audioconferenze può essere visualizzato nella parte inferiore del riquadro Azioni in **Audioconferenza** quando si seleziona l'utente nella **pagina** Utenti.</span><span class="sxs-lookup"><span data-stu-id="9ca92-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="9ca92-124">Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="9ca92-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="9ca92-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="9ca92-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="9ca92-126">Gli utenti possono usare lo strumento riunione Skype for Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="9ca92-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="9ca92-127">Per informazioni su come scaricare, installare ed eseguire lo strumento di aggiornamento delle riunioni Skype for Business, vedi:</span><span class="sxs-lookup"><span data-stu-id="9ca92-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="9ca92-128">Meeting Update Tool per Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="9ca92-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="9ca92-129">Skype for Business online, strumento di migrazione delle riunioni (64 bit)</span><span class="sxs-lookup"><span data-stu-id="9ca92-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="9ca92-130">Skype for Business online, strumento di migrazione delle riunioni (32 bit)</span><span class="sxs-lookup"><span data-stu-id="9ca92-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9ca92-131">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9ca92-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="9ca92-132">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="9ca92-132">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9ca92-133">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business online con un unico punto di amministrazione che può semplificare il lavoro quotidiano, quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="9ca92-133">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9ca92-134">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="9ca92-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9ca92-135">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9ca92-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="9ca92-136">Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9ca92-136">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- <span data-ttu-id="9ca92-137">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9ca92-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9ca92-138">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9ca92-138">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="9ca92-139">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9ca92-139">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="9ca92-140">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="9ca92-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="9ca92-141">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="9ca92-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="9ca92-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9ca92-142">Related topics</span></span>

[<span data-ttu-id="9ca92-143">Reimpostare il PIN di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="9ca92-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)