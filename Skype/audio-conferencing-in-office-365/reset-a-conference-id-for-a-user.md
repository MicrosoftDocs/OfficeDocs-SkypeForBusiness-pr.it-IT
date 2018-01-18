---
title: Reimpostare un ID conferenza per un utente
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn the steps to reset a user''s meeting conference ID, and get links to meeting update and migration tools. '
ms.openlocfilehash: 2f2cbd6efa61e05defb17ef05f86fd9a228987ac
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="ee0f7-103">Reimpostare un ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="ee0f7-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="ee0f7-104">Quando le organizzazioni non è stato abilitato per gli ID conferenza dinamico, un ID conferenza statica viene creato automaticamente quando Skype per utenti Business o Microsoft Teams è abilitata per le conferenze Audio tramite Microsoft come provider.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-104">When your organizations hasn't been enabled for dynamic conference IDs, a static conference ID is automatically created when a Skype for Business or Microsoft Teams user is enabled for Audio Conferencing using Microsoft as the provider.</span></span> <span data-ttu-id="ee0f7-105">Questo ID conferenza è incluso nella parte inferiore dell'insieme ai numeri di telefono di accesso esterno che possono essere utilizzati per i chiamanti per chiamare una riunione convocazioni di riunione.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-105">This conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="ee0f7-106">Quando l'utente digita il numero di telefono, l'operatore automatico per la riunione verrà chiedere al chiamante di immettere l'ID conferenza in modo che è possibile partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ee0f7-107">Se il provider di servizi di conferenza Microsoft, ID conferenza degli utenti è impostato su dinamico solo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="ee0f7-108">Purtroppo, non sarà possibile modificare in Skype per Business Admin Center o utilizzando Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-108">Unfortunately, you won't be able to change it in the Skype for Business Admin Center or using Windows Powershell.</span></span> <span data-ttu-id="ee0f7-109">È necessario contattare il supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-109">You will have to contact Microsoft support.</span></span> 
  
<span data-ttu-id="ee0f7-110">ID statico vengono utilizzati quando gli utenti dell'organizzazione non desiderano Memorizza numero casuale; possono selezionare un determinato numero o utilizzare una facile da ricordare.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-110">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="ee0f7-111">Quando vengono utilizzati gli ID conferenza dinamico, ogni riunione pianificazioni un utente verranno ottenere assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-111">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="ee0f7-112">Se si desidera assegnare dinamico anziché gli ID, [fare clic qui](using-audio-conferencing-dynamic-ids-in-your-organization.md)di conferenza statico.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-112">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="ee0f7-113">ID conferenza vengono impostate automaticamente solo solo per Skype per utenti Business e Microsoft Teams abilitato per le conferenze Audio tramite Microsoft come i provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-113">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing using Microsoft as their audio conferencing provider.</span></span> <span data-ttu-id="ee0f7-114">Se è necessario reimpostare un ID conferenza per un utente che utilizza un provider di servizi di conferenza audio di terze parti (ACP), sarà necessario immettere manualmente un ID conferenza nella pagina delle proprietà dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-114">If you need to reset a conference ID for a user who is using a third-party audio conferencing provider (ACP), you will need to manually enter a conference ID on the properties page for the user.</span></span>
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="ee0f7-115">Reimpostare l'ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="ee0f7-115">Resetting the conference ID for a user</span></span>

1. <span data-ttu-id="ee0f7-116">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="ee0f7-117">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="ee0f7-118">In **Skype per interfaccia di amministrazione di Business**, fare clic su **servizi di conferenza Audio** > **gli utenti**, selezionare un utente e quindi nel riquadro azioni in **ID conferenza** fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-118">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
4. <span data-ttu-id="ee0f7-119">Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-119">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="ee0f7-120">Una conferenza che ID verrà automaticamente creato e un messaggio di posta elettronica inviati all'utente con il nuovo ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="ee0f7-121">Per impostazione predefinita, messaggi di posta elettronica inviati a utenti, ma si possono essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-121">By default, emails are sent to users, but this can be turned off.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ee0f7-p106">Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio viene inviato all'indirizzo e-mail principale, che, in molti casi, corrisponde alla cassetta postale di Office 365. Nell'e-mail è contenuto il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso esterno e alcune istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business, che consente di aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-p106">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="ee0f7-125">Quali altre informazioni sono necessarie?</span><span class="sxs-lookup"><span data-stu-id="ee0f7-125">What else should I know?</span></span>

- <span data-ttu-id="ee0f7-126">È possibile inviare tutte le informazioni di servizi di conferenza per utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono di accesso esterno facendo clic su **Invia informazioni conferenza tramite posta elettronica** dell'utente nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-126">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="ee0f7-127">Non invia il PIN.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-127">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="ee0f7-128">Un ID conferenza conterrà 7 cifre e non è possibile modificare la lunghezza in Skype for Business admin center o utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-128">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="ee0f7-129">Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-129">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="ee0f7-130">L'ID conferenza per un utente per le conferenze audio può essere visualizzato nella parte inferiore del riquadro delle azioni in **servizi di conferenza Audio** quando si seleziona l'utente nella pagina **utenti** .</span><span class="sxs-lookup"><span data-stu-id="ee0f7-130">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="ee0f7-131">Dopo aver creato un nuovo ID conferenza, l'ID conferenza precedente non può essere utilizzato per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="ee0f7-132">È necessario avvisare gli utenti di pianificare di nuovo le riunioni gli inviti per verificare che la nuova conferenza che ID viene aggiunto a inviti esistente.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="ee0f7-133">Gli utenti possono utilizzare Skype per strumento riunione Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-133">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="ee0f7-134">Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere:</span><span class="sxs-lookup"><span data-stu-id="ee0f7-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="ee0f7-135">Meeting Update Tool per Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="ee0f7-135">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="ee0f7-136">Skype for Business online, strumento di migrazione delle riunioni (64 bit)</span><span class="sxs-lookup"><span data-stu-id="ee0f7-136">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="ee0f7-137">Skype for Business online, strumento di migrazione delle riunioni (32 bit)</span><span class="sxs-lookup"><span data-stu-id="ee0f7-137">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ee0f7-138">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ee0f7-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ee0f7-p109">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="ee0f7-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ee0f7-142">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ee0f7-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ee0f7-143">Perché è necessario utilizzare Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee0f7-143">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ee0f7-p110">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee0f7-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ee0f7-146">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="ee0f7-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ee0f7-147">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ee0f7-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ee0f7-148">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ee0f7-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ee0f7-149">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ee0f7-149">Related topics</span></span>

[<span data-ttu-id="ee0f7-150">Reimpostare il PIN di conferenza Audio di un utente</span><span class="sxs-lookup"><span data-stu-id="ee0f7-150">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin-for-a-user.md)
