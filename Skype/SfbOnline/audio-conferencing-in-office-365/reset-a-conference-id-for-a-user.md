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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: 077b35169b3829262c38c9ebc44451aba8bd110d
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="bb308-103">Reimpostare un ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="bb308-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="bb308-104">Quando le organizzazioni non è stato abilitato per gli ID conferenza dinamico, un ID conferenza statica viene creato automaticamente quando Skype per utenti Business o Microsoft Teams è abilitata per le conferenze Audio tramite Microsoft come provider.</span><span class="sxs-lookup"><span data-stu-id="bb308-104">When your organizations hasn't been enabled for dynamic conference IDs, a static conference ID is automatically created when a Skype for Business or Microsoft Teams user is enabled for Audio Conferencing using Microsoft as the provider.</span></span> <span data-ttu-id="bb308-105">Questo ID conferenza è incluso nella parte inferiore dell'insieme ai numeri di telefono di accesso esterno che possono essere utilizzati per i chiamanti per chiamare una riunione convocazioni di riunione.</span><span class="sxs-lookup"><span data-stu-id="bb308-105">This conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="bb308-106">Quando l'utente digita il numero di telefono, l'operatore automatico per la riunione verrà chiedere al chiamante di immettere l'ID conferenza in modo che è possibile partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="bb308-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb308-107">Se il provider di servizi di conferenza Microsoft, ID conferenza degli utenti è impostato su dinamico solo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bb308-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="bb308-108">Purtroppo, non sarà possibile modificare in Skype per Business Admin Center o utilizzando Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="bb308-108">Unfortunately, you won't be able to change it in the Skype for Business Admin Center or using Windows Powershell.</span></span> <span data-ttu-id="bb308-109">È necessario contattare il supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bb308-109">You will have to contact Microsoft support.</span></span> 
  
<span data-ttu-id="bb308-110">ID statico vengono utilizzati quando gli utenti dell'organizzazione non desiderano Memorizza numero casuale; possono selezionare un determinato numero o utilizzare una facile da ricordare.</span><span class="sxs-lookup"><span data-stu-id="bb308-110">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="bb308-111">Quando vengono utilizzati gli ID conferenza dinamico, ogni riunione pianificazioni un utente verranno ottenere assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="bb308-111">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="bb308-112">Se si desidera assegnare dinamico anziché gli ID, [fare clic qui](using-audio-conferencing-dynamic-ids-in-your-organization.md)di conferenza statico.</span><span class="sxs-lookup"><span data-stu-id="bb308-112">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="bb308-113">ID conferenza vengono impostate automaticamente solo solo per Skype per utenti Business e Microsoft Teams abilitato per le conferenze Audio tramite Microsoft come i provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="bb308-113">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing using Microsoft as their audio conferencing provider.</span></span> <span data-ttu-id="bb308-114">Se è necessario reimpostare un ID conferenza per un utente che utilizza un provider di servizi di conferenza audio di terze parti (ACP), sarà necessario immettere manualmente un ID conferenza nella pagina delle proprietà dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bb308-114">If you need to reset a conference ID for a user who is using a third-party audio conferencing provider (ACP), you will need to manually enter a conference ID on the properties page for the user.</span></span>
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="bb308-115">Reimpostare l'ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="bb308-115">Resetting the conference ID for a user</span></span>

<span data-ttu-id="bb308-116">**Utilizzo del team di Microsoft e Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="bb308-116">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bb308-117">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="bb308-117">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="bb308-118">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="bb308-118">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="bb308-119">Fare clic sul menu accanto a **Ponti di conferenza**e quindi fare clic su **Reimposta id conferenza** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bb308-119">Click the menu next to **Conference Bridges**, and then click **Reset conference id** in the drop-down list.</span></span>

2. <span data-ttu-id="bb308-120">Nella finestra di **reimpostare id conferenza** , fare clic su **Ok**.</span><span class="sxs-lookup"><span data-stu-id="bb308-120">In the **Reset conference id** window, click **Ok**.</span></span> <span data-ttu-id="bb308-121">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="bb308-121">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="bb308-122">Per impostazione predefinita, messaggi di posta elettronica inviati a utenti, ma si possono essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="bb308-122">By default, emails are sent to users, but this can be turned off.</span></span>   

<span data-ttu-id="bb308-123">**Utilizzo di Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="bb308-123">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="bb308-124">In **Skype per interfaccia di amministrazione di Business**, fare clic su **servizi di conferenza Audio** > **gli utenti**, selezionare un utente e quindi nel riquadro azioni in **ID conferenza** fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="bb308-124">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="bb308-125">Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="bb308-125">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="bb308-126">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="bb308-126">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="bb308-127">Per impostazione predefinita, messaggi di posta elettronica inviati a utenti, ma si possono essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="bb308-127">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bb308-p107">Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio viene inviato all'indirizzo e-mail principale, che, in molti casi, corrisponde alla cassetta postale di Office 365. Nell'e-mail è contenuto il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso esterno e alcune istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business, che consente di aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="bb308-p107">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="bb308-131">Quali altre informazioni sono necessarie?</span><span class="sxs-lookup"><span data-stu-id="bb308-131">What else should I know?</span></span>

- <span data-ttu-id="bb308-132">È possibile inviare tutte le informazioni di servizi di conferenza per utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono di accesso esterno facendo clic su **Invia informazioni conferenza tramite posta elettronica** dell'utente nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="bb308-132">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="bb308-133">Il PIN non è incluso.</span><span class="sxs-lookup"><span data-stu-id="bb308-133">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="bb308-134">Un ID conferenza conterrà 7 cifre e non è possibile modificare la lunghezza in Skype for Business admin center o utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb308-134">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="bb308-135">Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="bb308-135">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="bb308-136">L'ID conferenza per un utente per le conferenze audio può essere visualizzato nella parte inferiore del riquadro delle azioni in **servizi di conferenza Audio** quando si seleziona l'utente nella pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="bb308-136">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="bb308-137">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="bb308-137">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="bb308-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="bb308-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="bb308-139">Gli utenti possono utilizzare Skype per strumento riunione Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="bb308-139">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="bb308-140">Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere:</span><span class="sxs-lookup"><span data-stu-id="bb308-140">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="bb308-141">Meeting Update Tool per Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="bb308-141">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="bb308-142">Skype for Business online, strumento di migrazione delle riunioni (64 bit)</span><span class="sxs-lookup"><span data-stu-id="bb308-142">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="bb308-143">Skype for Business online, strumento di migrazione delle riunioni (32 bit)</span><span class="sxs-lookup"><span data-stu-id="bb308-143">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="bb308-144">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bb308-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="bb308-p110">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="bb308-p110">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bb308-148">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bb308-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bb308-149">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="bb308-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="bb308-p111">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb308-p111">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="bb308-152">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="bb308-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="bb308-153">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bb308-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bb308-154">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bb308-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="bb308-155">See also</span><span class="sxs-lookup"><span data-stu-id="bb308-155">Related topics</span></span>

[<span data-ttu-id="bb308-156">Reimpostare il PIN di audioconferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="bb308-156">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin-for-a-user.md)
