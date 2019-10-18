---
title: Delega del messaggio
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Un utente può impostare in modo esplicito un altro utente come delegato nel messaggio di stato.
ms.openlocfilehash: 56c0e9bd5394e738170130bab15803e5cb4d741c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570359"
---
# <a name="message-delegation"></a><span data-ttu-id="8d91d-103">Delega del messaggio</span><span class="sxs-lookup"><span data-stu-id="8d91d-103">Message delegation</span></span>

<span data-ttu-id="8d91d-104">Un utente può già impostare esplicitamente lo stato su away o non disturbare e specificare il testo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8d91d-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="8d91d-105">La caratteristica delega messaggio funziona nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8d91d-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="8d91d-106">Un utente @username menziona un altro utente in parte di un messaggio di stato del testo, suggerendo che, mentre non sono disponibili persone che desiderano contattarle, contattare il @username utente menzionato.</span><span class="sxs-lookup"><span data-stu-id="8d91d-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="8d91d-107">La persona che è stata assegnata come delegato viene avvisata che è stata nominata come delegato.</span><span class="sxs-lookup"><span data-stu-id="8d91d-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="8d91d-108">Chi prova a contattare il primo utente può quindi passare il puntatore del mouse sul delegato nominato e facilmente Message il delegato.</span><span class="sxs-lookup"><span data-stu-id="8d91d-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="8d91d-109">Si tratta di un processo avviato dall'utente nel client e non è necessario alcun coinvolgimento dell'amministratore per abilitare la caratteristica.</span><span class="sxs-lookup"><span data-stu-id="8d91d-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="8d91d-110">Scenario use Delegation in Healthcare</span><span class="sxs-lookup"><span data-stu-id="8d91d-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="8d91d-111">*Esempio di utilizzo senza impostare delegati:*  Il dottor Franco Piccio è in servizio presso il dipartimento di radiologia.</span><span class="sxs-lookup"><span data-stu-id="8d91d-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="8d91d-112">Riceve una chiamata personale urgente e deve andarsene per le prossime due ore.</span><span class="sxs-lookup"><span data-stu-id="8d91d-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="8d91d-113">Chiede a uno dei suoi coetanei del dipartimento di radiologia, la dottoressa Lena Ehrle, di occuparsi di lui mentre è fuori sede.</span><span class="sxs-lookup"><span data-stu-id="8d91d-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="8d91d-114">Informalmente consegna il suo cercapersone al Dr. Ehrle, che sta ascoltando i messaggi urgenti e i ping sul pager e li risponde per conto del dottor Piccio, oltre alle sue attuali responsabilità.</span><span class="sxs-lookup"><span data-stu-id="8d91d-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="8d91d-115">Gli altri membri del team potrebbero non realizzare la delegazione informale e la confusione che ne consegue con le cure di un paziente.</span><span class="sxs-lookup"><span data-stu-id="8d91d-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="8d91d-116">*Esempio di utilizzo con l'impostazione dei delegati:* Il dottor Franco Piccio è in servizio presso il dipartimento di radiologia.</span><span class="sxs-lookup"><span data-stu-id="8d91d-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="8d91d-117">Riceve una chiamata personale urgente e deve andarsene per le prossime due ore.</span><span class="sxs-lookup"><span data-stu-id="8d91d-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="8d91d-118">Chiede a uno dei suoi coetanei nel dipartimento di radiologia, la dottoressa Lena Ehrle di occuparsi di lui mentre è fuori sede.</span><span class="sxs-lookup"><span data-stu-id="8d91d-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="8d91d-119">Modifica il messaggio di stato personalizzato per dire qualcosa di simile a "non sono disponibile per le prossime ore.</span><span class="sxs-lookup"><span data-stu-id="8d91d-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="8d91d-120">Contattare @DrEhrle per eventuali emergenze. "</span><span class="sxs-lookup"><span data-stu-id="8d91d-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="8d91d-121">Altri membri del team realizzano che la delegazione è avvenuta mentre tentano di contattare il Dr. Piccio, in modo che ora sappiano di contattare il Dr. Ehrle nel frattempo.</span><span class="sxs-lookup"><span data-stu-id="8d91d-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="8d91d-122">Non ne consegue confusione con il paziente.</span><span class="sxs-lookup"><span data-stu-id="8d91d-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="8d91d-123">Impatto delle modalità di coesistenza sullo stato dell'utente nel client Teams</span><span class="sxs-lookup"><span data-stu-id="8d91d-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="8d91d-124">Gli amministratori devono tenere presente che le note di stato e i comportamenti di menzione della delega dipendono in parte dalla modalità di coesistenza di un utente.</span><span class="sxs-lookup"><span data-stu-id="8d91d-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user’s co-existence mode.</span></span> <span data-ttu-id="8d91d-125">Questa matrice Mostra le possibilità:</span><span class="sxs-lookup"><span data-stu-id="8d91d-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="8d91d-126">Modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="8d91d-126">Co-Existence Mode</span></span> | <span data-ttu-id="8d91d-127">Comportamento previsto</span><span class="sxs-lookup"><span data-stu-id="8d91d-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="8d91d-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="8d91d-128">TeamsOnly</span></span> |<span data-ttu-id="8d91d-129">Gli utenti possono impostare una nota solo da teams.</span><span class="sxs-lookup"><span data-stu-id="8d91d-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="8d91d-130">La nota Teams dell'utente è visibile in teams & SfB.</span><span class="sxs-lookup"><span data-stu-id="8d91d-130">User’s Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="8d91d-131">Isole</span><span class="sxs-lookup"><span data-stu-id="8d91d-131">Islands</span></span> | <span data-ttu-id="8d91d-132">Nota dell'utente impostata in teams visibile solo in teams.</span><span class="sxs-lookup"><span data-stu-id="8d91d-132">User’s note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="8d91d-133">Nota dell'utente impostata in SfB visibile solo in SfB</span><span class="sxs-lookup"><span data-stu-id="8d91d-133">User’s note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="8d91d-134">Modalità \* SfB</span><span class="sxs-lookup"><span data-stu-id="8d91d-134">SfB\* modes</span></span> | <span data-ttu-id="8d91d-135">Gli utenti possono impostare una nota solo da SfB.</span><span class="sxs-lookup"><span data-stu-id="8d91d-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="8d91d-136">La nota SfB dell'utente è visibile in SfB & teams.</span><span class="sxs-lookup"><span data-stu-id="8d91d-136">User’s SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="8d91d-137">Un utente può impostare una nota solo in teams se la modalità è TeamsOnly o Islands.</span><span class="sxs-lookup"><span data-stu-id="8d91d-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="8d91d-138">Visualizzazione delle note impostate in Skype for business</span><span class="sxs-lookup"><span data-stu-id="8d91d-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="8d91d-139">Non ci sono indicazioni visive che una nota sia stata impostata da Skype for business.</span><span class="sxs-lookup"><span data-stu-id="8d91d-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="8d91d-140">Skype for business non applica un limite di caratteri alle note di stato.</span><span class="sxs-lookup"><span data-stu-id="8d91d-140">Skype for Business doesn’t enforce a character limit on status notes.</span></span> <span data-ttu-id="8d91d-141">Microsoft teams visualizzerà solo i primi 280 caratteri di una nota impostata da Skype for business.</span><span class="sxs-lookup"><span data-stu-id="8d91d-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="8d91d-142">Un oggetto Ellipse (...) alla fine di una nota indica il troncamento.</span><span class="sxs-lookup"><span data-stu-id="8d91d-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="8d91d-143">Skype for business non supporta gli orari di scadenza delle note.</span><span class="sxs-lookup"><span data-stu-id="8d91d-143">Skype for Business doesn’t support expiry times for notes.</span></span>

<span data-ttu-id="8d91d-144">La migrazione delle note da Skype for business a teams non è supportata quando un utente viene aggiornato alla modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="8d91d-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d91d-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8d91d-145">Related topics</span></span>

[<span data-ttu-id="8d91d-146">Coesistenza con Skype for business</span><span class="sxs-lookup"><span data-stu-id="8d91d-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
