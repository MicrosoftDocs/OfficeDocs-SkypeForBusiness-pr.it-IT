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
description: Scopri come un utente con stato Assente o Non disturbare può impostare esplicitamente un altro utente come delegato nel proprio messaggio di stato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790468"
---
# <a name="message-delegation"></a><span data-ttu-id="f62e6-103">Delega messaggi</span><span class="sxs-lookup"><span data-stu-id="f62e6-103">Message delegation</span></span>

<span data-ttu-id="f62e6-104">Un utente può già impostare esplicitamente il proprio stato su Assente o Non disturbare e fornire testo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f62e6-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="f62e6-105">La funzionalità di delega dei messaggi funziona come segue:</span><span class="sxs-lookup"><span data-stu-id="f62e6-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="f62e6-106">Un utente @username menziona un altro utente in parte di un messaggio di stato di testo, indicando che mentre non sono disponibili, le persone che vogliono contattarlo invece possono contattare l'utente @username menzionato.</span><span class="sxs-lookup"><span data-stu-id="f62e6-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="f62e6-107">La persona assegnata come delegato viene informata di essere stata nominata come delegato.</span><span class="sxs-lookup"><span data-stu-id="f62e6-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="f62e6-108">Qualcuno che tenta di contattare il primo utente può quindi passare il mouse sul delegato nominato e inviare facilmente un messaggio al delegato.</span><span class="sxs-lookup"><span data-stu-id="f62e6-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="f62e6-109">Si tratta di un processo avviato dall'utente nel client e non è richiesto il coinvolgimento dell'amministratore per abilitare la funzione.</span><span class="sxs-lookup"><span data-stu-id="f62e6-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="f62e6-110">Scenario di utilizzo della delega in Healthcare</span><span class="sxs-lookup"><span data-stu-id="f62e6-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="f62e6-111">*Esempio di utilizzo senza impostazione dei delegati:*  il dott. Franco Piccio è di guardia al reparto di radiologia.</span><span class="sxs-lookup"><span data-stu-id="f62e6-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="f62e6-112">Riceve una chiamata personale urgente e deve allontanarsi per le prossime due ore.</span><span class="sxs-lookup"><span data-stu-id="f62e6-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="f62e6-113">Chiede a uno dei suoi colleghi del reparto di radiologia, la dott.ssa Lena Ehrle, di coprirlo mentre è via.</span><span class="sxs-lookup"><span data-stu-id="f62e6-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="f62e6-114">Consegna ufficiosamente il suo cercapersone alla dott.ssa Ehrle, che sta ascoltando messaggi urgenti e ping sul cercapersone e risponde a loro per conto del dott. Piccio oltre alle sue attuali responsabilità.</span><span class="sxs-lookup"><span data-stu-id="f62e6-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="f62e6-115">Altri membri del team potrebbero non rendersi conto che la delega informale è avvenuta e ne deriva confusione con le cure di un paziente.</span><span class="sxs-lookup"><span data-stu-id="f62e6-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="f62e6-116">*Esempio di utilizzo con impostazione dei delegati:* il dott. Franco Piccio è di guardia al reparto di radiologia.</span><span class="sxs-lookup"><span data-stu-id="f62e6-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="f62e6-117">Riceve una chiamata personale urgente e deve allontanarsi per le prossime due ore.</span><span class="sxs-lookup"><span data-stu-id="f62e6-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="f62e6-118">Chiede a uno dei suoi colleghi del reparto di radiologia, la dott.ssa Lena Ehrle di coprirlo mentre è via.</span><span class="sxs-lookup"><span data-stu-id="f62e6-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="f62e6-119">Cambia il suo messaggio di stato personalizzato per dire qualcosa di simile a "Non sono disponibile per le prossime ore.</span><span class="sxs-lookup"><span data-stu-id="f62e6-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="f62e6-120">Si prega di contattare @DrEhrle per eventuali emergenze. "</span><span class="sxs-lookup"><span data-stu-id="f62e6-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="f62e6-121">Altri nel team si rendono conto della delega mentre tentano di contattare il dott. Piccio, quindi ora sanno di dover contattare la dott.ssa Ehrle.</span><span class="sxs-lookup"><span data-stu-id="f62e6-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="f62e6-122">Ne consegue poca o nessuna confusione con le cure di un paziente.</span><span class="sxs-lookup"><span data-stu-id="f62e6-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="f62e6-123">Impatto delle modalità di coesistenza sullo stato dell'utente nel client Teams</span><span class="sxs-lookup"><span data-stu-id="f62e6-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="f62e6-124">Gli amministratori devono essere consapevoli che le note sullo stato e i comportamenti di menzione della delega dipenderanno in parte dalla modalità di coesistenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f62e6-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="f62e6-125">Questa matrice mostra le seguenti possibilità:</span><span class="sxs-lookup"><span data-stu-id="f62e6-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="f62e6-126">Modalità di Coesistenza</span><span class="sxs-lookup"><span data-stu-id="f62e6-126">Co-Existence Mode</span></span> | <span data-ttu-id="f62e6-127">Comportamento Previsto</span><span class="sxs-lookup"><span data-stu-id="f62e6-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="f62e6-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="f62e6-128">TeamsOnly</span></span> |<span data-ttu-id="f62e6-129">Gli utenti possono impostare una nota solo da Teams.</span><span class="sxs-lookup"><span data-stu-id="f62e6-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="f62e6-130">La nota Team dell'utente è visibile in Teams e SfB.</span><span class="sxs-lookup"><span data-stu-id="f62e6-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="f62e6-131">Isole</span><span class="sxs-lookup"><span data-stu-id="f62e6-131">Islands</span></span> | <span data-ttu-id="f62e6-132">Nota dell'utente impostata in Teams visibile solo in Teams.</span><span class="sxs-lookup"><span data-stu-id="f62e6-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="f62e6-133">Nota utente impostata in SfB visibile solo in SfB</span><span class="sxs-lookup"><span data-stu-id="f62e6-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="f62e6-134">Modalità SfB</span><span class="sxs-lookup"><span data-stu-id="f62e6-134">SfB\* modes</span></span> | <span data-ttu-id="f62e6-135">Gli utenti possono impostare una nota solo da SfB.</span><span class="sxs-lookup"><span data-stu-id="f62e6-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="f62e6-136">La nota SfB dell'utente è visibile in SfB e Teams.</span><span class="sxs-lookup"><span data-stu-id="f62e6-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="f62e6-137">Un utente può impostare una nota in Teams solo se la modalità è TeamsOnly o Isole.</span><span class="sxs-lookup"><span data-stu-id="f62e6-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="f62e6-138">Visualizzazione delle note impostate in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f62e6-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="f62e6-139">Non vi è alcuna indicazione visiva che sia stata impostata una nota da Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f62e6-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="f62e6-140">Skype for Business non applica un limite di caratteri alle note di stato.</span><span class="sxs-lookup"><span data-stu-id="f62e6-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="f62e6-141">Microsoft Teams visualizzerà solo i primi 280 caratteri di un set di note da Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f62e6-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="f62e6-142">Un'ellisse (…) alla fine di una nota indica il troncamento.</span><span class="sxs-lookup"><span data-stu-id="f62e6-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="f62e6-143">Skype for Business non supporta i tempi di scadenza per le note.</span><span class="sxs-lookup"><span data-stu-id="f62e6-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="f62e6-144">La migrazione delle note da Skype for Business a Teams non è supportata quando un utente viene aggiornato alla modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="f62e6-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f62e6-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f62e6-145">Related topics</span></span>

[<span data-ttu-id="f62e6-146">Coesistenza con Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f62e6-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
