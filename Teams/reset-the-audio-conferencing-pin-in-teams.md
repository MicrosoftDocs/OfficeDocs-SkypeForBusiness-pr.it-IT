---
title: Reimpostare il PIN di audioconferenza in Microsoft Teams
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
description: Informazioni su come reimpostare il PIN di audioconferenza di un utente in Microsoft Teams informazioni importanti sui PIN.
ms.openlocfilehash: 6470085fed25a83c1a8dc46ab45e8c6ea57b5603
ms.sourcegitcommit: a07040d1527692b4dbde7bd2c21994377ad0a92e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114025"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="4157f-103">Reimpostare il PIN di audioconferenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4157f-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="4157f-104">Un PIN è un codice costituito da numeri creati per ogni utente Microsoft Teams abilitato per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="4157f-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="4157f-105">I PIN di audioconferenza vengono usati dagli organizzatori della riunione per identificare che sono l'organizzatore della riunione e consentire loro di avviare una riunione tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="4157f-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="4157f-106">Se usano l'app Microsoft Teams per avviare la riunione, non è necessario un PIN.</span><span class="sxs-lookup"><span data-stu-id="4157f-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="4157f-107">Se gli utenti dimenticano il PIN e non lo trovano nel messaggio di posta elettronica inviato quando sono stati abilitati per le audioconferenze, un amministratore può reimpostare il PIN oppure reimpostare il PROPRIO PIN.</span><span class="sxs-lookup"><span data-stu-id="4157f-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="4157f-108">Le riunioni possono essere avviate quando un utente autenticato partecipa usando l'app Microsoft Teams o quando l'organizzatore partecipa con il PIN tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="4157f-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with their PIN over the phone.</span></span> <span data-ttu-id="4157f-109">Quando una riunione richiede l'avvio di un PIN, gli utenti che aderiscono al telefono vengono inseriti nella sala d'attesa e ascoltano la musica in attesa finché l'organizzatore non lo ammette.</span><span class="sxs-lookup"><span data-stu-id="4157f-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the organizer admits them.</span></span> <span data-ttu-id="4157f-110">Se l'organizzatore di una riunione non richiede il PIN per avviare la riunione tramite telefono, quando un chiamante tenta di partecipare alla riunione, non dovrà specificare un PIN.</span><span class="sxs-lookup"><span data-stu-id="4157f-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="4157f-111">Reimpostare il PIN dell'utente</span><span class="sxs-lookup"><span data-stu-id="4157f-111">Reset a user's PIN</span></span>

<span data-ttu-id="4157f-112">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="4157f-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4157f-113">Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="4157f-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4157f-114">Fare clic **su Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4157f-114">Click **Edit**.</span></span>

3. <span data-ttu-id="4157f-115">In **Audioconferenza** fare clic **su Reimposta PIN.**</span><span class="sxs-lookup"><span data-stu-id="4157f-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="4157f-116">Fare clic **su Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="4157f-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a><span data-ttu-id="4157f-117">Fare in modo che un utente resetti il proprio PIN</span><span class="sxs-lookup"><span data-stu-id="4157f-117">Have a user reset their own PIN</span></span>

1. <span data-ttu-id="4157f-118">Fare in modo che l'utente vada a [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .</span><span class="sxs-lookup"><span data-stu-id="4157f-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="4157f-119">Fare clic **su Reimposta PIN**.</span><span class="sxs-lookup"><span data-stu-id="4157f-119">Click **Reset PIN**.</span></span> 

> [!NOTE]
> <span data-ttu-id="4157f-120">Per GCCH, vai a: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing .</span><span class="sxs-lookup"><span data-stu-id="4157f-120">For GCCH go to: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing.</span></span>

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="4157f-121">Quali sono le altre informazioni utili sul PIN?</span><span class="sxs-lookup"><span data-stu-id="4157f-121">What else should you know about PINs?</span></span>

- <span data-ttu-id="4157f-122">Per motivi di sicurezza, il PIN viene visualizzato una sola volta all'amministratore, quando il PIN viene reimpostato.</span><span class="sxs-lookup"><span data-stu-id="4157f-122">For security purposes, the PIN is only shown to an administrator one time, when the PIN is reset.</span></span> <span data-ttu-id="4157f-123">Dopo la reimpostazione del PIN da parte di un amministratore, il PIN verrà elencato come \*\*\*\*\*\*\*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="4157f-123">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="4157f-124">L'invio automatico di messaggi di posta elettronica agli utenti è abilitato per impostazione predefinita e gli utenti riceveranno un messaggio di posta elettronica con il PIN quando sono abilitati per le audioconferenze o quando il PIN viene reimpostato.</span><span class="sxs-lookup"><span data-stu-id="4157f-124">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="4157f-125">Se tuttavia l'invio automatico dei messaggi di posta elettronica è stato disabilitato, non verrà inviato un messaggio di posta elettronica di reimpostazione del PIN a un utente e sarà necessario inviare manualmente le informazioni sul PIN all'utente.</span><span class="sxs-lookup"><span data-stu-id="4157f-125">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="4157f-126">All'avvio di una riunione, l'organizzatore deve ammettere tutti gli utenti PSTN nella sala d'attesa per partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="4157f-126">When a meeting starts, the organizer needs to admit all PSTN users in the lobby to join the meeting.</span></span> <span data-ttu-id="4157f-127">Ad esempio, se due partecipanti PSTN provano a partecipare a una riunione prima dell'inizio, vengono messi nella sala d'attesa e ascoltano la musica in attesa e quando l'organizzatore della riunione partecipa usando il PIN tramite telefono, la riunione verrà avviata e l'organizzatore potrà usare il comando in riunione (premere \*21) per ammettere tutti gli utenti PSTN nella sala d'attesa.</span><span class="sxs-lookup"><span data-stu-id="4157f-127">For example, if two PSTN participants try to join a meeting before it has started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using their PIN via phone, the meeting will start and the organizer can use the in-meeting command (press \*21) to admit all PSTN users in the lobby.</span></span>
    
- <span data-ttu-id="4157f-128">L'impostazione predefinita è non consentire l'avvio di una riunione da parte di chiamanti anonimi.</span><span class="sxs-lookup"><span data-stu-id="4157f-128">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="4157f-129">Quando si abilita un utente per le audioconferenze, per impostazione predefinita vengono inviati messaggi di posta elettronica che includono le informazioni di conferenza e il PIN.</span><span class="sxs-lookup"><span data-stu-id="4157f-129">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="4157f-130">L'utente deve avere una cassetta postale di Microsoft 365 o Office 365, perché quando viene reimpostato un PIN, all'utente verrà inviato un nuovo PIN tramite posta elettronica all'indirizzo SMTP principale (alias) impostato per l'utente.</span><span class="sxs-lookup"><span data-stu-id="4157f-130">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="4157f-131">Quando si imposta una audioconferenza, impostare le cifre necessari per il PIN nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4157f-131">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="4157f-132">I PIN possono essere da 4 a 12 cifre, il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="4157f-132">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="4157f-133">Se si modifica l'impostazione della lunghezza del PIN, l'impostazione viene applicata solo sui PIN generati successivamente e non viene applicata per l'impostazione del PIN degli utenti precedetemente abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="4157f-133">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="4157f-134">Vedere [impostare la lunghezza del PIN per le riunioni in audioconferenze](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4157f-134">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="4157f-135">Per impostazione predefinita, il messaggio di posta elettronica verrà Microsoft 365 o Office 365'indirizzo SMTP principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4157f-135">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="4157f-136">È possibile inviare un messaggio di posta elettronica a un indirizzo di posta elettronica non Microsoft 365 o non Office 365, ad esempio un indirizzo di posta elettronica Hotmail o MSN.</span><span class="sxs-lookup"><span data-stu-id="4157f-136">You can send an email to a non-Microsoft 365 or non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="4157f-137">È possibile sostituire l'indirizzo di posta elettronica predefinito tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4157f-137">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="4157f-138">Questa opzione è utile se gli utenti non hanno una cassetta postale Exchange in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="4157f-138">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4157f-139">Vuoi saperne di più su Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4157f-139">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4157f-140">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="4157f-140">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4157f-141">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="4157f-141">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="4157f-142">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4157f-142">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4157f-143">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="4157f-143">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="4157f-144">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="4157f-144">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="4157f-145">Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="4157f-145">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4157f-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4157f-146">Related topics</span></span>

[<span data-ttu-id="4157f-147">Reimpostare un ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="4157f-147">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
