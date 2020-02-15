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
ms.openlocfilehash: cec912d84859baf77363764851d7abd1592b2760
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="116f0-102">Modelli utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="116f0-102">User models in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="116f0-103">_**Ultimo argomento modificato:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="116f0-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="116f0-104">I modelli utente descritti di seguito forniscono la base per le misure di pianificazione della capacità e i suggerimenti descritti nella [pianificazione della capacità di Lync Server 2013 utilizzando i modelli utente](lync-server-2013-capacity-planning-using-the-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="116f0-104">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="116f0-105">Modelli utente di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="116f0-105">Lync Server 2013 User Models</span></span>

<span data-ttu-id="116f0-106">Nella tabella seguente viene descritto il modello utente per la registrazione, i contatti, la messaggistica istantanea (IM) e la presenza per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="116f0-106">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="116f0-107">Modello utente per ambiente e registrazione</span><span class="sxs-lookup"><span data-stu-id="116f0-107">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116f0-108">Categoria</span><span class="sxs-lookup"><span data-stu-id="116f0-108">Category</span></span></th>
<th><span data-ttu-id="116f0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="116f0-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116f0-110">Dimensione e distribuzione</span><span class="sxs-lookup"><span data-stu-id="116f0-110">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="116f0-111">Viene creato un modello di distribuzione estesa con tre siti centrali e un pool Front End per sito.</span><span class="sxs-lookup"><span data-stu-id="116f0-111">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-112">Percentuale di utenti di Active Directory</span><span class="sxs-lookup"><span data-stu-id="116f0-112">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="116f0-113">Si presuppone che il 70% di tutti gli utenti di Active Directory nell'organizzazione sia abilitato per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="116f0-113">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="116f0-114">80% di tali utenti abilitati sono connessi a Lync Server ogni giorno (80% Concurrency).</span><span class="sxs-lookup"><span data-stu-id="116f0-114">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="116f0-115">Gli utenti simultanei rappresentano la base per i valori indicati nel resto di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="116f0-115">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116f0-116">Cambiamenti in Active Directory</span><span class="sxs-lookup"><span data-stu-id="116f0-116">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="116f0-117">Si presuppone che il 0,5% del totale degli utenti siano stati creati e abilitati per Lync in Active Directory ogni settimana e che il 0,5% del totale degli utenti sia disabilitato da Active Directory e da Lync ogni settimana.</span><span class="sxs-lookup"><span data-stu-id="116f0-117">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="116f0-118">Per il 5% degli utenti viene modificato almeno un attributo di Active Directory ogni settimana.</span><span class="sxs-lookup"><span data-stu-id="116f0-118">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-119">Gruppi di distribuzione di Active Directory</span><span class="sxs-lookup"><span data-stu-id="116f0-119">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="116f0-p103">Si parte dal presupposto che il numero di gruppi di distribuzione di Active Directory nell'organizzazione sia pari a tre volte il numero di tutti gli utenti in Active Directory. Le dimensioni dei gruppi di distribuzione sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="116f0-p103">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory. The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="116f0-122">64% con 2-30 utenti</span><span class="sxs-lookup"><span data-stu-id="116f0-122">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="116f0-123">13% con 31-50 utenti</span><span class="sxs-lookup"><span data-stu-id="116f0-123">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="116f0-124">10% con 51-100 utenti</span><span class="sxs-lookup"><span data-stu-id="116f0-124">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="116f0-125">13% con 101-500 utenti</span><span class="sxs-lookup"><span data-stu-id="116f0-125">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116f0-126">Utenti di VoIP (Voice over IP)</span><span class="sxs-lookup"><span data-stu-id="116f0-126">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="116f0-127">60% degli utenti di Lync Server sono abilitati per le comunicazioni unificate (ovvero i numeri di telefono sono di proprietà di Lync Server).</span><span class="sxs-lookup"><span data-stu-id="116f0-127">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-128">Distribuzione dei client registrati</span><span class="sxs-lookup"><span data-stu-id="116f0-128">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="116f0-129">il 65% dei client esegue il software Lync 2013, tra cui Lync e Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="116f0-129">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="116f0-130">30% dei client che eseguono il software client da una versione precedente di Lync.</span><span class="sxs-lookup"><span data-stu-id="116f0-130">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="116f0-131">5% di client che utilizzano Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="116f0-131">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="116f0-132">Se la mobilità è abilitata, si presuppone che il 40% degli utenti utilizzi la mobilità contemporaneamente alle altre opzioni client registrate precedentemente citate.</span><span class="sxs-lookup"><span data-stu-id="116f0-132">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options.</span></span> <span data-ttu-id="116f0-133">In questo caso, il rapporto più punti di presenza del client (MPOP) è 1:1.9.</span><span class="sxs-lookup"><span data-stu-id="116f0-133">In this case the client multiple point of presence (MPOP) ratio is 1:1.9.</span></span> <span data-ttu-id="116f0-134">Se l'utilizzo dei dispositivi mobili è disabilitato, il rapporto MPOP invece è pari a 1:1,5.</span><span class="sxs-lookup"><span data-stu-id="116f0-134">If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116f0-135">Distribuzione degli utenti remoti</span><span class="sxs-lookup"><span data-stu-id="116f0-135">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="116f0-136">Il 70% degli utenti si connette internamente.</span><span class="sxs-lookup"><span data-stu-id="116f0-136">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="116f0-137">Il 30% degli utenti si connette tramite un server perimetrale e un server Director.</span><span class="sxs-lookup"><span data-stu-id="116f0-137">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-138">Distribuzione dei contatti</span><span class="sxs-lookup"><span data-stu-id="116f0-138">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="116f0-p105">Il numero massimo di contatti di cui può disporre un utente è 1.000. Meno dell'1% degli utenti dispone di 1.000 contatti. Meno del 25% degli utenti dispone di 100 o più contatti.</span><span class="sxs-lookup"><span data-stu-id="116f0-p105">The maximum number of contacts a user has is 1,000. Less than 1% of users have 1,000 contacts. Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="116f0-p106">Media di 80 contatti per gli utenti con connettività a cloud pubblici. Di questi utenti:</span><span class="sxs-lookup"><span data-stu-id="116f0-p106">Average of 80 contacts for users with public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="116f0-p107">Il 50% dei contatti è all'interno dell'organizzazione. Il 10% di questi utenti è rappresentato da utenti remoti che si connettono dall'esterno del firewall.</span><span class="sxs-lookup"><span data-stu-id="116f0-p107">50% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="116f0-146">Il 40% dei contatti è rappresentato da utenti di cloud pubblici, ad esempio AOL, Yahoo!, MSN o Google Talk.</span><span class="sxs-lookup"><span data-stu-id="116f0-146">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="116f0-147">Il 10% dei contatti proviene da partner federati.</span><span class="sxs-lookup"><span data-stu-id="116f0-147">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="116f0-148">Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="116f0-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="116f0-149">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="116f0-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="116f0-150">Messenger fino alla data di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="116f0-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="116f0-151">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="116f0-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="116f0-152">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="116f0-152">has been announced.</span></span> <span data-ttu-id="116f0-153">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="116f0-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="116f0-154">Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="116f0-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="116f0-155">Messaggero.</span><span class="sxs-lookup"><span data-stu-id="116f0-155">Messenger.</span></span> <span data-ttu-id="116f0-156">La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</span><span class="sxs-lookup"><span data-stu-id="116f0-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="116f0-157">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="116f0-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="116f0-158">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="116f0-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="116f0-159">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="116f0-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="116f0-p111">Media di 50 contatti per gli utenti senza connettività a cloud pubblici. Di questi utenti:</span><span class="sxs-lookup"><span data-stu-id="116f0-p111">Average of 50 contacts for users without public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="116f0-p112">L'80% dei contatti è all'interno dell'organizzazione. Il 10% di questi utenti è rappresentato da utenti remoti che si connettono dall'esterno del firewall.</span><span class="sxs-lookup"><span data-stu-id="116f0-p112">80% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="116f0-164">Il 20% dei contatti proviene da partner federati.</span><span class="sxs-lookup"><span data-stu-id="116f0-164">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="116f0-p113">Ogni utente dispone di un gruppo di distribuzione nell'elenco contatti. Per i test delle prestazioni, si presuppone che i gruppi di distribuzione siano sempre espansi.</span><span class="sxs-lookup"><span data-stu-id="116f0-p113">Each user has 1 distribution group in their contact list. For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="116f0-167">Il 25% dei contatti di un utente utilizza XMPP.</span><span class="sxs-lookup"><span data-stu-id="116f0-167">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116f0-168">Durata delle sessioni</span><span class="sxs-lookup"><span data-stu-id="116f0-168">Session time</span></span></p></td>
<td><p><span data-ttu-id="116f0-p114">La sessione di accesso utente dura in media 12 ore. Tutti gli utenti eseguono l'accesso entro 120 minuti dall'avvio della sessione.</span><span class="sxs-lookup"><span data-stu-id="116f0-p114">The average user logon session lasts 12 hours. All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="116f0-171">Modello utente per messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="116f0-171">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116f0-172">Categoria</span><span class="sxs-lookup"><span data-stu-id="116f0-172">Category</span></span></th>
<th><span data-ttu-id="116f0-173">Descrizione</span><span class="sxs-lookup"><span data-stu-id="116f0-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116f0-174">Sessioni di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="116f0-174">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="116f0-175">Ogni utente esegue in media sei sessioni di messaggistica istantanea peer-to-peer al giorno.</span><span class="sxs-lookup"><span data-stu-id="116f0-175">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="116f0-176">10 messaggi istantanei per sessione.</span><span class="sxs-lookup"><span data-stu-id="116f0-176">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="116f0-177">Ogni messaggio è associato a due messaggi di informazioni SIP e 2 messaggi SIP 200 OK (per gli indicatori di stato, ad&lt;esempio&gt; "nome digitando")</span><span class="sxs-lookup"><span data-stu-id="116f0-177">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-178">Polling della presenza</span><span class="sxs-lookup"><span data-stu-id="116f0-178">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="116f0-p115">In generale, si presuppongono 60 polling di presenza per utente all'ora. Per ogni utente si presuppone una media di:</span><span class="sxs-lookup"><span data-stu-id="116f0-p115">Overall, we assume presence polling at an average of 60 polls per user per hour. For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="116f0-p116">Un polling al giorno della presenza degli utenti nella scheda dell'organizzazione dell'utente, ma non nell'elenco Contatti. Il numero medio di utenti non contatti nella scheda dell'organizzazione dell'utente è di 15 utenti. Due operazioni di visualizzazione di schede contatto al giorno.</span><span class="sxs-lookup"><span data-stu-id="116f0-p116">One poll per day of the presence of users in the user’s organization tab (but not Contacts list). Average number of non-contacts in the user’s organization tab is 15 users. Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="116f0-184">Un polling di presenza ogni volta che l'utente fa clic su un altro per avviare una conversazione, con frequenza stimata di una volta all'ora.</span><span class="sxs-lookup"><span data-stu-id="116f0-184">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="116f0-p117">Sei ricerche utente all'ora. Ogni volta che viene eseguita una ricerca, viene inviato un polling batch per ogni utente nell'elenco dei risultati della ricerca. Si presuppone che la dimensione media dei risultati della ricerca sia di 20 utenti. Se i risultati della ricerca restano visualizzati sullo schermo, il polling batch viene aggiornato ogni cinque minuti. Si presuppongono due aggiornamenti di questo tipo all'ora.</span><span class="sxs-lookup"><span data-stu-id="116f0-p117">Six user searches per hour. Every time a search is performed, a batch poll is sent for everyone in the search result list. We assume the average size of search results is 20. If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="116f0-189">Quando l'utente apre un messaggio di posta elettronica in Outlook o lo visualizza in anteprima, un polling della presenza per gli utenti nei campi A e Cc del messaggio di posta elettronica, con valori stimati di cinque messaggi di posta elettronica all'ora e quattro utenti per ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="116f0-189">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116f0-190">Sottoscrizioni della presenza</span><span class="sxs-lookup"><span data-stu-id="116f0-190">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="116f0-p118">Quando un utente ne aggiunge un altro come contatto, il primo utente <em>sottoscrive</em> cinque categorie di informazioni sul secondo utente. Gli aggiornamenti di queste categorie di informazioni vengono inviati automaticamente al primo utente.</span><span class="sxs-lookup"><span data-stu-id="116f0-p118">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user. Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="116f0-193">Per ogni client, viene inviata una singola richiesta di sottoscrizione batch per ottenere lo stato di presenza di una media di 40 contatti, con ulteriori 40 finestre di dialogo per ottenere la presenza dei contatti federati.</span><span class="sxs-lookup"><span data-stu-id="116f0-193">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="116f0-194">Le informazioni sulla presenza per i membri di un gruppo di distribuzione espanso vengono trovate mediante sottoscrizioni della presenza persistenti e non mediante il polling. Il modello prevede un'espansione per utente ogni due ore.</span><span class="sxs-lookup"><span data-stu-id="116f0-194">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="116f0-p119">Le <em>sottoscrizioni brevi</em> si verificano quando un utente esegue l'accesso, viene eseguita una sottoscrizione batch per tutti i contatti dell'utente e quindi l'utente si disconnette. Si presuppongono sei sottoscrizioni brevi per utente all'ora, ognuna della durata di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="116f0-p119"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off. We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-197">Pubblicazione della presenza</span><span class="sxs-lookup"><span data-stu-id="116f0-197">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="116f0-198">Lo stato di presenza viene pubblicato con una media di quattro pubblicazioni per utente all'ora, con un massimo di sei pubblicazioni per utente all'ora.</span><span class="sxs-lookup"><span data-stu-id="116f0-198">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116f0-199">Dimensione del documento delle informazioni sulla presenza</span><span class="sxs-lookup"><span data-stu-id="116f0-199">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="116f0-200">Si presuppone che la dimensione media di un documento completo di informazioni sulla presenza corrisponda a 4 K, fino a un massimo di 25 K.</span><span class="sxs-lookup"><span data-stu-id="116f0-200">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="116f0-201">Nella tabella riportata di seguito viene descritto il modello utente per l'utilizzo della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="116f0-201">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="116f0-202">Modello utente per l'utilizzo della Rubrica</span><span class="sxs-lookup"><span data-stu-id="116f0-202">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116f0-203">Modalità di ricerca nella Rubrica</span><span class="sxs-lookup"><span data-stu-id="116f0-203">Address Book search mode</span></span></th>
<th><span data-ttu-id="116f0-204">Usage</span><span class="sxs-lookup"><span data-stu-id="116f0-204">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116f0-205">Solo query Web nella Rubrica (tutte le query eseguite dal servizio Address Book Web Query)</span><span class="sxs-lookup"><span data-stu-id="116f0-205">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="116f0-206">Quattro query di prefisso per utente al giorno.</span><span class="sxs-lookup"><span data-stu-id="116f0-206">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="116f0-p120">60 query di ricerca esatta per utente al giorno. Il 40% di queste è eseguito in batch, con una media di 20 contatti per query. L'altro 60% delle query è per un singolo contatto.</span><span class="sxs-lookup"><span data-stu-id="116f0-p120">60 exact search queries per user per day. 40% of those are batched, with an average of 20 contacts per query. The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="116f0-p121">25 query di foto per utente al giorno. 24 per una singola foto, l'altra è una query in batch con una media di 20 contatti.</span><span class="sxs-lookup"><span data-stu-id="116f0-p121">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="116f0-212">Una query di ricerca in tutta l'organizzazione per utente al giorno.</span><span class="sxs-lookup"><span data-stu-id="116f0-212">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-p122">Modalità mista con utilizzo sia di query nel file della Rubrica che di query Web. Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="116f0-p122">Mixed mode, both address book file and web queries used. This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="116f0-215">Solo due tipi di query vanno in rete, ovvero le query di ricerca di foto e quelle di ricerca in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="116f0-215">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="116f0-p123">25 query di foto per utente al giorno. 24 per una singola foto, l'altra è una query in batch con una media di 20 contatti.</span><span class="sxs-lookup"><span data-stu-id="116f0-p123">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="116f0-218">Una query di ricerca in tutta l'organizzazione per utente al giorno.</span><span class="sxs-lookup"><span data-stu-id="116f0-218">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="116f0-219">Nella tabella seguente viene descritto il modello per i servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="116f0-219">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="116f0-220">Modello per i servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="116f0-220">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116f0-221">Categoria</span><span class="sxs-lookup"><span data-stu-id="116f0-221">Category</span></span></th>
<th><span data-ttu-id="116f0-222">Descrizione</span><span class="sxs-lookup"><span data-stu-id="116f0-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116f0-223">&quot;Riunioni pianificate e riunioni&quot; risalenti a oggi</span><span class="sxs-lookup"><span data-stu-id="116f0-223">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="116f0-224">60% pianificate, 40% non pianificate.</span><span class="sxs-lookup"><span data-stu-id="116f0-224">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="116f0-225">Delle riunioni pianificate, si presuppone che l'80% corrisponda a conferenze assegnate, ovvero occorrenze di conferenze ricorrenti, il 10% corrisponda a riunioni aperte occasionali, l'8% corrisponda a riunioni anonime occasionali e il 2% corrisponda a riunioni chiuse occasionali.</span><span class="sxs-lookup"><span data-stu-id="116f0-225">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-226">Distribuzione dei client per i servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="116f0-226">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="116f0-227">Per le riunioni pianificate:</span><span class="sxs-lookup"><span data-stu-id="116f0-227">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="116f0-228">65% di utenti di conferenze utilizzano Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="116f0-228">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="116f0-229">5% di utenti di conferenze utilizzano Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="116f0-229">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="116f0-230">il 30% degli utenti di servizi di conferenza utilizza client precedenti, tra cui Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 e Microsoft Office Communicator Web Access (versione 2007).</span><span class="sxs-lookup"><span data-stu-id="116f0-230">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="116f0-231">Per le riunioni non pianificate:</span><span class="sxs-lookup"><span data-stu-id="116f0-231">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="116f0-232">70% di utenti di conferenze utilizzano Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="116f0-232">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="116f0-233">il 30% degli utenti di servizi di conferenza utilizza client precedenti, tra cui Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 e Microsoft Office Communicator Web Access (versione 2007).</span><span class="sxs-lookup"><span data-stu-id="116f0-233">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116f0-234">Concorrenza riunione</span><span class="sxs-lookup"><span data-stu-id="116f0-234">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="116f0-p124">Il 5% degli utenti sarà in conferenza durante le ore lavorative. Per un pool di 80.000 utenti, pertanto, fino a 4.000 utenti potrebbe essere in conferenza contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="116f0-p124">5% of users will be in conferences during working hours. Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-237">Distribuzione dell'audio delle riunioni</span><span class="sxs-lookup"><span data-stu-id="116f0-237">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="116f0-238">40% misto di audio VoIP e conferenza telefonica con accesso esterno, con un rapporto di 3:1 di utenti VoIP rispetto agli utenti connessi tramite chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="116f0-238">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="116f0-239">35% solo audio VoIP.</span><span class="sxs-lookup"><span data-stu-id="116f0-239">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="116f0-240">15% solo audio di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="116f0-240">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="116f0-241">10% senza audio (conferenze solo con messaggi istantanei, con una media di cinque messaggi inviati per utente).</span><span class="sxs-lookup"><span data-stu-id="116f0-241">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116f0-242">Combinazioni multimediali per le conferenze</span><span class="sxs-lookup"><span data-stu-id="116f0-242">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="116f0-243">Il 75% delle conferenze è rappresentato da conferenze Web, che includono funzionalità audio e altre modalità di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="116f0-243">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="116f0-244">Per queste conferenze, gli altri metodi di collaborazione sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="116f0-244">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="116f0-245">La somma di questi numeri è maggiore del 100% perché in una conferenza si possono utilizzare più metodi di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="116f0-245">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="116f0-p125">Nel 50% viene aggiunta la condivisione di applicazioni. Si presuppone che un utente invii dati fino a un massimo di 1,1 MB al secondo.</span><span class="sxs-lookup"><span data-stu-id="116f0-p125">50% add application sharing. We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="116f0-248">Nel 50% viene aggiunta la messaggistica istantanea (con una media di due messaggi per utente).</span><span class="sxs-lookup"><span data-stu-id="116f0-248">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="116f0-p126">Nel 20% viene aggiunta la collaborazione dati, inclusi PowerPoint o una lavagna. In questo gruppo in media vengono presentati due file di PowerPoint per conferenza, con una dimensione media dei file di PowerPoint di 10 MB (senza video incorporato) o di 30 MB (con video incorporato). Sono presenti in media 20 annotazioni per lavagna.</span><span class="sxs-lookup"><span data-stu-id="116f0-p126">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video). Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="116f0-p127">Nel 20% viene aggiunto il video. Di questi utenti, il 70% partecipa a conferenze abilitate per il video multiview, in cui ogni utente riceve 2-3 flussi video.</span><span class="sxs-lookup"><span data-stu-id="116f0-p127">20% add video. Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="116f0-253">Nel 15% vengono aggiunte note condivise.</span><span class="sxs-lookup"><span data-stu-id="116f0-253">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-254">Distribuzione dei partecipanti alle riunioni</span><span class="sxs-lookup"><span data-stu-id="116f0-254">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="116f0-255">50% utenti interni autenticati.</span><span class="sxs-lookup"><span data-stu-id="116f0-255">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="116f0-256">25% utenti autenticati con accesso remoto.</span><span class="sxs-lookup"><span data-stu-id="116f0-256">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="116f0-257">15% utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="116f0-257">15% anonymous users.</span></span></p>
<p><span data-ttu-id="116f0-258">10% utenti federati.</span><span class="sxs-lookup"><span data-stu-id="116f0-258">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116f0-259">Distribuzione della partecipazione alle riunioni</span><span class="sxs-lookup"><span data-stu-id="116f0-259">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="116f0-260">Si presuppone la partecipazione degli utenti alla riunione entro i primi cinque minuti.</span><span class="sxs-lookup"><span data-stu-id="116f0-260">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="116f0-261">In pool Front End regolari, Lync Server 2013 ha una dimensione massima di riunioni supportate di 250 utenti.</span><span class="sxs-lookup"><span data-stu-id="116f0-261">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="116f0-262">Ogni pool può ospitare una riunione da 250 utenti per volta.</span><span class="sxs-lookup"><span data-stu-id="116f0-262">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="116f0-263">Mentre è in corso una riunione di dimensioni così elevate, il pool può ospitare anche altre conferenze più ridotte.</span><span class="sxs-lookup"><span data-stu-id="116f0-263">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="116f0-264">È inoltre possibile supportare riunioni a cui partecipano fino a 1000 utenti configurando un pool dedicato per ospitare tali riunioni.</span><span class="sxs-lookup"><span data-stu-id="116f0-264">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="116f0-265">Per informazioni dettagliate, vedere [supporto per le riunioni di grandi dimensioni in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="116f0-265">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="116f0-266">Sono state simulate le conferenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="116f0-266">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="116f0-267">85% di conferenze con quattro partecipanti.</span><span class="sxs-lookup"><span data-stu-id="116f0-267">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="116f0-268">10% di conferenze con sei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="116f0-268">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="116f0-269">5% di conferenze con 11 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="116f0-269">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="116f0-270">Una conferenza estesa con 250 utenti.</span><span class="sxs-lookup"><span data-stu-id="116f0-270">One large conference of 250 users.</span></span>

<span data-ttu-id="116f0-271">Nella tabella seguente sono disponibili informazioni dettagliate sul modello utente per le conferenze che coinvolgono utenti connessi tramite chiamate in ingresso.</span><span class="sxs-lookup"><span data-stu-id="116f0-271">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="116f0-272">Modello utente per conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="116f0-272">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116f0-273">Categoria</span><span class="sxs-lookup"><span data-stu-id="116f0-273">Category</span></span></th>
<th><span data-ttu-id="116f0-274">Descrizione</span><span class="sxs-lookup"><span data-stu-id="116f0-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116f0-275">Autenticato/Anonimo</span><span class="sxs-lookup"><span data-stu-id="116f0-275">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="116f0-p129">Il 70% dei chiamanti partecipa in modalità anonima e deve specificare un nome registrato. Il 30% partecipa come utente autenticato.</span><span class="sxs-lookup"><span data-stu-id="116f0-p129">70% of callers join as anonymous and are prompted for a recorded name. 30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-278">Durata delle chiamate e musica di attesa</span><span class="sxs-lookup"><span data-stu-id="116f0-278">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="116f0-279">Durata media della chiamata senza musica di attesa: 50 secondi.</span><span class="sxs-lookup"><span data-stu-id="116f0-279">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="116f0-280">Il 50% degli utenti che chiamano ascoltano la musica di attesa per una media di 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="116f0-280">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116f0-281">Multifrequenza (DTMF)</span><span class="sxs-lookup"><span data-stu-id="116f0-281">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="116f0-p130">Per il 15% delle conferenze telefoniche con accesso esterno è presente un coordinatore della chiamata. Anche per il 10% delle conferenze miste che includono utenti connessi tramite chiamate in ingresso sono presenti coordinatori della chiamata.</span><span class="sxs-lookup"><span data-stu-id="116f0-p130">15% of conferences that are dial-in only have phone leaders. 10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="116f0-284">Il 20% dei coordinatori utilizza due comandi DTMF per conferenza.</span><span class="sxs-lookup"><span data-stu-id="116f0-284">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-285">Lingue degli annunci</span><span class="sxs-lookup"><span data-stu-id="116f0-285">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="116f0-286">Nelle simulazioni viene utilizzato l'inglese come lingua degli annunci.</span><span class="sxs-lookup"><span data-stu-id="116f0-286">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="116f0-287">Nella tabella seguente sono disponibili informazioni dettagliate sul modello utente per le sale di attesa delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="116f0-287">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="116f0-288">Modello utente per le sale di attesa delle conferenze</span><span class="sxs-lookup"><span data-stu-id="116f0-288">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116f0-289">Categoria</span><span class="sxs-lookup"><span data-stu-id="116f0-289">Category</span></span></th>
<th><span data-ttu-id="116f0-290">Descrizione</span><span class="sxs-lookup"><span data-stu-id="116f0-290">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116f0-291">Numero di utenti nella sala di attesa</span><span class="sxs-lookup"><span data-stu-id="116f0-291">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="116f0-292">Il 5% degli utenti che si connettono tramite chiamate in ingresso passa dalla sala di attesa, come il 25% degli altri utenti</span><span class="sxs-lookup"><span data-stu-id="116f0-292">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-293">Ammissione dalla sala di attesa</span><span class="sxs-lookup"><span data-stu-id="116f0-293">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="116f0-294">Nelle simulazioni tutti gli utenti sono stati ammessi dal relatore prima del timeout del client.</span><span class="sxs-lookup"><span data-stu-id="116f0-294">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="116f0-295">Nella tabella riportata di seguito viene descritto il modello utente per altre sessioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="116f0-295">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="116f0-296">Modello utente per altre sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="116f0-296">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116f0-297">Categoria</span><span class="sxs-lookup"><span data-stu-id="116f0-297">Category</span></span></th>
<th><span data-ttu-id="116f0-298">Descrizione</span><span class="sxs-lookup"><span data-stu-id="116f0-298">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116f0-299">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="116f0-299">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="116f0-300">Ogni utente partecipa a cinque sessioni di condivisione applicazioni peer-to-peer al mese, per una media di 0,25 sessioni al giorno.</span><span class="sxs-lookup"><span data-stu-id="116f0-300">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-301">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="116f0-301">File transfer</span></span></p></td>
<td><p><span data-ttu-id="116f0-p131">Ogni utente partecipa a 1 sessione di trasferimento file peer-to-peer al mese (nell'ambito di una sessione di messaggistica istantanea), per una media di 0,05 sessioni al giorno. Le dimensioni medie dei file trasferiti durante la sessione sono di 1 MB.</span><span class="sxs-lookup"><span data-stu-id="116f0-p131">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day. The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="116f0-304">Nella tabella seguente viene descritto il modello utente per i criteri.</span><span class="sxs-lookup"><span data-stu-id="116f0-304">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="116f0-305">Modello utente per i criteri</span><span class="sxs-lookup"><span data-stu-id="116f0-305">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116f0-306">Categoria</span><span class="sxs-lookup"><span data-stu-id="116f0-306">Category</span></span></th>
<th><span data-ttu-id="116f0-307">Descrizione</span><span class="sxs-lookup"><span data-stu-id="116f0-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116f0-308">Criteri di conferenza, presenza e archiviazione</span><span class="sxs-lookup"><span data-stu-id="116f0-308">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="116f0-309">Si presuppone che siano configurati un criterio globale, 10 criteri tag di conferenza, quattro criteri di archiviazione e 10 criteri tag di presenza.</span><span class="sxs-lookup"><span data-stu-id="116f0-309">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116f0-310">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="116f0-310">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="116f0-311">Si presuppone che esista un criterio globale e 2 criteri di tag per sito.</span><span class="sxs-lookup"><span data-stu-id="116f0-311">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="116f0-312">il 100% dei siti dispone di un criterio sito e il 30% degli utenti ha un criterio per utente assegnato.</span><span class="sxs-lookup"><span data-stu-id="116f0-312">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="116f0-313">Si presuppone un dial plan per sito e due route per sito.</span><span class="sxs-lookup"><span data-stu-id="116f0-313">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="116f0-314">Ora di punta</span><span class="sxs-lookup"><span data-stu-id="116f0-314">Busy Hour</span></span>

<span data-ttu-id="116f0-p133">Per le sessioni peer-to-peer, il carico di picco viene calcolato tramite l'indicatore dei tentativi di chiamata durante l'ora di punta, noto anche come BHCA (Busy Hour Call Attempt). Questo indicatore del settore presuppone che il 50% di tutte le chiamate in un giorno venga effettuato nel 20% del tempo. Per il calcolo viene utilizzata la formula seguente:</span><span class="sxs-lookup"><span data-stu-id="116f0-p133">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA). This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time. It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="116f0-318">Per i test delle prestazioni l'ora di punta è stata simulata eseguendo sessioni VoIP e altre sessioni peer-to-peer con un carico di picco per almeno 1,6 ore al giorno.</span><span class="sxs-lookup"><span data-stu-id="116f0-318">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="116f0-p134">Nel carico di picco per le conferenze si presuppone che il 75% di tutte le conferenze per un giorno di otto ore venga effettuato in 4 ore di punta. In tali ore di punta si concentra 1,5 volte il carico medio delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="116f0-p134">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours. Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="116f0-321">VoIP aziendale per le chiamate PSTN</span><span class="sxs-lookup"><span data-stu-id="116f0-321">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="116f0-322">Le seguenti ipotesi si applicano alle chiamate vocali di VoIP aziendale:</span><span class="sxs-lookup"><span data-stu-id="116f0-322">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="116f0-323">50% di utenti sono abilitati per VoIP aziendale e il 60% di questi utenti è abilitato per le chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="116f0-323">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="116f0-p135">Ognuno di questi utenti abilitati per le chiamate PSTN esegue quattro chiamate PSTN durante l'orario lavorativo. Ogni chiamata dura tre minuti.</span><span class="sxs-lookup"><span data-stu-id="116f0-p135">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour. Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="116f0-326">Nel 65% di queste chiamate vocali PSTN viene utilizzato il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="116f0-326">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="116f0-327">Mobilità</span><span class="sxs-lookup"><span data-stu-id="116f0-327">Mobility</span></span>

<span data-ttu-id="116f0-p136">Si presuppone che il 40% degli utenti registrati sia abilitato per i dispositivi mobili. Per ogni utente abilitato per i dispositivi mobili, si presuppone che l'attività del client mobile si aggiunga a quella delle altre istanze MPOP dell'utente, ad eccezione delle interazioni con i servizi di conferenza, per cui il client per servizi mobili rappresenta solo un altro tipo di client che può essere utilizzato per partecipare alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="116f0-p136">40% of registered users are assumed to be enabled for Mobility. For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="116f0-330">Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="116f0-330">Persistent Chat</span></span>

<span data-ttu-id="116f0-331">Si presuppone che il 25% degli utenti registrati parteciperà a sessioni di Persistent Chat, con le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="116f0-331">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="116f0-332">Una media di 1,5 chat room per utente</span><span class="sxs-lookup"><span data-stu-id="116f0-332">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="116f0-333">Ogni chat room comporta 12 richieste di polling all'ora, con una media di 10 utenti per ognuna</span><span class="sxs-lookup"><span data-stu-id="116f0-333">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="116f0-334">Response Group e parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="116f0-334">Response Group and Call Park</span></span>

<span data-ttu-id="116f0-p137">Si presuppone che lo 0,15% degli utenti registrati appartenga a Response Group e che lo 0,02% degli utenti registrati utilizzi la funzionalità di parcheggio di chiamata in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="116f0-p137">We assume that 0.15% of registered users belong to response groups. We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

