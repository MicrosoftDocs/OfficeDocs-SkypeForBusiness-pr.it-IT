---
title: 'Lync Server 2013: Elenco di tabelle di registrazione dettagli chiamata (CDR)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0c620eaf6b54a89604071a18f445d20816178bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="f5037-102">Elenco di tabelle di registrazione dettagli chiamata (CDR) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5037-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5037-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f5037-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f5037-104">Lo schema di database di registrazione dei dettagli delle chiamate (CDR) è costituito dalle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="f5037-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="f5037-105">Tabelle statiche</span><span class="sxs-lookup"><span data-stu-id="f5037-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5037-106">Tabella</span><span class="sxs-lookup"><span data-stu-id="f5037-106">Table</span></span></th>
<th><span data-ttu-id="f5037-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5037-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5037-108"><a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-109">Archivia l'elenco delle possibili priorità di chiamata, ad esempio emergenza, urgente, normale, non urgente e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="f5037-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabella ConferenceJoinTimeThresholds in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-111">Archivia i limiti di classificazione usati dal report di riepilogo dell'ora di partecipazione alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="f5037-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-112"><a href="lync-server-2013-deregistertype-table.md">Tabella DeRegisterType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-113">Archivia l'elenco dei possibili motivi di annullamento della registrazione degli utenti, &quot;ad esempio client avviati,&quot; &quot;registrazione&quot; &quot;scaduta, arresto&quot; anomalo del client e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="f5037-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-114"><a href="lync-server-2013-medialist-table.md">Tabella MediaList in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-115">Archivia l'elenco dei tipi di elementi multimediali che possono generare voci nel database, ad esempio messaggistica istantanea, audio, video e trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="f5037-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-116"><a href="lync-server-2013-purgesettings-table.md">Tabella PurgeSettings in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-117">Archivia le informazioni che specificano se (e quando) i record dettagli chiamata non aggiornati verranno eliminati automaticamente dal database CDR.</span><span class="sxs-lookup"><span data-stu-id="f5037-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-118"><a href="lync-server-2013-roles-table.md">Tabella Roles in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-119">Archivia l'elenco dei ruoli di conferenza possibili, ad esempio partecipante e relatore.</span><span class="sxs-lookup"><span data-stu-id="f5037-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Tabella SIPResponseMetaData in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-121">Archivia un elenco di codici di risposta SIP e la classificazione e la definizione di ognuno di questi codici.</span><span class="sxs-lookup"><span data-stu-id="f5037-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="f5037-122">Tabelle di supporto</span><span class="sxs-lookup"><span data-stu-id="f5037-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5037-123">Tabella</span><span class="sxs-lookup"><span data-stu-id="f5037-123">Table</span></span></th>
<th><span data-ttu-id="f5037-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5037-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5037-125"><a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-126">Archivia i client (sia il tipo di client che il numero di versione) di ogni client coinvolto in una chiamata con le informazioni acquisite in questo database.</span><span class="sxs-lookup"><span data-stu-id="f5037-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-127"><a href="lync-server-2013-conferenceuris-table.md">Tabella ConferenceUris in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-128">Archivia un elenco di ConferenceURIs usati nelle chiamate correlate alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="f5037-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-129"><a href="lync-server-2013-contenttypes-table.md">Tabella ContentTypes in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-130">Archivia un elenco di tipi di contenuto SIP (Session Initiation Protocol) usati sia in chiamate peer-to-peer che in conferenze telefoniche.</span><span class="sxs-lookup"><span data-stu-id="f5037-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-131"><a href="lync-server-2013-devices-table.md">Tabella Devices in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-132">Archivia un elenco di dispositivi, inclusi il produttore, la versione hardware e l'indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="f5037-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-133"><a href="lync-server-2013-dialogs-table.md">Tabella Dialogs in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-134">Archivia le informazioni sull'ID della finestra di dialogo per ogni sessione nel database.</span><span class="sxs-lookup"><span data-stu-id="f5037-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-135"><a href="lync-server-2013-edgeservers-table.md">Tabella EdgeServers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-136">Archivia un elenco di Edge Server usati per le chiamate esterne.</span><span class="sxs-lookup"><span data-stu-id="f5037-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-137"><a href="lync-server-2013-gateways-table.md">Tabella Gateways in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-138">Archivia un elenco di gateway usati per le chiamate VoIP (Voice over Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="f5037-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-139"><a href="lync-server-2013-hardwareversions-table.md">Tabella HardwareVersions in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-140">Archivia un elenco di versioni hardware dei dispositivi (telefono da tavolo).</span><span class="sxs-lookup"><span data-stu-id="f5037-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-141"><a href="lync-server-2013-manufacturers-table.md">Tabella Manufacturers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-142">Archivia un elenco di produttori di dispositivi (telefono da tavolo).</span><span class="sxs-lookup"><span data-stu-id="f5037-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-143"><a href="lync-server-2013-mcus-table.md">Tabella Mcus in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-144">Archivia le informazioni sui vari server di conferenza A/V e sui relativi URI.</span><span class="sxs-lookup"><span data-stu-id="f5037-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-145"><a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-146">Archivia un elenco di server di mediazione usati per le chiamate VoIP.</span><span class="sxs-lookup"><span data-stu-id="f5037-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-147"><a href="lync-server-2013-phones-table.md">Tabella Phones in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-148">Archivia tutti i numeri di telefono usati nelle chiamate VoIP archiviate o i cui dettagli delle chiamate sono stati registrati.</span><span class="sxs-lookup"><span data-stu-id="f5037-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-149"><a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-150">Archivia i nomi del pool in cui vengono acquisiti i messaggi di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="f5037-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-151"><a href="lync-server-2013-servers-table.md">Tabella Servers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-152">Archivia il nome dei server coinvolti nelle chiamate.</span><span class="sxs-lookup"><span data-stu-id="f5037-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-153"><a href="lync-server-2013-tenants-table.md">Tabella Tenants in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-154">Archivia i tenant supportati dalla distribuzione corrente.</span><span class="sxs-lookup"><span data-stu-id="f5037-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="f5037-155">Sono presenti alcuni tenant per l'utente aziendale, un utente federato, un utente di connettività per messaggistica istantanea pubblica e utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="f5037-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-156"><a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-157">Associa gli identificatori dell'agente utente ai nomi descrittivi dell'agente.</span><span class="sxs-lookup"><span data-stu-id="f5037-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-158"><a href="lync-server-2013-users-table.md">Tabella Users in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-159">Archivia gli URI utente degli utenti che hanno partecipato a sessioni registrate o archiviate in questo database.</span><span class="sxs-lookup"><span data-stu-id="f5037-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-160"><a href="lync-server-2013-userstatistics-table.md">Tabella UserStatistics in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-161">Archivia le informazioni sull'uso di un singolo utente del sistema.</span><span class="sxs-lookup"><span data-stu-id="f5037-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="f5037-162">Tabelle specifiche dei record CDR per conferenze</span><span class="sxs-lookup"><span data-stu-id="f5037-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5037-163">Tabella</span><span class="sxs-lookup"><span data-stu-id="f5037-163">Table</span></span></th>
<th><span data-ttu-id="f5037-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5037-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5037-165"><a href="lync-server-2013-conferences-table.md">Tabella Conferences in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-166">Archivia informazioni su tutte le conferenze archiviate o i cui dettagli sono stati registrati, inclusi ConferenceURI, e l'ora di inizio e di fine.</span><span class="sxs-lookup"><span data-stu-id="f5037-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Tabella ConferenceSessionDetails in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-168">Archivia informazioni su ogni sessione di conferenza basata su SIP, inclusi l'ora di inizio e di fine, l'ID utente, il codice di risposta e l'ID di diagnostica per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="f5037-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabella FocusJoinsAndLeaves in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-170">Archivia le informazioni relative a riunioni e fogli di conferenza, inclusi il ruolo degli utenti e la versione client.</span><span class="sxs-lookup"><span data-stu-id="f5037-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabella McuJoinsAndLeaves in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-172">Archivia le informazioni sui server di conferenza A/V coinvolti in una conferenza e l'utente partecipa e lascia gli orari.</span><span class="sxs-lookup"><span data-stu-id="f5037-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="f5037-173">Tabelle per i messaggi nelle conferenze di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="f5037-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5037-174">Tabella</span><span class="sxs-lookup"><span data-stu-id="f5037-174">Table</span></span></th>
<th><span data-ttu-id="f5037-175">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5037-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5037-176"><a href="lync-server-2013-conferencemessagecount-table.md">Tabella ConferenceMessageCount in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-177">Per ogni conferenza di messaggistica istantanea, archivia il numero di messaggi inviati da ogni utente.</span><span class="sxs-lookup"><span data-stu-id="f5037-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-178"><a href="lync-server-2013-imreportsummary-table.md">Tabella IMReportSummary in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-179">Fornisce un report globale sulle sessioni di messaggistica istantanea svolte in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5037-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="f5037-180">Tabelle per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="f5037-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5037-181">Tabella</span><span class="sxs-lookup"><span data-stu-id="f5037-181">Table</span></span></th>
<th><span data-ttu-id="f5037-182">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5037-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5037-183"><a href="lync-server-2013-sessiondetails-table.md">Tabella SessionDetails in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-184">Archivia informazioni su ogni sessione peer-to-peer, inclusi l'ora di inizio e di fine, l'ID utente, il codice di risposta e il numero di messaggi per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="f5037-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-185"><a href="lync-server-2013-filetransfers-table.md">Tabella FileTransfers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-186">Archivia informazioni sulle sessioni di trasferimento di file, inclusi il nome e il risultato del file (accettato, rifiutato o annullato).</span><span class="sxs-lookup"><span data-stu-id="f5037-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-187"><a href="lync-server-2013-media-table.md">Tabella Media in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-188">Archivia le informazioni sui diversi tipi di elementi multimediali coinvolti nelle sessioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="f5037-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="f5037-189">Tabella per i dettagli delle chiamate VoIP</span><span class="sxs-lookup"><span data-stu-id="f5037-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5037-190">Tabella</span><span class="sxs-lookup"><span data-stu-id="f5037-190">Table</span></span></th>
<th><span data-ttu-id="f5037-191">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5037-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5037-192"><a href="lync-server-2013-voipdetails-table.md">Tabella VoipDetails in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-193">Per ogni chiamata VoIP/PSTN a due parti, archivia le informazioni sulla chiamata, ad esempio l'ID telefono del telefono VoIP, il gateway usato e il partito disconnesso.</span><span class="sxs-lookup"><span data-stu-id="f5037-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="f5037-194">Fa riferimento alla <a href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</a> per gli orari di inizio/fine delle chiamate e il codice di risposta.</span><span class="sxs-lookup"><span data-stu-id="f5037-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f5037-195">Se una delle parti di una chiamata è un utente VoIP o se è stato coinvolto un Mediation Server nella chiamata, verrà creato un record in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="f5037-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="f5037-196">Le informazioni sulle chiamate VoIP/VoIP che non coinvolgono un telefono PSTN (Public Switched Telephone Network) vengono acquisite nella <A href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f5037-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="f5037-197">Tabella per il controllo delle chiamate E9-1-1</span><span class="sxs-lookup"><span data-stu-id="f5037-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5037-198">Tabella</span><span class="sxs-lookup"><span data-stu-id="f5037-198">Table</span></span></th>
<th><span data-ttu-id="f5037-199">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5037-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5037-200"><a href="lync-server-2013-locations-table.md">Tabella Locations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-201">Per ogni chiamata di emergenza, ad esempio una chiamata avanzata di 9-1-1 (E9-1-1), memorizza le informazioni sulla posizione sulla chiamata.</span><span class="sxs-lookup"><span data-stu-id="f5037-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="f5037-202">Fa riferimento alla <a href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</a> per gli orari di inizio/fine delle chiamate e il codice di risposta.</span><span class="sxs-lookup"><span data-stu-id="f5037-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f5037-203">Questa tabella contiene solo il BLOB della posizione per la chiamata E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f5037-203">This table only contains the location blob for the E9-1-1 call.</span></span> <span data-ttu-id="f5037-204">Fa riferimento alla tabella SessionDetails per altre informazioni dettagliate sulla chiamata.</span><span class="sxs-lookup"><span data-stu-id="f5037-204">Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="f5037-205">Tabelle per la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="f5037-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5037-206">Tabella</span><span class="sxs-lookup"><span data-stu-id="f5037-206">Table</span></span></th>
<th><span data-ttu-id="f5037-207">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5037-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5037-208"><a href="lync-server-2013-application-table.md">Tabella Application in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-209">Archivia informazioni su vari processi in Lync Server 2013 coinvolti in routing e connessioni.</span><span class="sxs-lookup"><span data-stu-id="f5037-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-210"><a href="lync-server-2013-calltype-table.md">Tabella CallType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-211">Archivia informazioni sui tipi di chiamata, ad esempio "audio", "messaggistica istantanea", "audio e video" e "condivisione applicazioni".</span><span class="sxs-lookup"><span data-stu-id="f5037-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-212"><a href="lync-server-2013-errorcategory-table.md">Tabella ErrorCategory in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-213">Archivia il nome descrittivo per ogni classificazione di diagnostica di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5037-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-214"><a href="lync-server-2013-errordef-table.md">Tabella ErrorDef in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-215">Archivia informazioni sui tipi di errori e sulle relative definizioni.</span><span class="sxs-lookup"><span data-stu-id="f5037-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-216"><a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-217">Archivia le informazioni sugli errori che si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="f5037-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-218"><a href="lync-server-2013-progressreport-table.md">Tabella ProgressReport in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5037-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f5037-219">Archivia le informazioni sui rapporti sullo stato di avanzamento di vari passaggi coinvolti nei processi di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5037-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f5037-220">Le tabelle nell'elenco seguente vengono usate internamente da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5037-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="f5037-221">I relativi dettagli non sono descritti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="f5037-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="f5037-222">Tabelle per l'uso interno da Lync Server</span><span class="sxs-lookup"><span data-stu-id="f5037-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5037-223">Tabella</span><span class="sxs-lookup"><span data-stu-id="f5037-223">Table</span></span></th>
<th><span data-ttu-id="f5037-224">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5037-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5037-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-226">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-228">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-230">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-231"><strong>Tabella FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-232">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-233"><strong>Tabella MSMQProcessing</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-234">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-236">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-237"><strong>Tabella Syndicate</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-238">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-239"><strong>Tabella SyndicatorsTenantMap</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-240">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-241"><strong>Tabella delle attività</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-242">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-244">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-246">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-248">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-250">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-252">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-253"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-254">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-256">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-258">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5037-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-260">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5037-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="f5037-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="f5037-262">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f5037-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

