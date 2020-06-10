---
title: Reimpostare il PIN di conferenza audio in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Informazioni su come reimpostare il PIN per le conferenze audio di un utente in Microsoft teams e scoprire informazioni importanti sui pin.
ms.openlocfilehash: 8926218c72c888edb00480ff8382672a3730cf15
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666188"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="b06ce-103">Reimpostare il PIN di conferenza audio in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b06ce-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="b06ce-104">Un PIN è un codice composto da numeri creati per ogni utente di Microsoft teams abilitato per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="b06ce-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="b06ce-105">I pin di conferenza audio vengono usati dagli organizzatori della riunione per identificare che sono l'organizzatore della riunione e consentire loro di avviare una riunione tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="b06ce-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="b06ce-106">Se usano l'app Microsoft teams per avviare la riunione, non è necessario un PIN.</span><span class="sxs-lookup"><span data-stu-id="b06ce-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="b06ce-107">Se gli utenti dimenticano il PIN e non riescono a trovarlo nel messaggio di posta elettronica inviato loro quando sono stati abilitati per i servizi di audioconferenza, un amministratore può reimpostare il PIN oppure può reimpostare il proprio PIN.</span><span class="sxs-lookup"><span data-stu-id="b06ce-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="b06ce-108">Le riunioni possono essere avviate quando un utente autenticato entra in contatto con l'app Microsoft teams o quando l'organizzatore si unisce al proprio PIN tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="b06ce-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="b06ce-109">Se è richiesto un PIN per avviare la riunione tramite telefono, per impostazione predefinita tutti gli utenti che partecipano alla riunione tramite telefono prima dell'inizio della riunione dovranno rimanere nella sala di attesa ascoltando musica fino all'inizio della riunione.</span><span class="sxs-lookup"><span data-stu-id="b06ce-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="b06ce-110">Se l'organizzatore di una riunione non richiede il PIN per avviare la riunione tramite telefono, quando un chiamante tenta di partecipare alla riunione, non dovrà specificare un PIN.</span><span class="sxs-lookup"><span data-stu-id="b06ce-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="b06ce-111">Reimpostare il PIN dell'utente</span><span class="sxs-lookup"><span data-stu-id="b06ce-111">Reset a user's PIN</span></span>

<span data-ttu-id="b06ce-112">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b06ce-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b06ce-113">Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="b06ce-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="b06ce-114">Fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="b06ce-114">Click **Edit**.</span></span>

3. <span data-ttu-id="b06ce-115">In **audioconferenza**fare clic su **Reimposta PIN**.</span><span class="sxs-lookup"><span data-stu-id="b06ce-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="b06ce-116">Fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="b06ce-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="b06ce-117">Reimpostazione del PIN da parte dell'utente</span><span class="sxs-lookup"><span data-stu-id="b06ce-117">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="b06ce-118">Far accedere l'utente [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .</span><span class="sxs-lookup"><span data-stu-id="b06ce-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="b06ce-119">Fare clic su **Reimposta PIN**.</span><span class="sxs-lookup"><span data-stu-id="b06ce-119">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="b06ce-120">Quali sono le altre informazioni utili sul PIN?</span><span class="sxs-lookup"><span data-stu-id="b06ce-120">What else should you know about PINs?</span></span>

- <span data-ttu-id="b06ce-121">Ai fini della sicurezza, il PIN viene visualizzato solo una volta dall'amministratore, alla reimpostazione del PIN.</span><span class="sxs-lookup"><span data-stu-id="b06ce-121">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="b06ce-122">Dopo la reimpostazione del PIN da parte di un amministratore, il PIN verrà elencato come \* \* \* \* \* \* \* \* \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="b06ce-122">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="b06ce-123">L'invio automatico di messaggi di posta elettronica agli utenti è abilitato per impostazione predefinita e gli utenti riceveranno un messaggio di posta elettronica con il PIN quando sono abilitati per i servizi di audioconferenza o quando il PIN viene reimpostato.</span><span class="sxs-lookup"><span data-stu-id="b06ce-123">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="b06ce-124">Ma se si è disabilitato l'invio automatico di messaggi di posta elettronica, un messaggio di reimpostazione del PIN non verrà inviato a un utente e sarà necessario inviare manualmente le informazioni sul PIN all'utente.</span><span class="sxs-lookup"><span data-stu-id="b06ce-124">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="b06ce-p105">Quando la riunione inizia, tutti gli utenti nella sala di attesa si uniranno automaticamente. Se ad esempio due partecipanti tentano di partecipare a una riunione prima che questa inizi, dovranno rimanere nella sala di attesa ascoltando musica e quando l'organizzatore della riunione si unirà usando il proprio PIN tramite telefono, la riunione avrà inizio e i partecipanti nella sala di attesa potranno partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="b06ce-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="b06ce-127">L'impostazione predefinita consiste nel non consentire l'avvio di una riunione da parte di chiamanti anonimi.</span><span class="sxs-lookup"><span data-stu-id="b06ce-127">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="b06ce-128">Quando si Abilita un utente per i servizi di audioconferenza, per impostazione predefinita vengono inviati messaggi di posta elettronica che includono informazioni per i servizi di conferenza e il PIN.</span><span class="sxs-lookup"><span data-stu-id="b06ce-128">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="b06ce-129">L'utente deve avere una cassetta postale di Microsoft 365 o Office 365, poiché quando viene reimpostato un PIN, un nuovo PIN verrà inviato all'utente tramite posta elettronica all'indirizzo SMTP principale (alias) impostato per l'utente.</span><span class="sxs-lookup"><span data-stu-id="b06ce-129">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="b06ce-130">Quando si imposta una audioconferenza, impostare le cifre necessari per il PIN nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b06ce-130">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="b06ce-131">I pin possono essere da 4 a 12 cifre: l'impostazione predefinita è 5.</span><span class="sxs-lookup"><span data-stu-id="b06ce-131">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="b06ce-132">Se si modifica l'impostazione della lunghezza del PIN, l'impostazione viene applicata solo sui PIN generati successivamente e non viene applicata per l'impostazione del PIN degli utenti precedetemente abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="b06ce-132">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="b06ce-133">Vedere [impostare la lunghezza del PIN per le riunioni in audioconferenze](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b06ce-133">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="b06ce-134">Per impostazione predefinita, il messaggio di posta elettronica verrà impostato sull'indirizzo SMTP principale di Microsoft 365 o Office 365 dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b06ce-134">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="b06ce-135">È possibile inviare un messaggio di posta elettronica a un indirizzo non Microsoft 365 o non Office 365, ad esempio un indirizzo di posta elettronica Hotmail o MSN.</span><span class="sxs-lookup"><span data-stu-id="b06ce-135">You can send an email to a non-Microsoft 365 or non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="b06ce-136">È possibile sostituire l'indirizzo di posta elettronica predefinito tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b06ce-136">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="b06ce-137">Questa operazione è utile se gli utenti non hanno una cassetta postale di Exchange in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="b06ce-137">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b06ce-138">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b06ce-138">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="b06ce-139">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="b06ce-139">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b06ce-140">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione in grado di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="b06ce-140">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="b06ce-141">Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="b06ce-141">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b06ce-142">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="b06ce-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b06ce-143">Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b06ce-143">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="b06ce-144">Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="b06ce-144">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b06ce-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b06ce-145">Related topics</span></span>

[<span data-ttu-id="b06ce-146">Reimpostare un ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="b06ce-146">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
