---
title: 'Lync Server 2013: Panoramica del routing basato sulla posizione per i servizi di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adb103d1f2314e033d9ef0958dd05a7648012bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="f95b1-102">Panoramica del routing basato sulla posizione per i servizi di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f95b1-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f95b1-103">_**Argomento Ultima modifica:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="f95b1-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="f95b1-104">L'applicazione per i servizi di conferenza di routing basato sulla posizione offre alle conferenze di Lync un meccanismo per la prevenzione del bypass a pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="f95b1-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="f95b1-105">L'applicazione monitora le conferenze attive e applica le restrizioni di routing basate sulla posizione in base alla posizione degli utenti di Lync partecipanti.</span><span class="sxs-lookup"><span data-stu-id="f95b1-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="f95b1-106">L'applicazione per i servizi di conferenza di routing basata sulla posizione determina se il routing basato sulla posizione deve essere applicato a una riunione Lync se vengono soddisfatti i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f95b1-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="f95b1-107">L'organizzatore della riunione è abilitato per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="f95b1-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="f95b1-108">Le restrizioni di routing basate sul percorso verranno applicate solo alle conferenze organizzate dagli utenti abilitati per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="f95b1-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="f95b1-109">Almeno un partecipante alla riunione è un endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="f95b1-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="f95b1-110">Le restrizioni di routing basate sulla posizione sono applicabili solo per le conferenze che includono endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="f95b1-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="f95b1-111">Sito di rete in cui si trova il gateway PSTN usato per il Bridge della conferenza alla rete PSTN, nonché i siti di Network in cui gli organizzatori e i partecipanti sono connessi.</span><span class="sxs-lookup"><span data-stu-id="f95b1-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="f95b1-112">L'applicazione di conferenza di routing basata sulla posizione impedisce la partecipazione degli utenti di Lync e degli endpoint PSTN da siti di rete diversi alla stessa conferenza.</span><span class="sxs-lookup"><span data-stu-id="f95b1-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="f95b1-113">Se l'organizzatore di una riunione è abilitato per il routing basato sulla posizione, l'applicazione di conferenza applica le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f95b1-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="f95b1-114">Gli endpoint che possono partecipare a una riunione Lync dipendono dagli endpoint che hanno già partecipato alla conferenza e questa restrizione viene regolata quando gli endpoint Uniti vengono abbandonati e i nuovi endpoint partecipano alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="f95b1-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="f95b1-115">Se gli organizzatori e i partecipanti partecipano a una riunione Lync dallo stesso sito di rete, viene consentito un endpoint PSTN, un altro partecipante dello stesso sito di rete, un altro partecipante da un sito di rete diverso o da un partecipante di un sito di rete sconosciuto partecipare a.</span><span class="sxs-lookup"><span data-stu-id="f95b1-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="f95b1-116">Se gli organizzatori e i partecipanti partecipano alla riunione da siti di rete diversi o sconosciuti, non è consentito l'accesso alla riunione da parte di un endpoint PSTN se la chiamata PSTN entra da un trunk SIP abilitato per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="f95b1-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="f95b1-117">Se gli organizzatori e i partecipanti partecipano alla riunione dallo stesso sito di rete e i partecipanti partecipano alla stessa riunione da PSTN, non è consentito partecipare alla riunione a un endpoint di Lync proveniente da un sito di rete diverso.</span><span class="sxs-lookup"><span data-stu-id="f95b1-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="f95b1-118">Queste restrizioni di routing basate sulla posizione dei servizi di conferenza sono riepilogate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f95b1-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f95b1-119">Utenti in una conferenza in un dato punto</span><span class="sxs-lookup"><span data-stu-id="f95b1-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="f95b1-120">Utenti autorizzati a partecipare alla conferenza</span><span class="sxs-lookup"><span data-stu-id="f95b1-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="f95b1-121">Utenti non autorizzati a partecipare alla conferenza</span><span class="sxs-lookup"><span data-stu-id="f95b1-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f95b1-122">Utenti del client VoIP di Lync da un singolo sito di rete</span><span class="sxs-lookup"><span data-stu-id="f95b1-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="f95b1-123">Utente client VoIP di Lync dello stesso sito di rete</span><span class="sxs-lookup"><span data-stu-id="f95b1-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="f95b1-124">Utente client VoIP di Lync da un sito di rete diverso</span><span class="sxs-lookup"><span data-stu-id="f95b1-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="f95b1-125">Utente client VoIP di Lync da un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="f95b1-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="f95b1-126">Utenti client VoIP di Lync federati</span><span class="sxs-lookup"><span data-stu-id="f95b1-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="f95b1-127">Aggiunta di un utente da un endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="f95b1-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="f95b1-128">Nessuno</span><span class="sxs-lookup"><span data-stu-id="f95b1-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f95b1-129">Utenti del client VoIP di Lync da un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="f95b1-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="f95b1-130">Utente client VoIP di Lync da qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="f95b1-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="f95b1-131">Utente client VoIP di Lync da un sito sconosciuto</span><span class="sxs-lookup"><span data-stu-id="f95b1-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="f95b1-132">Utenti client VoIP di Lync federati</span><span class="sxs-lookup"><span data-stu-id="f95b1-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="f95b1-133">L'aggiunta di un utente tramite un endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="f95b1-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f95b1-134">Utenti client VoIP di Lync provenienti da siti di rete diversi</span><span class="sxs-lookup"><span data-stu-id="f95b1-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="f95b1-135">Utente client VoIP di Lync da qualsiasi sito di rete</span><span class="sxs-lookup"><span data-stu-id="f95b1-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="f95b1-136">Utente client VoIP di Lync da un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="f95b1-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="f95b1-137">Utenti client VoIP di Lync federati</span><span class="sxs-lookup"><span data-stu-id="f95b1-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="f95b1-138">L'aggiunta di un utente tramite un endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="f95b1-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f95b1-139">Utenti del client VoIP di Lync da un singolo sito di rete e utenti che partecipano da un endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="f95b1-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="f95b1-140">Utente client VoIP di Lync dello stesso sito di rete</span><span class="sxs-lookup"><span data-stu-id="f95b1-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="f95b1-141">Utente client VoIP di Lync da un sito di rete diverso</span><span class="sxs-lookup"><span data-stu-id="f95b1-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="f95b1-142">Utente client VoIP di Lync da un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="f95b1-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="f95b1-143">Utenti client VoIP di Lync federati</span><span class="sxs-lookup"><span data-stu-id="f95b1-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f95b1-144">Di seguito sono riportate le caratteristiche aggiuntive dell'applicazione di conferenza di routing basata sulla posizione:</span><span class="sxs-lookup"><span data-stu-id="f95b1-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="f95b1-145">Quando un utente non è autorizzato a partecipare a una conferenza con restrizioni di routing basate sulla posizione, la chiamata degli utenti alla conferenza verrà rifiutata e il client Lync riferirà che la chiamata non è stata completata o è terminata.</span><span class="sxs-lookup"><span data-stu-id="f95b1-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="f95b1-146">Un endpoint PSTN che partecipa a una conferenza con le imposte di routing basate sul percorso non sarà limitato per partecipare alla conferenza indipendentemente dallo stato, se l'endpoint si unisce tramite un trunk non abilitato per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="f95b1-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="f95b1-147">Un sistema PBX connesso a un server di mediazione su un trunk SIP che non esegue l'uscita dalle chiamate alla rete PSTN avrà le stesse imposte degli utenti di Lync nello stesso sito di rete in cui è definito il trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="f95b1-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="f95b1-148">Ad esempio, un endpoint PSTN sarà in grado di partecipare a una conferenza con un utente PBX e un utente di Lync se si trovano nello stesso sito di rete; in caso contrario, l'endpoint PSTN non sarà autorizzato a partecipare alla conferenza se l'utente PBX si trova in un sito di rete diverso da quello dell'utente di Lync.</span><span class="sxs-lookup"><span data-stu-id="f95b1-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

