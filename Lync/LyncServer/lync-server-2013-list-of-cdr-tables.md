---
title: 'Lync Server 2013: elenco delle tabelle di registrazione dettagli chiamata'
description: 'Lync Server 2013: elenco delle tabelle di registrazione dettagli chiamata.'
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
ms.openlocfilehash: 21d0f683ffeb0f5f1cbba5db4c45d248aa14e8e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558702"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="640ee-103">Elenco delle tabelle di registrazione dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="640ee-103">List of CDR tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="640ee-104">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="640ee-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="640ee-105">Lo schema del database di registrazione dettagli chiamata (CDR) è costituito dalle tabelle riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="640ee-105">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="640ee-106">Tabelle statiche</span><span class="sxs-lookup"><span data-stu-id="640ee-106">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640ee-107">tavolo</span><span class="sxs-lookup"><span data-stu-id="640ee-107">Table</span></span></th>
<th><span data-ttu-id="640ee-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="640ee-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640ee-109"><a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-109"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-110">In questa tabella è archiviato l'elenco delle possibili priorità delle chiamate, ad esempio "emergency" (di emergenza), "urgent" (urgente), "normal" (normale), "non-urgent" (non urgente) e così via.</span><span class="sxs-lookup"><span data-stu-id="640ee-110">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabella ConferenceJoinTimeThresholds in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-112">In questa tabella sono archiviati i limiti di classificazione utilizzati dal rapporto riepilogativo Tempo di partecipazione alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="640ee-112">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-113"><a href="lync-server-2013-deregistertype-table.md">Tabella DeRegisterType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-113"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-114">Archivia l'elenco dei possibili motivi di deregistrazione degli utenti, ad esempio &quot; client avviato, &quot; &quot; registrazione scaduta, &quot; &quot; arresto anomalo del client &quot; e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="640ee-114">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-115"><a href="lync-server-2013-medialist-table.md">Tabella media in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-115"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-116">,</span><span class="sxs-lookup"><span data-stu-id="640ee-116">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-117"><a href="lync-server-2013-purgesettings-table.md">Tabella PurgeSettings in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-117"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-118">In questa tabella sono archiviate informazioni che specificano se le registrazioni dettagli chiamata obsolete verranno eliminate automaticamente dal database CDR.</span><span class="sxs-lookup"><span data-stu-id="640ee-118">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-119"><a href="lync-server-2013-roles-table.md">Tabella Roles in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-119"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-120">In questa tabella è archiviato l'elenco dei possibili ruoli per le conferenze, ad esempio partecipante e relatore.</span><span class="sxs-lookup"><span data-stu-id="640ee-120">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-121"><a href="lync-server-2013-sipresponsemetadata-table.md">Tabella SIPResponseMetaData in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-121"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-122">In questa tabella è archiviato un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice.</span><span class="sxs-lookup"><span data-stu-id="640ee-122">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="640ee-123">Tabelle di supporto</span><span class="sxs-lookup"><span data-stu-id="640ee-123">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640ee-124">tavolo</span><span class="sxs-lookup"><span data-stu-id="640ee-124">Table</span></span></th>
<th><span data-ttu-id="640ee-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="640ee-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640ee-126"><a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-126"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-127">In questa tabella sono archiviati il tipo e il numero di versione dei singoli client coinvolti in una chiamata con le informazioni acquisite nel database.</span><span class="sxs-lookup"><span data-stu-id="640ee-127">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-128"><a href="lync-server-2013-conferenceuris-table.md">Tabella ConferenceUris in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-128"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-129">In questa tabella è archiviato l'elenco degli URI conferenza utilizzati nelle chiamate relative alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="640ee-129">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-130"><a href="lync-server-2013-contenttypes-table.md">Tabella ContentTypes in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-130"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-131">In questa tabella è archiviato l'elenco dei tipi di contenuto SIP (Session Initiation Protocol) utilizzati sia nelle chiamate peer-to-peer che nelle conferenze telefoniche.</span><span class="sxs-lookup"><span data-stu-id="640ee-131">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-132"><a href="lync-server-2013-devices-table.md">Tabella Devices in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-132"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-133">In questa tabella è archiviato l'elenco dei dispositivi con il relativo produttore, la versione hardware e l'indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="640ee-133">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-134"><a href="lync-server-2013-dialogs-table.md">Tabella Dialogs in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-134"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-135">In questa tabella sono archiviate le informazioni relative all'ID dialogo per ogni sessione nel database.</span><span class="sxs-lookup"><span data-stu-id="640ee-135">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-136"><a href="lync-server-2013-edgeservers-table.md">Tabella EdgeServers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-136"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-137">In questa tabella è archiviato l'elenco dei server perimetrali utilizzati per le chiamate esterne.</span><span class="sxs-lookup"><span data-stu-id="640ee-137">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-138"><a href="lync-server-2013-gateways-table.md">Tabella Gateways in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-138"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-139">In questa tabella è archiviato l'elenco dei gateway utilizzati per le chiamate VoIP (Voice over Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="640ee-139">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-140"><a href="lync-server-2013-hardwareversions-table.md">Tabella HardwareVersions in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-140"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-141">In questa tabella è archiviato l'elenco delle versioni hardware dei dispositivi (telefoni da tavolo).</span><span class="sxs-lookup"><span data-stu-id="640ee-141">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-142"><a href="lync-server-2013-manufacturers-table.md">Tabella Manufacturers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-142"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-143">In questa tabella è archiviato l'elenco dei produttori dei dispositivi (telefoni da tavolo).</span><span class="sxs-lookup"><span data-stu-id="640ee-143">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-144"><a href="lync-server-2013-mcus-table.md">Tabella MCU in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-144"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-145">In questa tabella sono archiviate le informazioni relative ai diversi A/V Conferencing Server con i relativi URI.</span><span class="sxs-lookup"><span data-stu-id="640ee-145">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-146"><a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-146"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-147">In questa tabella è archiviato l'elenco dei Mediation Server utilizzati per le chiamate VoIP.</span><span class="sxs-lookup"><span data-stu-id="640ee-147">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-148"><a href="lync-server-2013-phones-table.md">Tabella Phones in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-148"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-149">In questa tabella sono archiviati tutti i numeri di telefono utilizzati nelle chiamate VoIP che sono state archiviate o di cui sono stati registrati i dettagli.</span><span class="sxs-lookup"><span data-stu-id="640ee-149">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-150"><a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-150"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-151">In questa tabella sono archiviati i nomi del pool in cui vengono acquisiti i messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="640ee-151">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-152"><a href="lync-server-2013-servers-table.md">Tabella Servers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-152"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-153">In questa tabella è archiviato il nome dei server coinvolti nelle chiamate.</span><span class="sxs-lookup"><span data-stu-id="640ee-153">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-154"><a href="lync-server-2013-tenants-table.md">Tabella Tenants in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-154"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-155">In questa tabella sono archiviati i tenant supportati dalla distribuzione corrente.</span><span class="sxs-lookup"><span data-stu-id="640ee-155">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="640ee-156">Vi sono alcuni tenant predefiniti per l'utente Enterprise, l'utente federato, l'utente di connettività di messaggistica istantanea pubblica e gli utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="640ee-156">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-157"><a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-157"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-158">Questa tabella contiene il mapping degli identificatori degli agenti utente ai nomi descrittivi degli agenti.</span><span class="sxs-lookup"><span data-stu-id="640ee-158">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-159"><a href="lync-server-2013-users-table.md">Tabella Users in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-159"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-160">In questa tabella sono archiviati gli URI degli utenti che hanno partecipato alle sessioni registrate o archiviate nel database.</span><span class="sxs-lookup"><span data-stu-id="640ee-160">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-161"><a href="lync-server-2013-userstatistics-table.md">Tabella UserStatistics in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-161"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-162">In questa tabella sono archiviate informazioni sull'uso del sistema da parte di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="640ee-162">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="640ee-163">Tabelle specifiche dei record CDR per le conferenze</span><span class="sxs-lookup"><span data-stu-id="640ee-163">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640ee-164">tavolo</span><span class="sxs-lookup"><span data-stu-id="640ee-164">Table</span></span></th>
<th><span data-ttu-id="640ee-165">Descrizione</span><span class="sxs-lookup"><span data-stu-id="640ee-165">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640ee-166"><a href="lync-server-2013-conferences-table.md">Tabella Conferences in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-166"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-167">In questa tabella sono archiviate le informazioni relative a tutte le conferenze che sono state archiviate o di cui sono stati registrati i dettagli, inclusi l'URI conferenza e la data/ora di inizio e fine.</span><span class="sxs-lookup"><span data-stu-id="640ee-167">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-168"><a href="lync-server-2013-conferencesessiondetails-table.md">Tabella ConferenceSessionDetails in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-168"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-169">In questa tabella sono archiviate le informazioni relative a tutte le sessioni di conferenza basate su SIP, inclusi la data/ora di inizio e fine, l'ID utente, il codice di risposta e l'ID diagnostica di ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="640ee-169">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabella FocusJoinsAndLeaves in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-171">In questa tabella sono archiviate le informazioni relative alle partecipazioni e agli abbandoni delle conferenze, inclusi il ruolo degli utenti e la versione client.</span><span class="sxs-lookup"><span data-stu-id="640ee-171">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabella McuJoinsAndLeaves in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-173">In questa tabella sono archiviate le informazioni relative agli A/V Conferencing Server coinvolti in una conferenza e la data/ora di partecipazione e abbandono degli utenti.</span><span class="sxs-lookup"><span data-stu-id="640ee-173">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="640ee-174">Tabelle per i messaggi nelle conferenze di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="640ee-174">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640ee-175">tavolo</span><span class="sxs-lookup"><span data-stu-id="640ee-175">Table</span></span></th>
<th><span data-ttu-id="640ee-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="640ee-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640ee-177"><a href="lync-server-2013-conferencemessagecount-table.md">Tabella ConferenceMessageCount in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-177"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-178">In questa tabella è archiviato, per ogni conferenza di messaggistica istantanea, il numero dei messaggi inviati da ogni utente.</span><span class="sxs-lookup"><span data-stu-id="640ee-178">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-179"><a href="lync-server-2013-imreportsummary-table.md">Tabella IMReportSummary in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-179"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-180">Questa tabella fornisce un rapporto complessivo sulle sessioni di messaggistica istantanea tenute in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="640ee-180">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="640ee-181">Tabelle per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="640ee-181">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640ee-182">tavolo</span><span class="sxs-lookup"><span data-stu-id="640ee-182">Table</span></span></th>
<th><span data-ttu-id="640ee-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="640ee-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640ee-184"><a href="lync-server-2013-sessiondetails-table.md">Tabella SessionDetails in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-184"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-185">In questa tabella sono archiviate le informazioni relative a tutte le sessioni peer-to-peer, inclusi la data/ora di inizio e fine, l'ID utente, il codice di risposta e il numero dei messaggi per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="640ee-185">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-186"><a href="lync-server-2013-filetransfers-table.md">Tabella FileTransfers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-186"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-187">In questa tabella sono archiviate le informazioni relative alle sessioni di trasferimento file, inclusi il nome di file e il risultato (accettazione, rifiuto o annullamento).</span><span class="sxs-lookup"><span data-stu-id="640ee-187">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-188"><a href="lync-server-2013-media-table.md">Tabella multimediale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-188"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-189">In questa tabella sono archiviate le informazioni relative ai diversi tipi di contenuto multimediale coinvolti nelle sessioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="640ee-189">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="640ee-190">Tabella per i dettagli delle chiamate VoIP</span><span class="sxs-lookup"><span data-stu-id="640ee-190">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640ee-191">tavolo</span><span class="sxs-lookup"><span data-stu-id="640ee-191">Table</span></span></th>
<th><span data-ttu-id="640ee-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="640ee-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640ee-193"><a href="lync-server-2013-voipdetails-table.md">Tabella VoipDetails in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-193"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-194">In questa tabella sono archiviate, per ogni chiamata VoIP/PSTN tra due parti, le informazioni relative alla chiamata, ad esempio l'ID del telefono VoIP, il gateway utilizzato e la parte che si è disconnessa.</span><span class="sxs-lookup"><span data-stu-id="640ee-194">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="640ee-195">Fa riferimento alla <a href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</a> per gli orari di inizio e di fine chiamata e il codice di risposta.</span><span class="sxs-lookup"><span data-stu-id="640ee-195">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="640ee-196">Se una parte coinvolta in una chiamata è un utente VoIP o se nella chiamata è coinvolto un Mediation Server, verrà creato un record in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="640ee-196">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="640ee-197">Le informazioni sulle chiamate VoIP/VoIP che non coinvolgono un telefono PSTN (Public Switched Telephone Network) sono state acquisite nella <A href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="640ee-197">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="640ee-198">Tabella per il controllo delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="640ee-198">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640ee-199">tavolo</span><span class="sxs-lookup"><span data-stu-id="640ee-199">Table</span></span></th>
<th><span data-ttu-id="640ee-200">Descrizione</span><span class="sxs-lookup"><span data-stu-id="640ee-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640ee-201"><a href="lync-server-2013-locations-table.md">Tabella Locations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-201"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-202">In questa tabella sono archiviate, per ogni chiamata di emergenza, le informazioni relative alla località della chiamata.</span><span class="sxs-lookup"><span data-stu-id="640ee-202">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="640ee-203">Fa riferimento alla <a href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</a> per gli orari di inizio e di fine chiamata e il codice di risposta.</span><span class="sxs-lookup"><span data-stu-id="640ee-203">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="640ee-p105">In questa tabella è contenuto solo il BLOB della località per la chiamata di emergenza. Fa riferimento alla tabella SessionDetails per altre informazioni dettagliate relative alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="640ee-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="640ee-206">Tabella per la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="640ee-206">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640ee-207">tavolo</span><span class="sxs-lookup"><span data-stu-id="640ee-207">Table</span></span></th>
<th><span data-ttu-id="640ee-208">Descrizione</span><span class="sxs-lookup"><span data-stu-id="640ee-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640ee-209"><a href="lync-server-2013-application-table.md">Tabella Application in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-209"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-210">Archivia informazioni sui vari processi all'interno di Lync Server 2013 coinvolti nel routing e nelle connessioni.</span><span class="sxs-lookup"><span data-stu-id="640ee-210">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-211"><a href="lync-server-2013-calltype-table.md">Tabella CallType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-211"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-212">In questa tabella sono archiviate le informazioni relative ai tipi di chiamata, ad esempio "audio", "Instant Messaging" (messaggistica istantanea), "audio and video" (audio e video) e "application sharing" (condivisione applicazioni).</span><span class="sxs-lookup"><span data-stu-id="640ee-212">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-213"><a href="lync-server-2013-errorcategory-table.md">Tabella ErrorCategory in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-213"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-214">Archivia il nome descrittivo per ogni classificazione diagnostica di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="640ee-214">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-215"><a href="lync-server-2013-errordef-table.md">Tabella ErrorDef in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-215"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-216">In questa tabella sono archiviate le informazioni relative ai tipi di errori con le relative definizioni.</span><span class="sxs-lookup"><span data-stu-id="640ee-216">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-217"><a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-217"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-218">In questa tabella sono archiviate le informazioni relative agli errori che si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="640ee-218">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-219"><a href="lync-server-2013-progressreport-table.md">Tabella ProgressReport in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="640ee-219"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="640ee-220">Archivia informazioni sui report sullo stato di avanzamento di vari passaggi coinvolti nei processi di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="640ee-220">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="640ee-221">Le tabelle nell'elenco seguente vengono utilizzate internamente da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="640ee-221">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="640ee-222">I relativi dettagli non vengono illustrati in questo documento.</span><span class="sxs-lookup"><span data-stu-id="640ee-222">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="640ee-223">Tabelle utilizzate internamente da Lync Server</span><span class="sxs-lookup"><span data-stu-id="640ee-223">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640ee-224">tavolo</span><span class="sxs-lookup"><span data-stu-id="640ee-224">Table</span></span></th>
<th><span data-ttu-id="640ee-225">Descrizione</span><span class="sxs-lookup"><span data-stu-id="640ee-225">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640ee-226"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-226"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-227">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-227">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-228"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-228"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-229">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-229">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-230"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-230"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-231">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-231">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-232"><strong>Tabella FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-232"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-233">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-233">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-234"><strong>Tabella MSMQProcessing</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-234"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-235">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-235">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-236"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-236"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-237">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-237">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-238"><strong>Tabella Syndicators</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-238"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-239">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-239">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-240"><strong>Tabella SyndicatorsTenantMap</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-240"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-241">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-241">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-242"><strong>Tabella Task</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-242"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-243">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-243">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-244"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-244"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-245">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-245">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-246"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-246"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-247">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-247">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-248"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-248"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-249">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-249">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-250"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-250"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-251">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-251">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-252"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-252"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-253">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-253">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-254"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-254"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-255">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-255">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-256"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-256"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-257">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-257">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-258"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-258"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-259">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-259">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640ee-260"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-260"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-261">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-261">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640ee-262"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="640ee-262"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="640ee-263">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="640ee-263">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

