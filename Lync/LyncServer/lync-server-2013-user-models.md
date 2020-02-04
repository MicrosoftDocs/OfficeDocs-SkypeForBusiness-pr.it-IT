---
title: 'Lync Server 2013: modelli utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8f45b3ea11911ea7a3dce36b0b6a9d64ac1e690
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="84cfd-102">Modelli utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84cfd-102">User models in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84cfd-103">_**Argomento Ultima modifica:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="84cfd-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="84cfd-104">I modelli di utenti descritti in questa sezione costituiscono la base per le misure e le raccomandazioni per la pianificazione della capacità descritte nella [pianificazione della capacità per Lync Server 2013 con i modelli utente](lync-server-2013-capacity-planning-using-the-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="84cfd-104">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="84cfd-105">Modelli di utenti di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84cfd-105">Lync Server 2013 User Models</span></span>

<span data-ttu-id="84cfd-106">La tabella seguente descrive il modello di utente per la registrazione, i contatti, la messaggistica istantanea e la presenza per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84cfd-106">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="84cfd-107">Modello utente ambiente e registrazione</span><span class="sxs-lookup"><span data-stu-id="84cfd-107">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84cfd-108">Categoria</span><span class="sxs-lookup"><span data-stu-id="84cfd-108">Category</span></span></th>
<th><span data-ttu-id="84cfd-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84cfd-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-110">Dimensioni e distribuzione della distribuzione</span><span class="sxs-lookup"><span data-stu-id="84cfd-110">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="84cfd-111">Modelliamo una distribuzione di grandi dimensioni con tre siti centrali, con un pool di front-end per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="84cfd-111">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-112">Percentuale di utenti di Active Directory</span><span class="sxs-lookup"><span data-stu-id="84cfd-112">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="84cfd-113">Supponiamo che il 70% di tutti gli utenti di Active Directory dell'organizzazione siano abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="84cfd-113">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="84cfd-114">80% degli utenti abilitati hanno eseguito l'accesso a Lync Server ogni giorno (80% di concorrenza).</span><span class="sxs-lookup"><span data-stu-id="84cfd-114">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="84cfd-115">Gli utenti simultanei sono la base per i numeri nel resto di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="84cfd-115">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-116">Modifiche di Active Directory</span><span class="sxs-lookup"><span data-stu-id="84cfd-116">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="84cfd-117">Supponiamo che il 0,5% degli utenti totali venga creato e abilitato per Lync in Active Directory ogni settimana e che il 0,5% degli utenti totali sia disabilitato da Active Directory e da Lync ogni settimana.</span><span class="sxs-lookup"><span data-stu-id="84cfd-117">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="84cfd-118">il 5% degli utenti ha almeno un attributo Active Directory modificato ogni settimana.</span><span class="sxs-lookup"><span data-stu-id="84cfd-118">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-119">Gruppi di distribuzione di Active Directory</span><span class="sxs-lookup"><span data-stu-id="84cfd-119">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="84cfd-120">Supponiamo che il numero di gruppi di distribuzione di Active Directory nell'organizzazione sia pari a tre volte il numero di tutti gli utenti in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="84cfd-120">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory.</span></span> <span data-ttu-id="84cfd-121">I gruppi di distribuzione hanno le dimensioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84cfd-121">The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="84cfd-122">64% hanno utenti di 2-30</span><span class="sxs-lookup"><span data-stu-id="84cfd-122">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="84cfd-123">il 13% ha 31-50 utenti</span><span class="sxs-lookup"><span data-stu-id="84cfd-123">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="84cfd-124">10% hanno 51-100 utenti</span><span class="sxs-lookup"><span data-stu-id="84cfd-124">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="84cfd-125">il 13% ha 101-500 utenti</span><span class="sxs-lookup"><span data-stu-id="84cfd-125">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-126">Utenti VoIP (Voice over IP)</span><span class="sxs-lookup"><span data-stu-id="84cfd-126">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="84cfd-127">60% degli utenti di Lync Server sono abilitati per le comunicazioni unificate (UC), ovvero i relativi numeri di telefono sono di proprietà di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="84cfd-127">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-128">Distribuzione client registrata</span><span class="sxs-lookup"><span data-stu-id="84cfd-128">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="84cfd-129">il 65% dei client esegue il software Lync 2013, inclusi Lync e Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="84cfd-129">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="84cfd-130">30% dei client che gestiscono il software client da una versione precedente di Lync.</span><span class="sxs-lookup"><span data-stu-id="84cfd-130">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="84cfd-131">5% di client che usano Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="84cfd-131">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="84cfd-132">Se è abilitata la mobilità, presupponiamo che il 40% degli utenti usi la mobilità in concomitanza con le altre opzioni del client registrato precedentemente citate.</span><span class="sxs-lookup"><span data-stu-id="84cfd-132">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options.</span></span> <span data-ttu-id="84cfd-133">In questo caso, il rapporto di multiple Point of Presence (MPOP) del client è 1:1.9.</span><span class="sxs-lookup"><span data-stu-id="84cfd-133">In this case the client multiple point of presence (MPOP) ratio is 1:1.9.</span></span> <span data-ttu-id="84cfd-134">Se la mobilità è disabilitata, il rapporto MPOP è 1:1.5.</span><span class="sxs-lookup"><span data-stu-id="84cfd-134">If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-135">Distribuzione remota degli utenti</span><span class="sxs-lookup"><span data-stu-id="84cfd-135">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="84cfd-136">70% degli utenti che si connettono internamente.</span><span class="sxs-lookup"><span data-stu-id="84cfd-136">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="84cfd-137">30% degli utenti che si connettono tramite un server perimetrale e un amministratore.</span><span class="sxs-lookup"><span data-stu-id="84cfd-137">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-138">Distribuzione di contatti</span><span class="sxs-lookup"><span data-stu-id="84cfd-138">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="84cfd-139">Il numero massimo di contatti di un utente è 1.000.</span><span class="sxs-lookup"><span data-stu-id="84cfd-139">The maximum number of contacts a user has is 1,000.</span></span> <span data-ttu-id="84cfd-140">Meno dell'1% degli utenti ha contatti di 1.000.</span><span class="sxs-lookup"><span data-stu-id="84cfd-140">Less than 1% of users have 1,000 contacts.</span></span> <span data-ttu-id="84cfd-141">Meno del 25% degli utenti ha 100 o più contatti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-141">Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="84cfd-142">Media dei contatti di 80 per gli utenti con connettività cloud pubblica.</span><span class="sxs-lookup"><span data-stu-id="84cfd-142">Average of 80 contacts for users with public cloud connectivity.</span></span> <span data-ttu-id="84cfd-143">Di questi utenti:</span><span class="sxs-lookup"><span data-stu-id="84cfd-143">Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="84cfd-144">50% dei contatti si trovano all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84cfd-144">50% of the contacts are within the organization.</span></span> <span data-ttu-id="84cfd-145">il 10% degli utenti sono utenti remoti, che si connettono dall'esterno del firewall.</span><span class="sxs-lookup"><span data-stu-id="84cfd-145">10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="84cfd-146">40% dei contatti sono utenti di cloud pubblici (ad esempio utenti di AOL, Yahoo!, MSN o Google Talk).</span><span class="sxs-lookup"><span data-stu-id="84cfd-146">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="84cfd-147">il 10% dei contatti è da partner federati.</span><span class="sxs-lookup"><span data-stu-id="84cfd-147">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="84cfd-148">A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="84cfd-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="84cfd-149">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="84cfd-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="84cfd-150">Messenger fino alla data di chiusura del servizio.</span><span class="sxs-lookup"><span data-stu-id="84cfd-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="84cfd-151">Data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="84cfd-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="84cfd-152">è stato annunciato.</span><span class="sxs-lookup"><span data-stu-id="84cfd-152">has been announced.</span></span> <span data-ttu-id="84cfd-153">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="84cfd-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="84cfd-154">Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="84cfd-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="84cfd-155">Messenger.</span><span class="sxs-lookup"><span data-stu-id="84cfd-155">Messenger.</span></span> <span data-ttu-id="84cfd-156">La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</span><span class="sxs-lookup"><span data-stu-id="84cfd-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="84cfd-157">Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="84cfd-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="84cfd-158">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="84cfd-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="84cfd-159">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</span><span class="sxs-lookup"><span data-stu-id="84cfd-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="84cfd-160">Media dei contatti di 50 per gli utenti senza connettività cloud pubblica.</span><span class="sxs-lookup"><span data-stu-id="84cfd-160">Average of 50 contacts for users without public cloud connectivity.</span></span> <span data-ttu-id="84cfd-161">Di questi utenti:</span><span class="sxs-lookup"><span data-stu-id="84cfd-161">Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="84cfd-162">80% dei contatti si trovano all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84cfd-162">80% of the contacts are within the organization.</span></span> <span data-ttu-id="84cfd-163">il 10% degli utenti sono utenti remoti, che si connettono dall'esterno del firewall.</span><span class="sxs-lookup"><span data-stu-id="84cfd-163">10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="84cfd-164">il 20% dei contatti è da partner federati.</span><span class="sxs-lookup"><span data-stu-id="84cfd-164">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="84cfd-165">Ogni utente ha un gruppo di distribuzione nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-165">Each user has 1 distribution group in their contact list.</span></span> <span data-ttu-id="84cfd-166">Per i test delle prestazioni, presupponiamo che i gruppi di distribuzione siano sempre espansi.</span><span class="sxs-lookup"><span data-stu-id="84cfd-166">For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="84cfd-167">il 25% dei contatti di un utente usa XMPP.</span><span class="sxs-lookup"><span data-stu-id="84cfd-167">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-168">Ora della sessione</span><span class="sxs-lookup"><span data-stu-id="84cfd-168">Session time</span></span></p></td>
<td><p><span data-ttu-id="84cfd-169">La sessione di accesso utente media dura 12 ore.</span><span class="sxs-lookup"><span data-stu-id="84cfd-169">The average user logon session lasts 12 hours.</span></span> <span data-ttu-id="84cfd-170">Tutti gli utenti accedono a 120 minuti dall'inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="84cfd-170">All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="84cfd-171">Modello utente di messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="84cfd-171">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84cfd-172">Categoria</span><span class="sxs-lookup"><span data-stu-id="84cfd-172">Category</span></span></th>
<th><span data-ttu-id="84cfd-173">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84cfd-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-174">Sessioni di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="84cfd-174">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="84cfd-175">Ogni utente calcola la media di sei sessioni di messaggistica istantanea peer-to-peer per giorno.</span><span class="sxs-lookup"><span data-stu-id="84cfd-175">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="84cfd-176">10 messaggi istantanei per sessione.</span><span class="sxs-lookup"><span data-stu-id="84cfd-176">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="84cfd-177">Ogni messaggio è abbinato a due messaggi di informazioni SIP e 2 messaggi OK di SIP 200 (per gli indicatori di stato&lt;,&gt; ad esempio "nome sta digitando")</span><span class="sxs-lookup"><span data-stu-id="84cfd-177">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-178">Polling presenza</span><span class="sxs-lookup"><span data-stu-id="84cfd-178">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="84cfd-179">In generale, presupponiamo il polling della presenza in media di 60 sondaggi per utente per ora.</span><span class="sxs-lookup"><span data-stu-id="84cfd-179">Overall, we assume presence polling at an average of 60 polls per user per hour.</span></span> <span data-ttu-id="84cfd-180">Per ogni utente, assumere una media di:</span><span class="sxs-lookup"><span data-stu-id="84cfd-180">For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="84cfd-181">Un sondaggio per giorno della presenza di utenti nella scheda organizzazione dell'utente, ma non nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-181">One poll per day of the presence of users in the user’s organization tab (but not Contacts list).</span></span> <span data-ttu-id="84cfd-182">Il numero medio di non contatti nella scheda organizzazione dell'utente è di 15 utenti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-182">Average number of non-contacts in the user’s organization tab is 15 users.</span></span> <span data-ttu-id="84cfd-183">Due operazioni di visualizzazione della scheda contatto per giorno.</span><span class="sxs-lookup"><span data-stu-id="84cfd-183">Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="84cfd-184">Un sondaggio di presenza ogni volta che l'utente fa clic su un altro utente per avviare una conversazione, stimata in una volta all'ora.</span><span class="sxs-lookup"><span data-stu-id="84cfd-184">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="84cfd-185">Sei ricerche utente per ora.</span><span class="sxs-lookup"><span data-stu-id="84cfd-185">Six user searches per hour.</span></span> <span data-ttu-id="84cfd-186">Ogni volta che viene eseguita una ricerca, viene inviato un sondaggio batch per tutti gli utenti nell'elenco dei risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="84cfd-186">Every time a search is performed, a batch poll is sent for everyone in the search result list.</span></span> <span data-ttu-id="84cfd-187">Supponiamo che la dimensione media dei risultati della ricerca sia 20.</span><span class="sxs-lookup"><span data-stu-id="84cfd-187">We assume the average size of search results is 20.</span></span> <span data-ttu-id="84cfd-188">Se i risultati della ricerca rimangono sullo schermo, il sondaggio batch viene aggiornato ogni 5 minuti; Supponiamo che ci saranno due aggiornamenti per ora.</span><span class="sxs-lookup"><span data-stu-id="84cfd-188">If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="84cfd-189">Quando l'utente apre o Visualizza in anteprima un messaggio di posta elettronica in Outlook, viene visualizzato un sondaggio sulla presenza degli utenti nei campi a: e CC: del messaggio di posta elettronica, stimati in cinque messaggi all'ora e quattro utenti per ogni messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="84cfd-189">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-190">Abbonamenti alla presenza</span><span class="sxs-lookup"><span data-stu-id="84cfd-190">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="84cfd-191">Quando un utente aggiunge un altro come contatto, il primo utente sta <em>sottoscrivendo</em> cinque categorie di informazioni sul secondo utente.</span><span class="sxs-lookup"><span data-stu-id="84cfd-191">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user.</span></span> <span data-ttu-id="84cfd-192">Gli aggiornamenti di queste categorie di informazioni vengono inviati automaticamente al primo utente.</span><span class="sxs-lookup"><span data-stu-id="84cfd-192">Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="84cfd-193">Per ogni client, viene inviata una richiesta di abbonamento a un singolo batch per ottenere lo stato di presenza di una media di contatti di 40, con una finestra di dialogo di 40 aggiuntiva per ottenere la presenza di contatti federati.</span><span class="sxs-lookup"><span data-stu-id="84cfd-193">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="84cfd-194">La presenza per i membri di un gruppo di distribuzione espanso viene trovata tramite sottoscrizioni di presenza persistente, non polling, ed è modellata come 1 espansione per ogni utente per ogni 2 ore.</span><span class="sxs-lookup"><span data-stu-id="84cfd-194">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="84cfd-195">Gli <em>abbonamenti brevi</em> si verificano quando un utente effettua l'accesso, esiste un abbonamento batch per tutti i contatti dell'utente e quindi l'utente si disconnette presto.</span><span class="sxs-lookup"><span data-stu-id="84cfd-195"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off.</span></span> <span data-ttu-id="84cfd-196">Assumiamo 6 abbonamenti brevi per ogni utente per ora, in cui ogni sottoscrizione dura 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-196">We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-197">Pubblicazione di presenza</span><span class="sxs-lookup"><span data-stu-id="84cfd-197">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="84cfd-198">Lo stato presenza viene pubblicato in media 4 pubblicazioni per utente per ora, con un massimo di 6 per utente per ora.</span><span class="sxs-lookup"><span data-stu-id="84cfd-198">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-199">Dimensioni del documento di presenza</span><span class="sxs-lookup"><span data-stu-id="84cfd-199">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="84cfd-200">Si presume che la dimensione media di un documento di presenza completa sia 4K, con un massimo di 25K.</span><span class="sxs-lookup"><span data-stu-id="84cfd-200">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="84cfd-201">La tabella seguente descrive il modello di utente per l'uso della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="84cfd-201">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="84cfd-202">Modello utente utilizzo Rubrica</span><span class="sxs-lookup"><span data-stu-id="84cfd-202">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84cfd-203">Modalità di ricerca della Rubrica</span><span class="sxs-lookup"><span data-stu-id="84cfd-203">Address Book search mode</span></span></th>
<th><span data-ttu-id="84cfd-204">L'uso</span><span class="sxs-lookup"><span data-stu-id="84cfd-204">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-205">Solo query Web della Rubrica (tutte le query eseguite dal servizio query Web Rubrica)</span><span class="sxs-lookup"><span data-stu-id="84cfd-205">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="84cfd-206">Quattro query di prefisso per utente per giorno.</span><span class="sxs-lookup"><span data-stu-id="84cfd-206">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="84cfd-207">60 query di ricerca esatte per utente per giorno.</span><span class="sxs-lookup"><span data-stu-id="84cfd-207">60 exact search queries per user per day.</span></span> <span data-ttu-id="84cfd-208">40% di questi vengono raggruppati in batch, con una media di 20 contatti per query.</span><span class="sxs-lookup"><span data-stu-id="84cfd-208">40% of those are batched, with an average of 20 contacts per query.</span></span> <span data-ttu-id="84cfd-209">L'altro 60% delle query è per un singolo contatto.</span><span class="sxs-lookup"><span data-stu-id="84cfd-209">The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="84cfd-210">25 query fotografiche per utente per giorno.</span><span class="sxs-lookup"><span data-stu-id="84cfd-210">25 photo queries per user per day.</span></span> <span data-ttu-id="84cfd-211">24 per una singola foto, l'altra è una query batch con una media di 20 contatti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-211">24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="84cfd-212">Una query di ricerca totale dell'organizzazione per ogni utente per giorno.</span><span class="sxs-lookup"><span data-stu-id="84cfd-212">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-213">Modalità mista, sia file della rubrica che query Web usate.</span><span class="sxs-lookup"><span data-stu-id="84cfd-213">Mixed mode, both address book file and web queries used.</span></span> <span data-ttu-id="84cfd-214">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="84cfd-214">This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="84cfd-215">Solo due tipi di query accedono alla rete, alla foto e alle query di ricerca dell'organizzazione totale.</span><span class="sxs-lookup"><span data-stu-id="84cfd-215">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="84cfd-216">25 query fotografiche per utente per giorno.</span><span class="sxs-lookup"><span data-stu-id="84cfd-216">25 photo queries per user per day.</span></span> <span data-ttu-id="84cfd-217">24 per una singola foto, l'altra è una query batch con una media di 20 contatti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-217">24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="84cfd-218">Una query di ricerca totale dell'organizzazione per ogni utente per giorno.</span><span class="sxs-lookup"><span data-stu-id="84cfd-218">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="84cfd-219">La tabella seguente descrive il modello di conferenza.</span><span class="sxs-lookup"><span data-stu-id="84cfd-219">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="84cfd-220">Modello di conferenza</span><span class="sxs-lookup"><span data-stu-id="84cfd-220">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84cfd-221">Categoria</span><span class="sxs-lookup"><span data-stu-id="84cfd-221">Category</span></span></th>
<th><span data-ttu-id="84cfd-222">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84cfd-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-223">Riunioni pianificate &quot;rispetto alle&quot; riunioni di riunione ora</span><span class="sxs-lookup"><span data-stu-id="84cfd-223">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="84cfd-224">60% programmato, 40% non programmato.</span><span class="sxs-lookup"><span data-stu-id="84cfd-224">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="84cfd-225">Delle riunioni pianificate, supponiamo che al 80% vengano assegnate conferenze, che sono occorrenze di conferenze periodiche; 10% sono riunioni aperte una tantum; 8% sono riunioni anonime una tantum e il 2% sono riunioni chiuse una sola volta.</span><span class="sxs-lookup"><span data-stu-id="84cfd-225">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-226">Distribuzione client di servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="84cfd-226">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="84cfd-227">Per le riunioni pianificate:</span><span class="sxs-lookup"><span data-stu-id="84cfd-227">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="84cfd-228">65% degli utenti dei servizi di conferenza usano Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="84cfd-228">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="84cfd-229">il 5% degli utenti dei servizi di conferenza USA Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="84cfd-229">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="84cfd-230">il 30% degli utenti dei servizi di conferenza USA client precedenti, inclusi Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 e Microsoft Office Communicator Web Access (versione 2007).</span><span class="sxs-lookup"><span data-stu-id="84cfd-230">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="84cfd-231">Per le riunioni non pianificate:</span><span class="sxs-lookup"><span data-stu-id="84cfd-231">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="84cfd-232">70% degli utenti dei servizi di conferenza usano Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="84cfd-232">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="84cfd-233">il 30% degli utenti dei servizi di conferenza USA client precedenti, inclusi Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 e Microsoft Office Communicator Web Access (versione 2007).</span><span class="sxs-lookup"><span data-stu-id="84cfd-233">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-234">Concorrenza della riunione</span><span class="sxs-lookup"><span data-stu-id="84cfd-234">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="84cfd-235">il 5% degli utenti sarà in conferenze durante l'orario di lavoro.</span><span class="sxs-lookup"><span data-stu-id="84cfd-235">5% of users will be in conferences during working hours.</span></span> <span data-ttu-id="84cfd-236">Quindi, in un pool di utenti di 80.000, almeno un numero di utenti di 4.000 potrebbe essere presente in una conferenza in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="84cfd-236">Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-237">Distribuzione audio della riunione</span><span class="sxs-lookup"><span data-stu-id="84cfd-237">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="84cfd-238">40% di servizi di audioconferenza misti VoIP e con accesso esterno, con un rapporto di 3:1 degli utenti VoIP per gli utenti connessi con la chiamata.</span><span class="sxs-lookup"><span data-stu-id="84cfd-238">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="84cfd-239">solo audio VoIP per 35%.</span><span class="sxs-lookup"><span data-stu-id="84cfd-239">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="84cfd-240">solo audio per conferenze telefoniche con accesso esterno per il 15%.</span><span class="sxs-lookup"><span data-stu-id="84cfd-240">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="84cfd-241">10% Nessun audio (conferenze di messaggistica istantanea con una media di cinque messaggi inviati per ogni utente).</span><span class="sxs-lookup"><span data-stu-id="84cfd-241">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-242">Combinazione multimediale per le conferenze</span><span class="sxs-lookup"><span data-stu-id="84cfd-242">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="84cfd-243">75% delle conferenze sono conferenze Web, che includono l'audio e altre modalità di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="84cfd-243">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="84cfd-244">Per queste conferenze, gli altri metodi di collaborazione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="84cfd-244">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="84cfd-245">Questi numeri sommano più di 100% perché una conferenza può avere più metodi di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="84cfd-245">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="84cfd-246">50% Aggiungi condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="84cfd-246">50% add application sharing.</span></span> <span data-ttu-id="84cfd-247">Supponiamo che un utente invii i dati a un massimo di 1,1 MB al secondo.</span><span class="sxs-lookup"><span data-stu-id="84cfd-247">We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="84cfd-248">50% aggiungere la messaggistica istantanea (con una media di 2 messaggi per utente).</span><span class="sxs-lookup"><span data-stu-id="84cfd-248">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="84cfd-249">20% aggiungere la collaborazione ai dati, tra cui PowerPoint o lavagna in questi, una media di 2 file di PowerPoint presentati per conferenza, con una dimensione media di file di PowerPoint di 10 MB (senza video incorporato) o 30 MB (con video incorporato).</span><span class="sxs-lookup"><span data-stu-id="84cfd-249">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video).</span></span> <span data-ttu-id="84cfd-250">Media di 20 annotazioni per lavagna.</span><span class="sxs-lookup"><span data-stu-id="84cfd-250">Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="84cfd-251">aggiungere un video del 20%.</span><span class="sxs-lookup"><span data-stu-id="84cfd-251">20% add video.</span></span> <span data-ttu-id="84cfd-252">Di questi utenti, 70% sono in conferenze abilitate per il video MultiView, in cui ogni utente riceve i flussi video di 2-3.</span><span class="sxs-lookup"><span data-stu-id="84cfd-252">Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="84cfd-253">15% aggiungere note condivise.</span><span class="sxs-lookup"><span data-stu-id="84cfd-253">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-254">Distribuzione di partecipanti alla riunione</span><span class="sxs-lookup"><span data-stu-id="84cfd-254">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="84cfd-255">50% utenti interni e autenticati.</span><span class="sxs-lookup"><span data-stu-id="84cfd-255">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="84cfd-256">25% di accesso remoto, utenti autenticati.</span><span class="sxs-lookup"><span data-stu-id="84cfd-256">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="84cfd-257">15% utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="84cfd-257">15% anonymous users.</span></span></p>
<p><span data-ttu-id="84cfd-258">10% utenti federati.</span><span class="sxs-lookup"><span data-stu-id="84cfd-258">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-259">Distribuzione di join di riunione</span><span class="sxs-lookup"><span data-stu-id="84cfd-259">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="84cfd-260">Gli utenti vengono simulati per partecipare alla riunione entro i primi 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-260">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="84cfd-261">Nei pool di front end regolari Lync Server 2013 ha una dimensione di riunione massima supportata di 250 utenti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-261">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="84cfd-262">Ogni pool può ospitare 1 250-riunione utente alla volta.</span><span class="sxs-lookup"><span data-stu-id="84cfd-262">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="84cfd-263">Mentre si verifica questa riunione di grandi dimensioni, il pool può ospitare anche altre conferenze più piccole.</span><span class="sxs-lookup"><span data-stu-id="84cfd-263">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="84cfd-264">Inoltre, puoi supportare riunioni fino a 1000 utenti impostando un pool dedicato per ospitare queste riunioni.</span><span class="sxs-lookup"><span data-stu-id="84cfd-264">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="84cfd-265">Per informazioni dettagliate, vedere [supporto per riunioni di grandi dimensioni in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="84cfd-265">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="84cfd-266">Le conferenze sono state simulate nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="84cfd-266">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="84cfd-267">il 85% delle conferenze ha quattro partecipanti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-267">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="84cfd-268">il 10% delle conferenze ha sei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-268">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="84cfd-269">il 5% delle conferenze ha 11 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-269">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="84cfd-270">Una conferenza di grandi dimensioni per gli utenti di 250.</span><span class="sxs-lookup"><span data-stu-id="84cfd-270">One large conference of 250 users.</span></span>

<span data-ttu-id="84cfd-271">La tabella seguente fornisce informazioni dettagliate sul modello di utente per le conferenze che coinvolgono utenti con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="84cfd-271">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="84cfd-272">Modello utenti di servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="84cfd-272">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84cfd-273">Categoria</span><span class="sxs-lookup"><span data-stu-id="84cfd-273">Category</span></span></th>
<th><span data-ttu-id="84cfd-274">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84cfd-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-275">Autenticato/Anonimo</span><span class="sxs-lookup"><span data-stu-id="84cfd-275">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="84cfd-276">il 70% dei chiamanti si iscrive come anonimo e viene richiesto un nome registrato.</span><span class="sxs-lookup"><span data-stu-id="84cfd-276">70% of callers join as anonymous and are prompted for a recorded name.</span></span> <span data-ttu-id="84cfd-277">30% partecipa come utenti autenticati.</span><span class="sxs-lookup"><span data-stu-id="84cfd-277">30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-278">Durata chiamata e musica in attesa</span><span class="sxs-lookup"><span data-stu-id="84cfd-278">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="84cfd-279">Durata media della chiamata senza musica in attesa: 50 secondi.</span><span class="sxs-lookup"><span data-stu-id="84cfd-279">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="84cfd-280">per una media di 5 minuti, 50% degli utenti di chiamate in attesa sente musica in sospeso.</span><span class="sxs-lookup"><span data-stu-id="84cfd-280">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-281">DTMF (Dual-Tone Multifrequency)</span><span class="sxs-lookup"><span data-stu-id="84cfd-281">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="84cfd-282">il 15% delle conferenze telefoniche con accesso esterno ha solo i responsabili del telefono.</span><span class="sxs-lookup"><span data-stu-id="84cfd-282">15% of conferences that are dial-in only have phone leaders.</span></span> <span data-ttu-id="84cfd-283">il 10% delle conferenze miste che includono utenti con accesso esterno hanno anche i responsabili del telefono.</span><span class="sxs-lookup"><span data-stu-id="84cfd-283">10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="84cfd-284">il 20% dei responsabili telefonici USA 2 comandi DTMF per conferenza.</span><span class="sxs-lookup"><span data-stu-id="84cfd-284">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-285">Lingue di annunci</span><span class="sxs-lookup"><span data-stu-id="84cfd-285">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="84cfd-286">Le simulazioni usano l'inglese come lingua di annuncio.</span><span class="sxs-lookup"><span data-stu-id="84cfd-286">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="84cfd-287">La tabella seguente fornisce informazioni dettagliate sul modello di utente per le lobby delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="84cfd-287">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="84cfd-288">Modello di utente di lobby conferenza</span><span class="sxs-lookup"><span data-stu-id="84cfd-288">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84cfd-289">Categoria</span><span class="sxs-lookup"><span data-stu-id="84cfd-289">Category</span></span></th>
<th><span data-ttu-id="84cfd-290">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84cfd-290">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-291">Numero di utenti nella sala di attesa</span><span class="sxs-lookup"><span data-stu-id="84cfd-291">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="84cfd-292">il 5% degli utenti con accesso esterno passa attraverso la sala d'attesa e il 25% degli altri utenti passa attraverso la sala d'attesa</span><span class="sxs-lookup"><span data-stu-id="84cfd-292">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-293">Ammissione dalla sala di attesa</span><span class="sxs-lookup"><span data-stu-id="84cfd-293">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="84cfd-294">In simulazioni tutti gli utenti sono stati ammessi dal relatore prima del timeout del client.</span><span class="sxs-lookup"><span data-stu-id="84cfd-294">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="84cfd-295">La tabella seguente descrive il modello di utente per altre sessioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="84cfd-295">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="84cfd-296">Modello utente sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="84cfd-296">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84cfd-297">Categoria</span><span class="sxs-lookup"><span data-stu-id="84cfd-297">Category</span></span></th>
<th><span data-ttu-id="84cfd-298">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84cfd-298">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-299">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="84cfd-299">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="84cfd-300">Ogni utente partecipa a 5 sessioni di condivisione delle applicazioni peer-to-peer al mese, per una media di 0,25 sessioni al giorno.</span><span class="sxs-lookup"><span data-stu-id="84cfd-300">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-301">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="84cfd-301">File transfer</span></span></p></td>
<td><p><span data-ttu-id="84cfd-302">Ogni utente partecipa a una sessione di trasferimento di file peer-to-peer al mese (nell'ambito di una sessione di messaggistica istantanea), per una media di 0,05 sessioni al giorno.</span><span class="sxs-lookup"><span data-stu-id="84cfd-302">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day.</span></span> <span data-ttu-id="84cfd-303">La dimensione media del file della sessione trasferita è di 1 MB.</span><span class="sxs-lookup"><span data-stu-id="84cfd-303">The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="84cfd-304">La tabella seguente descrive il modello di utente per i criteri.</span><span class="sxs-lookup"><span data-stu-id="84cfd-304">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="84cfd-305">Modello di criteri utente</span><span class="sxs-lookup"><span data-stu-id="84cfd-305">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84cfd-306">Categoria</span><span class="sxs-lookup"><span data-stu-id="84cfd-306">Category</span></span></th>
<th><span data-ttu-id="84cfd-307">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84cfd-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84cfd-308">Criteri di conferenza, presenza e archiviazione</span><span class="sxs-lookup"><span data-stu-id="84cfd-308">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="84cfd-309">Supponiamo che esistano un criterio globale, 10 criteri di conferenza tag, 4 criteri di archiviazione e 10 criteri di presenza dei tag.</span><span class="sxs-lookup"><span data-stu-id="84cfd-309">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84cfd-310">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="84cfd-310">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="84cfd-311">Supponiamo che esistano un criterio globale e due criteri per i tag per sito.</span><span class="sxs-lookup"><span data-stu-id="84cfd-311">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="84cfd-312">il 100% dei siti ha un criterio per il sito e il 30% degli utenti ha un criterio per utente assegnato.</span><span class="sxs-lookup"><span data-stu-id="84cfd-312">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="84cfd-313">Assumiamo un dial plan per ogni sito e due rotte per sito.</span><span class="sxs-lookup"><span data-stu-id="84cfd-313">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="84cfd-314">Ora occupato</span><span class="sxs-lookup"><span data-stu-id="84cfd-314">Busy Hour</span></span>

<span data-ttu-id="84cfd-315">Per le sessioni peer-to-peer, il carico di picco viene calcolato usando i tentativi di chiamata di ora occupato (BHCA).</span><span class="sxs-lookup"><span data-stu-id="84cfd-315">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA).</span></span> <span data-ttu-id="84cfd-316">Questo termine del settore vocale presuppone che il 50% di tutte le chiamate per il giorno verrà completato in 20% del tempo.</span><span class="sxs-lookup"><span data-stu-id="84cfd-316">This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time.</span></span> <span data-ttu-id="84cfd-317">Viene calcolata usando la formula seguente:</span><span class="sxs-lookup"><span data-stu-id="84cfd-317">It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="84cfd-318">Test delle prestazioni ora di occupato simulato eseguendo VoIP e altre sessioni peer-to-peer a un carico di ora occupato per almeno 1,6 ore al giorno.</span><span class="sxs-lookup"><span data-stu-id="84cfd-318">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="84cfd-319">Il carico di picco per i servizi di conferenza presuppone che il 75% di tutte le conferenze per un giorno di otto ore avvenga in quattro ore di punta.</span><span class="sxs-lookup"><span data-stu-id="84cfd-319">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours.</span></span> <span data-ttu-id="84cfd-320">Le ore di punta hanno 1,5 volte il carico di conferenza media.</span><span class="sxs-lookup"><span data-stu-id="84cfd-320">Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="84cfd-321">VoIP aziendale per chiamate PSTN</span><span class="sxs-lookup"><span data-stu-id="84cfd-321">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="84cfd-322">Le ipotesi seguenti si applicano alle chiamate vocali aziendali:</span><span class="sxs-lookup"><span data-stu-id="84cfd-322">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="84cfd-323">50% degli utenti sono abilitati per VoIP aziendale e il 60% di questi utenti è abilitato per le chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="84cfd-323">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="84cfd-324">Ognuno di questi utenti abilitato per la chiamata PSTN effettua 4 chiamate PSTN durante l'ora di occupato.</span><span class="sxs-lookup"><span data-stu-id="84cfd-324">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour.</span></span> <span data-ttu-id="84cfd-325">Ogni durata della chiamata è di 3 minuti.</span><span class="sxs-lookup"><span data-stu-id="84cfd-325">Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="84cfd-326">65% di queste chiamate vocali PSTN usano il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="84cfd-326">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="84cfd-327">Mobilità</span><span class="sxs-lookup"><span data-stu-id="84cfd-327">Mobility</span></span>

<span data-ttu-id="84cfd-328">si presume che il 40% degli utenti registrati sia abilitato per la mobilità.</span><span class="sxs-lookup"><span data-stu-id="84cfd-328">40% of registered users are assumed to be enabled for Mobility.</span></span> <span data-ttu-id="84cfd-329">Per ogni utente abilitato alla mobilità, supponiamo che l'attività del client per dispositivi mobili sia additiva rispetto alle altre istanze di MPOP per tale utente, ad eccezione delle interazioni di conferenza, per cui il client di mobilità è solo un altro tipo di client che può essere usato per partecipare alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="84cfd-329">For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="84cfd-330">Chat persistente</span><span class="sxs-lookup"><span data-stu-id="84cfd-330">Persistent Chat</span></span>

<span data-ttu-id="84cfd-331">Presupponiamo che il 25% degli utenti registrati sarà coinvolto in sessioni di chat persistenti, con le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="84cfd-331">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="84cfd-332">Media delle chat room di 1,5 per utente</span><span class="sxs-lookup"><span data-stu-id="84cfd-332">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="84cfd-333">Ogni chat room genera 12 richieste di polling per ora, destinate a una media di 10 utenti ogni</span><span class="sxs-lookup"><span data-stu-id="84cfd-333">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="84cfd-334">Gruppo di risposte e parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="84cfd-334">Response Group and Call Park</span></span>

<span data-ttu-id="84cfd-335">Supponiamo che il 0,15% degli utenti registrati appartenga ai gruppi di risposta.</span><span class="sxs-lookup"><span data-stu-id="84cfd-335">We assume that 0.15% of registered users belong to response groups.</span></span> <span data-ttu-id="84cfd-336">Supponiamo che il 0,02% degli utenti registrati abbia chiamate parcheggiate in un dato momento.</span><span class="sxs-lookup"><span data-stu-id="84cfd-336">We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

