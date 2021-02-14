---
title: Delega messaggi
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Informazioni su come un utente con stato Non al computer o Non disturbare può impostare esplicitamente un altro utente come delegato nel messaggio di stato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790468"
---
# <a name="message-delegation"></a><span data-ttu-id="46d2c-103">Delega messaggi</span><span class="sxs-lookup"><span data-stu-id="46d2c-103">Message delegation</span></span>

<span data-ttu-id="46d2c-104">Un utente può già impostare esplicitamente il proprio stato su Non al computer o Non disturbare e fornire testo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="46d2c-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="46d2c-105">La caratteristica di delega dei messaggi funziona come segue:</span><span class="sxs-lookup"><span data-stu-id="46d2c-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="46d2c-106">Un utente @username menziona un altro utente in una parte di un MESSAGGIO di stato di testo, suggerendo che, anche se non è disponibile, le persone che vogliono contattarlo contattano l'utente menzionato @username contatto.</span><span class="sxs-lookup"><span data-stu-id="46d2c-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="46d2c-107">Alla persona a cui è stato assegnato il ruolo di delegato viene notificato che è stata nominata come delegato.</span><span class="sxs-lookup"><span data-stu-id="46d2c-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="46d2c-108">Qualcuno che tenta di contattare il primo utente può quindi passare il mouse sul delegato proposto e inviare facilmente un messaggio al delegato.</span><span class="sxs-lookup"><span data-stu-id="46d2c-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="46d2c-109">Si tratta di un processo avviato dall'utente nel client e per abilitare la caratteristica non è richiesto alcun coinvolgimento dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="46d2c-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="46d2c-110">Scenario di utilizzo della delega nel settore sanitario</span><span class="sxs-lookup"><span data-stu-id="46d2c-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="46d2c-111">*Esempio di utilizzo senza impostare delegati:*  Il dott. Franco Piccio è al telefono presso il reparto di radiology.</span><span class="sxs-lookup"><span data-stu-id="46d2c-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="46d2c-112">Riceve una chiamata personale urgente e deve allontanarsi per un paio d'ore.</span><span class="sxs-lookup"><span data-stu-id="46d2c-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="46d2c-113">Chiede a uno dei suoi colleghi del reparto radiologico, la dott. Lena Ehrle, di coprirlo mentre è fuori ufficio.</span><span class="sxs-lookup"><span data-stu-id="46d2c-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="46d2c-114">In modo informale, porta il suo pager al dott. Ehrle, che ascolta i messaggi urgenti e effettua un ping sul pager e risponde per conto del dott. Piccio, oltre alle sue attuali responsabilità.</span><span class="sxs-lookup"><span data-stu-id="46d2c-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="46d2c-115">Altri membri del team potrebbero non rendersi conto dell'avvenuta delega informale e si verifica confusione con le cure di un paziente.</span><span class="sxs-lookup"><span data-stu-id="46d2c-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="46d2c-116">*Esempio di utilizzo con l'impostazione di delegati:* Il dott. Franco Piccio è al telefono presso il reparto di radiology.</span><span class="sxs-lookup"><span data-stu-id="46d2c-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="46d2c-117">Riceve una chiamata personale urgente e deve allontanarsi per un paio d'ore.</span><span class="sxs-lookup"><span data-stu-id="46d2c-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="46d2c-118">Chiede a uno dei suoi colleghi del reparto radiologico, la dott. Lena Ehrle di coprirlo mentre è fuori ufficio.</span><span class="sxs-lookup"><span data-stu-id="46d2c-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="46d2c-119">Modifica il suo messaggio di stato personalizzato in modo che sia simile a "Non sono disponibile per le prossime ore.</span><span class="sxs-lookup"><span data-stu-id="46d2c-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="46d2c-120">Contatta il @DrEhrle per eventuali emergenze".</span><span class="sxs-lookup"><span data-stu-id="46d2c-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="46d2c-121">Altri membri del team hanno realizzato che la delega è avvenuta mentre provano a contattare il dott. Piccio, quindi ora sanno di contattare il dott. Ehrle nel frattempo.</span><span class="sxs-lookup"><span data-stu-id="46d2c-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="46d2c-122">L'assistenza di un paziente non crea confusione.</span><span class="sxs-lookup"><span data-stu-id="46d2c-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="46d2c-123">Impatto delle modalità di coesistenza sullo stato dell'utente nel client Teams</span><span class="sxs-lookup"><span data-stu-id="46d2c-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="46d2c-124">Gli amministratori devono tenere presente che le note di stato e i comportamenti di menzione della delega dipendono in parte dalla modalità di coesistenza di un utente.</span><span class="sxs-lookup"><span data-stu-id="46d2c-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="46d2c-125">Questa matrice mostra le possibilità:</span><span class="sxs-lookup"><span data-stu-id="46d2c-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="46d2c-126">Co-Existence automatica</span><span class="sxs-lookup"><span data-stu-id="46d2c-126">Co-Existence Mode</span></span> | <span data-ttu-id="46d2c-127">Comportamento previsto</span><span class="sxs-lookup"><span data-stu-id="46d2c-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="46d2c-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="46d2c-128">TeamsOnly</span></span> |<span data-ttu-id="46d2c-129">Gli utenti possono impostare una nota solo da Teams.</span><span class="sxs-lookup"><span data-stu-id="46d2c-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="46d2c-130">La nota di Teams dell'utente è visibile in Teams & SfB.</span><span class="sxs-lookup"><span data-stu-id="46d2c-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="46d2c-131">Isole</span><span class="sxs-lookup"><span data-stu-id="46d2c-131">Islands</span></span> | <span data-ttu-id="46d2c-132">Nota dell'utente impostata in Teams visibile solo in Teams.</span><span class="sxs-lookup"><span data-stu-id="46d2c-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="46d2c-133">Set di note dell'utente in SfB visibile solo in SfB</span><span class="sxs-lookup"><span data-stu-id="46d2c-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="46d2c-134">Modalità SfB\*</span><span class="sxs-lookup"><span data-stu-id="46d2c-134">SfB\* modes</span></span> | <span data-ttu-id="46d2c-135">Gli utenti possono impostare una nota solo da SfB.</span><span class="sxs-lookup"><span data-stu-id="46d2c-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="46d2c-136">La nota SfB dell'utente è visibile in SfB & Teams.</span><span class="sxs-lookup"><span data-stu-id="46d2c-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="46d2c-137">Un utente può impostare una nota in Teams solo se la modalità è TeamsOnly o Islands.</span><span class="sxs-lookup"><span data-stu-id="46d2c-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="46d2c-138">Visualizzazione di note impostate in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="46d2c-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="46d2c-139">Non c'è alcuna indicazione visiva che una nota sia stata impostata da Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="46d2c-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="46d2c-140">Skype for Business non applica un limite di caratteri alle note sullo stato.</span><span class="sxs-lookup"><span data-stu-id="46d2c-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="46d2c-141">Microsoft Teams visualizza solo i primi 280 caratteri di un set di note di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="46d2c-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="46d2c-142">Un puntoni di sospensione (...) alla fine di una nota indica il troncamento.</span><span class="sxs-lookup"><span data-stu-id="46d2c-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="46d2c-143">Skype for Business non supporta le ore di scadenza per le note.</span><span class="sxs-lookup"><span data-stu-id="46d2c-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="46d2c-144">La migrazione delle note da Skype for Business a Teams non è supportata quando un utente viene aggiornato alla modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="46d2c-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="46d2c-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="46d2c-145">Related topics</span></span>

[<span data-ttu-id="46d2c-146">Coesistenza con Skype for Business</span><span class="sxs-lookup"><span data-stu-id="46d2c-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
