---
title: 'Lync Server 2013: Panoramica del routing Location-Based per le conferenze'
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
ms.openlocfilehash: 9dd3508221babdd9c503e21d5662a1bbe60d4ce0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520953"
---
# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="28279-102">Panoramica del routing Location-Based per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28279-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28279-103">_**Ultimo argomento modificato:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="28279-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="28279-104">L'applicazione Location-Based routing Conferencing fornisce a Lync conferences un meccanismo per la prevenzione del bypass a pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="28279-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="28279-105">L'applicazione monitora le conferenze attive e applica Location-Based limitazioni del routing in base alla posizione degli utenti di Lync che partecipano.</span><span class="sxs-lookup"><span data-stu-id="28279-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="28279-106">L'applicazione di conferenza di routing Location-Based determina se Location-Based il routing deve essere applicato a una riunione di Lync se vengono soddisfatti i seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="28279-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="28279-107">L'organizzatore della riunione è abilitato per il routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="28279-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="28279-108">Le restrizioni di routing Location-Based verranno applicate solo alle conferenze organizzate dagli utenti abilitati per il routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="28279-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="28279-109">Almeno un partecipante alla riunione è un endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="28279-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="28279-110">Location-Based le restrizioni di routing sono applicabili solo per le conferenze che includono endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="28279-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="28279-111">Il sito di rete in cui si trova il gateway PSTN utilizzato per colmare la conferenza PSTN e i siti di rete in cui si connettono gli organizzatori e i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="28279-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="28279-112">L'applicazione di conferenza di routing Location-Based impedisce la partecipazione degli utenti di Lync e degli endpoint PSTN da siti di rete diversi alla stessa conferenza.</span><span class="sxs-lookup"><span data-stu-id="28279-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="28279-113">Se l'organizzatore di una riunione è abilitato per il routing Location-Based, l'applicazione per conferenze impone le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="28279-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="28279-114">Gli endpoint che possono partecipare a una riunione di Lync dipendono dagli endpoint che hanno già partecipato alla conferenza e questa restrizione viene modificata in base all'uscita degli endpoint Uniti e ai nuovi endpoint che partecipano alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="28279-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="28279-115">Se gli organizzatori e i partecipanti partecipano a una riunione di Lync dallo stesso sito di rete, un endpoint PSTN, un altro partecipante proveniente dallo stesso sito di rete, un altro partecipante proveniente da un sito di rete diverso o da un partecipante a un sito di rete sconosciuto può partecipare.</span><span class="sxs-lookup"><span data-stu-id="28279-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="28279-116">Se gli organizzatori e i partecipanti accedono alla riunione da siti di rete diversi o sconosciuti, non è consentito che un endpoint PSTN partecipi alla riunione se la chiamata PSTN accede da un trunk SIP abilitato per il routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="28279-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="28279-117">Se gli organizzatori e i partecipanti sono tutti Uniti alla riunione dallo stesso sito di rete e vi sono partecipanti che partecipano alla stessa riunione dalla PSTN, un endpoint di Lync proveniente da un sito di rete diverso non è autorizzato a partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="28279-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="28279-118">Queste restrizioni di routing Location-Based di conferenza sono riepilogate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="28279-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28279-119">Utente/i in una conferenza in un determinato punto</span><span class="sxs-lookup"><span data-stu-id="28279-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="28279-120">Utenti autorizzati a partecipare alla conferenza</span><span class="sxs-lookup"><span data-stu-id="28279-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="28279-121">Utenti non autorizzati a partecipare alla conferenza</span><span class="sxs-lookup"><span data-stu-id="28279-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28279-122">Utenti di Lync VoIP client da un singolo sito di rete</span><span class="sxs-lookup"><span data-stu-id="28279-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="28279-123">Utente client di Lync VoIP dallo stesso sito di rete</span><span class="sxs-lookup"><span data-stu-id="28279-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="28279-124">Utente client di Lync VoIP da un sito di rete diverso</span><span class="sxs-lookup"><span data-stu-id="28279-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="28279-125">Utente client di Lync VoIP da un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="28279-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="28279-126">Utente federato di Lync VoIP client</span><span class="sxs-lookup"><span data-stu-id="28279-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="28279-127">Aggiunta di un utente da un endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="28279-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="28279-128">Nessuno</span><span class="sxs-lookup"><span data-stu-id="28279-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28279-129">Utenti del client VoIP di Lync provenienti da un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="28279-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="28279-130">Utente client di Lync VoIP da qualsiasi sito</span><span class="sxs-lookup"><span data-stu-id="28279-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="28279-131">Utente client di Lync VoIP da un sito sconosciuto</span><span class="sxs-lookup"><span data-stu-id="28279-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="28279-132">Utente federato di Lync VoIP client</span><span class="sxs-lookup"><span data-stu-id="28279-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="28279-133">Aggiunta di un utente tramite un endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="28279-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28279-134">Utenti di Lync VoIP client provenienti da siti di rete diversi</span><span class="sxs-lookup"><span data-stu-id="28279-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="28279-135">Utente client di Lync VoIP da qualsiasi sito di rete</span><span class="sxs-lookup"><span data-stu-id="28279-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="28279-136">Utente client di Lync VoIP da un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="28279-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="28279-137">Utente federato di Lync VoIP client</span><span class="sxs-lookup"><span data-stu-id="28279-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="28279-138">Aggiunta di un utente tramite un endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="28279-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28279-139">Utenti del client VoIP di Lync provenienti da un singolo sito di rete e utenti che si congiungono da un endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="28279-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="28279-140">Utente client di Lync VoIP dallo stesso sito di rete</span><span class="sxs-lookup"><span data-stu-id="28279-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="28279-141">Utente client di Lync VoIP da un sito di rete diverso</span><span class="sxs-lookup"><span data-stu-id="28279-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="28279-142">Utente client di Lync VoIP da un sito di rete sconosciuto</span><span class="sxs-lookup"><span data-stu-id="28279-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="28279-143">Utente federato di Lync VoIP client</span><span class="sxs-lookup"><span data-stu-id="28279-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="28279-144">Di seguito sono riportate le caratteristiche aggiuntive dell'applicazione di conferenza di routing Location-Based:</span><span class="sxs-lookup"><span data-stu-id="28279-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="28279-145">Quando un utente non è autorizzato a partecipare a una conferenza in base Location-Based restrizioni di routing, la chiamata degli utenti alla conferenza verrà rifiutata e il client Lync riporterà che la chiamata non è stata completata o è terminata.</span><span class="sxs-lookup"><span data-stu-id="28279-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="28279-146">Un endpoint PSTN che partecipa a una conferenza con Location-Based le imposte del routing non sarà limitato a partecipare alla conferenza indipendentemente dal relativo stato, se l'endpoint si unisce tramite un trunk che non è abilitato per il routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="28279-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="28279-147">Un sistema PBX connesso a un server di Mediation tramite un trunk SIP che non esegue le chiamate alla rete PSTN avrà le stesse imposte degli utenti di Lync presenti nello stesso sito di rete in cui è definito il trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="28279-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="28279-148">Ad esempio, un endpoint PSTN sarà in grado di partecipare a una conferenza con un utente PBX e un utente di Lync se si trovano nello stesso sito di rete. in caso contrario, l'endpoint PSTN non sarà autorizzato a partecipare alla conferenza se l'utente PBX si trova in un sito di rete diverso da quello dell'utente Lync.</span><span class="sxs-lookup"><span data-stu-id="28279-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

