---
title: Reimpostare un ID conferenza per un utente
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: 395b1f2d9813c5ef99102c5c50ed7fff884dc594
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="9d0e5-103">Reimpostare un ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="9d0e5-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="9d0e5-104">Un ID conferenza dinamica è incluso nella parte inferiore dell'insieme ai numeri di telefono di accesso esterno che possono essere utilizzati per i chiamanti per chiamare una riunione convocazioni di riunione.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="9d0e5-105">Quando l'utente digita il numero di telefono, l'operatore automatico per la riunione verrà chiedere al chiamante di immettere l'ID conferenza in modo che è possibile partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d0e5-106">Se il provider di servizi di conferenza Microsoft, ID conferenza degli utenti è impostato su dinamico solo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="9d0e5-107">Non è purtroppo, non è possibile modificare in Skype per Business Admin Center o utilizzando Windows Powershell di diventare statico, come questa è ora supportato.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-107">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span>
<span data-ttu-id="9d0e5-108">ID conferenza vengono impostate automaticamente solo solo per Skype per utenti Business e Teams Microsoft abilitato per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-108">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing.</span></span> 
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="9d0e5-109">Reimpostare l'ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="9d0e5-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="9d0e5-110">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="9d0e5-110">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9d0e5-111">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-111">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="9d0e5-112">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-112">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="9d0e5-113">Fare clic sul menu accanto a **Ponti di conferenza**e quindi fare clic su **Reimposta id conferenza** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-113">Click the menu next to **Conference Bridges**, and then click **Reset conference id** in the drop-down list.</span></span>

2. <span data-ttu-id="9d0e5-114">Nella finestra di **reimpostare id conferenza** , fare clic su **Ok**.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-114">In the **Reset conference id** window, click **Ok**.</span></span> <span data-ttu-id="9d0e5-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="9d0e5-116">Per impostazione predefinita, messaggi di posta elettronica inviati a utenti, ma si possono essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-116">By default, emails are sent to users, but this can be turned off.</span></span>   

<span data-ttu-id="9d0e5-117">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="9d0e5-117">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="9d0e5-118">In **Skype per interfaccia di amministrazione di Business**, fare clic su **servizi di conferenza Audio** > **gli utenti**, selezionare un utente e quindi nel riquadro azioni in **ID conferenza** fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-118">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="9d0e5-119">Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-119">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="9d0e5-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="9d0e5-121">Per impostazione predefinita, messaggi di posta elettronica inviati a utenti, ma si possono essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-121">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9d0e5-p105">Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio viene inviato all'indirizzo e-mail principale, che, in molti casi, corrisponde alla cassetta postale di Office 365. Nell'e-mail è contenuto il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso esterno e alcune istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business, che consente di aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-p105">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="9d0e5-125">Quali altre informazioni sono necessarie?</span><span class="sxs-lookup"><span data-stu-id="9d0e5-125">What else should I know?</span></span>

- <span data-ttu-id="9d0e5-126">È possibile inviare tutte le informazioni di servizi di conferenza per utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono di accesso esterno facendo clic su **Invia informazioni conferenza tramite posta elettronica** dell'utente nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-126">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="9d0e5-127">Il PIN non è incluso.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-127">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="9d0e5-128">Un ID conferenza conterrà 7 cifre e non è possibile modificare la lunghezza in Skype for Business admin center o utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-128">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="9d0e5-129">Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-129">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="9d0e5-130">L'ID conferenza per un utente per le conferenze audio può essere visualizzato nella parte inferiore del riquadro delle azioni in **servizi di conferenza Audio** quando si seleziona l'utente nella pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="9d0e5-130">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="9d0e5-131">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="9d0e5-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="9d0e5-133">Gli utenti possono utilizzare Skype per strumento riunione Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="9d0e5-133">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="9d0e5-134">Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere:</span><span class="sxs-lookup"><span data-stu-id="9d0e5-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="9d0e5-135">Meeting Update Tool per Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="9d0e5-135">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="9d0e5-136">Skype for Business online, strumento di migrazione delle riunioni (64 bit)</span><span class="sxs-lookup"><span data-stu-id="9d0e5-136">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="9d0e5-137">Skype for Business online, strumento di migrazione delle riunioni (32 bit)</span><span class="sxs-lookup"><span data-stu-id="9d0e5-137">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9d0e5-138">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9d0e5-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="9d0e5-p108">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="9d0e5-p108">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9d0e5-142">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9d0e5-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="9d0e5-143">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="9d0e5-143">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="9d0e5-p109">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d0e5-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="9d0e5-146">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="9d0e5-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="9d0e5-147">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9d0e5-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9d0e5-148">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9d0e5-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="9d0e5-149">See also</span><span class="sxs-lookup"><span data-stu-id="9d0e5-149">Related topics</span></span>

[<span data-ttu-id="9d0e5-150">Reimpostare il PIN per conferenze Audio</span><span class="sxs-lookup"><span data-stu-id="9d0e5-150">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
