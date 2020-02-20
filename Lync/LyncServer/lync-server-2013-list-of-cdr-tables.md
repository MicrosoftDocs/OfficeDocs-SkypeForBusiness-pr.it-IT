---
title: 'Lync Server 2013: elenco delle tabelle di registrazione dettagli chiamata'
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
ms.openlocfilehash: b2792988c24ad412c80c18a4c334d1af54bbcf3a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="27e7e-102">Elenco delle tabelle di registrazione dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27e7e-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27e7e-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="27e7e-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="27e7e-104">Lo schema del database di registrazione dettagli chiamata (CDR) è costituito dalle tabelle riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="27e7e-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="27e7e-105">Tabelle statiche</span><span class="sxs-lookup"><span data-stu-id="27e7e-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27e7e-106">tavolo</span><span class="sxs-lookup"><span data-stu-id="27e7e-106">Table</span></span></th>
<th><span data-ttu-id="27e7e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27e7e-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-108"><a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-109">In questa tabella è archiviato l'elenco delle possibili priorità delle chiamate, ad esempio "emergency" (di emergenza), "urgent" (urgente), "normal" (normale), "non-urgent" (non urgente) e così via.</span><span class="sxs-lookup"><span data-stu-id="27e7e-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabella ConferenceJoinTimeThresholds in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-111">In questa tabella sono archiviati i limiti di classificazione utilizzati dal rapporto riepilogativo Tempo di partecipazione alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="27e7e-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-112"><a href="lync-server-2013-deregistertype-table.md">Tabella DeRegisterType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-113">Archivia l'elenco dei possibili motivi di deregistrazione degli utenti, ad &quot;esempio client avviato&quot; &quot;, registrazione scaduta&quot; &quot;, arresto anomalo&quot; del client e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="27e7e-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-114"><a href="lync-server-2013-medialist-table.md">Tabella media in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-115">,</span><span class="sxs-lookup"><span data-stu-id="27e7e-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-116"><a href="lync-server-2013-purgesettings-table.md">Tabella PurgeSettings in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-117">In questa tabella sono archiviate informazioni che specificano se le registrazioni dettagli chiamata obsolete verranno eliminate automaticamente dal database CDR.</span><span class="sxs-lookup"><span data-stu-id="27e7e-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-118"><a href="lync-server-2013-roles-table.md">Tabella Roles in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-119">In questa tabella è archiviato l'elenco dei possibili ruoli per le conferenze, ad esempio partecipante e relatore.</span><span class="sxs-lookup"><span data-stu-id="27e7e-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Tabella SIPResponseMetaData in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-121">In questa tabella è archiviato un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice.</span><span class="sxs-lookup"><span data-stu-id="27e7e-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="27e7e-122">Tabelle di supporto</span><span class="sxs-lookup"><span data-stu-id="27e7e-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27e7e-123">tavolo</span><span class="sxs-lookup"><span data-stu-id="27e7e-123">Table</span></span></th>
<th><span data-ttu-id="27e7e-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27e7e-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-125"><a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-126">In questa tabella sono archiviati il tipo e il numero di versione dei singoli client coinvolti in una chiamata con le informazioni acquisite nel database.</span><span class="sxs-lookup"><span data-stu-id="27e7e-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-127"><a href="lync-server-2013-conferenceuris-table.md">Tabella ConferenceUris in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-128">In questa tabella è archiviato l'elenco degli URI conferenza utilizzati nelle chiamate relative alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="27e7e-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-129"><a href="lync-server-2013-contenttypes-table.md">Tabella ContentTypes in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-130">In questa tabella è archiviato l'elenco dei tipi di contenuto SIP (Session Initiation Protocol) utilizzati sia nelle chiamate peer-to-peer che nelle conferenze telefoniche.</span><span class="sxs-lookup"><span data-stu-id="27e7e-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-131"><a href="lync-server-2013-devices-table.md">Tabella Devices in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-132">In questa tabella è archiviato l'elenco dei dispositivi con il relativo produttore, la versione hardware e l'indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="27e7e-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-133"><a href="lync-server-2013-dialogs-table.md">Tabella Dialogs in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-134">In questa tabella sono archiviate le informazioni relative all'ID dialogo per ogni sessione nel database.</span><span class="sxs-lookup"><span data-stu-id="27e7e-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-135"><a href="lync-server-2013-edgeservers-table.md">Tabella EdgeServers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-136">In questa tabella è archiviato l'elenco dei server perimetrali utilizzati per le chiamate esterne.</span><span class="sxs-lookup"><span data-stu-id="27e7e-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-137"><a href="lync-server-2013-gateways-table.md">Tabella Gateways in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-138">In questa tabella è archiviato l'elenco dei gateway utilizzati per le chiamate VoIP (Voice over Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="27e7e-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-139"><a href="lync-server-2013-hardwareversions-table.md">Tabella HardwareVersions in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-140">In questa tabella è archiviato l'elenco delle versioni hardware dei dispositivi (telefoni da tavolo).</span><span class="sxs-lookup"><span data-stu-id="27e7e-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-141"><a href="lync-server-2013-manufacturers-table.md">Tabella Manufacturers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-142">In questa tabella è archiviato l'elenco dei produttori dei dispositivi (telefoni da tavolo).</span><span class="sxs-lookup"><span data-stu-id="27e7e-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-143"><a href="lync-server-2013-mcus-table.md">Tabella MCU in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-144">In questa tabella sono archiviate le informazioni relative ai diversi A/V Conferencing Server con i relativi URI.</span><span class="sxs-lookup"><span data-stu-id="27e7e-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-145"><a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-146">In questa tabella è archiviato l'elenco dei Mediation Server utilizzati per le chiamate VoIP.</span><span class="sxs-lookup"><span data-stu-id="27e7e-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-147"><a href="lync-server-2013-phones-table.md">Tabella Phones in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-148">In questa tabella sono archiviati tutti i numeri di telefono utilizzati nelle chiamate VoIP che sono state archiviate o di cui sono stati registrati i dettagli.</span><span class="sxs-lookup"><span data-stu-id="27e7e-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-149"><a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-150">In questa tabella sono archiviati i nomi del pool in cui vengono acquisiti i messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="27e7e-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-151"><a href="lync-server-2013-servers-table.md">Tabella Servers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-152">In questa tabella è archiviato il nome dei server coinvolti nelle chiamate.</span><span class="sxs-lookup"><span data-stu-id="27e7e-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-153"><a href="lync-server-2013-tenants-table.md">Tabella Tenants in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-154">In questa tabella sono archiviati i tenant supportati dalla distribuzione corrente.</span><span class="sxs-lookup"><span data-stu-id="27e7e-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="27e7e-155">Vi sono alcuni tenant predefiniti per l'utente Enterprise, l'utente federato, l'utente di connettività di messaggistica istantanea pubblica e gli utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="27e7e-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-156"><a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-157">Questa tabella contiene il mapping degli identificatori degli agenti utente ai nomi descrittivi degli agenti.</span><span class="sxs-lookup"><span data-stu-id="27e7e-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-158"><a href="lync-server-2013-users-table.md">Tabella Users in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-159">In questa tabella sono archiviati gli URI degli utenti che hanno partecipato alle sessioni registrate o archiviate nel database.</span><span class="sxs-lookup"><span data-stu-id="27e7e-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-160"><a href="lync-server-2013-userstatistics-table.md">Tabella UserStatistics in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-161">In questa tabella sono archiviate informazioni sull'uso del sistema da parte di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="27e7e-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="27e7e-162">Tabelle specifiche dei record CDR per le conferenze</span><span class="sxs-lookup"><span data-stu-id="27e7e-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27e7e-163">tavolo</span><span class="sxs-lookup"><span data-stu-id="27e7e-163">Table</span></span></th>
<th><span data-ttu-id="27e7e-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27e7e-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-165"><a href="lync-server-2013-conferences-table.md">Tabella Conferences in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-166">In questa tabella sono archiviate le informazioni relative a tutte le conferenze che sono state archiviate o di cui sono stati registrati i dettagli, inclusi l'URI conferenza e la data/ora di inizio e fine.</span><span class="sxs-lookup"><span data-stu-id="27e7e-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Tabella ConferenceSessionDetails in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-168">In questa tabella sono archiviate le informazioni relative a tutte le sessioni di conferenza basate su SIP, inclusi la data/ora di inizio e fine, l'ID utente, il codice di risposta e l'ID diagnostica di ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="27e7e-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabella FocusJoinsAndLeaves in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-170">In questa tabella sono archiviate le informazioni relative alle partecipazioni e agli abbandoni delle conferenze, inclusi il ruolo degli utenti e la versione client.</span><span class="sxs-lookup"><span data-stu-id="27e7e-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabella McuJoinsAndLeaves in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-172">In questa tabella sono archiviate le informazioni relative agli A/V Conferencing Server coinvolti in una conferenza e la data/ora di partecipazione e abbandono degli utenti.</span><span class="sxs-lookup"><span data-stu-id="27e7e-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="27e7e-173">Tabelle per i messaggi nelle conferenze di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="27e7e-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27e7e-174">tavolo</span><span class="sxs-lookup"><span data-stu-id="27e7e-174">Table</span></span></th>
<th><span data-ttu-id="27e7e-175">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27e7e-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-176"><a href="lync-server-2013-conferencemessagecount-table.md">Tabella ConferenceMessageCount in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-177">In questa tabella è archiviato, per ogni conferenza di messaggistica istantanea, il numero dei messaggi inviati da ogni utente.</span><span class="sxs-lookup"><span data-stu-id="27e7e-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-178"><a href="lync-server-2013-imreportsummary-table.md">Tabella IMReportSummary in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-179">Questa tabella fornisce un rapporto complessivo sulle sessioni di messaggistica istantanea tenute in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="27e7e-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="27e7e-180">Tabelle per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="27e7e-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27e7e-181">tavolo</span><span class="sxs-lookup"><span data-stu-id="27e7e-181">Table</span></span></th>
<th><span data-ttu-id="27e7e-182">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27e7e-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-183"><a href="lync-server-2013-sessiondetails-table.md">Tabella SessionDetails in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-184">In questa tabella sono archiviate le informazioni relative a tutte le sessioni peer-to-peer, inclusi la data/ora di inizio e fine, l'ID utente, il codice di risposta e il numero dei messaggi per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="27e7e-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-185"><a href="lync-server-2013-filetransfers-table.md">Tabella FileTransfers in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-186">In questa tabella sono archiviate le informazioni relative alle sessioni di trasferimento file, inclusi il nome di file e il risultato (accettazione, rifiuto o annullamento).</span><span class="sxs-lookup"><span data-stu-id="27e7e-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-187"><a href="lync-server-2013-media-table.md">Tabella multimediale in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-188">In questa tabella sono archiviate le informazioni relative ai diversi tipi di contenuto multimediale coinvolti nelle sessioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="27e7e-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="27e7e-189">Tabella per i dettagli delle chiamate VoIP</span><span class="sxs-lookup"><span data-stu-id="27e7e-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27e7e-190">tavolo</span><span class="sxs-lookup"><span data-stu-id="27e7e-190">Table</span></span></th>
<th><span data-ttu-id="27e7e-191">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27e7e-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-192"><a href="lync-server-2013-voipdetails-table.md">Tabella VoipDetails in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-193">In questa tabella sono archiviate, per ogni chiamata VoIP/PSTN tra due parti, le informazioni relative alla chiamata, ad esempio l'ID del telefono VoIP, il gateway utilizzato e la parte che si è disconnessa.</span><span class="sxs-lookup"><span data-stu-id="27e7e-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="27e7e-194">Fa riferimento alla <a href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</a> per gli orari di inizio e di fine chiamata e il codice di risposta.</span><span class="sxs-lookup"><span data-stu-id="27e7e-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="27e7e-195">Se una parte coinvolta in una chiamata è un utente VoIP o se nella chiamata è coinvolto un Mediation Server, verrà creato un record in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="27e7e-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="27e7e-196">Le informazioni sulle chiamate VoIP/VoIP che non coinvolgono un telefono PSTN (Public Switched Telephone Network) sono state acquisite nella <A href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="27e7e-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="27e7e-197">Tabella per il controllo delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="27e7e-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27e7e-198">tavolo</span><span class="sxs-lookup"><span data-stu-id="27e7e-198">Table</span></span></th>
<th><span data-ttu-id="27e7e-199">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27e7e-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-200"><a href="lync-server-2013-locations-table.md">Tabella Locations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-201">In questa tabella sono archiviate, per ogni chiamata di emergenza, le informazioni relative alla località della chiamata.</span><span class="sxs-lookup"><span data-stu-id="27e7e-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="27e7e-202">Fa riferimento alla <a href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</a> per gli orari di inizio e di fine chiamata e il codice di risposta.</span><span class="sxs-lookup"><span data-stu-id="27e7e-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="27e7e-p105">In questa tabella è contenuto solo il BLOB della località per la chiamata di emergenza. Fa riferimento alla tabella SessionDetails per altre informazioni dettagliate relative alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="27e7e-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="27e7e-205">Tabella per la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="27e7e-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27e7e-206">tavolo</span><span class="sxs-lookup"><span data-stu-id="27e7e-206">Table</span></span></th>
<th><span data-ttu-id="27e7e-207">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27e7e-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-208"><a href="lync-server-2013-application-table.md">Tabella Application in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-209">Archivia informazioni sui vari processi all'interno di Lync Server 2013 coinvolti nel routing e nelle connessioni.</span><span class="sxs-lookup"><span data-stu-id="27e7e-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-210"><a href="lync-server-2013-calltype-table.md">Tabella CallType in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-211">In questa tabella sono archiviate le informazioni relative ai tipi di chiamata, ad esempio "audio", "Instant Messaging" (messaggistica istantanea), "audio and video" (audio e video) e "application sharing" (condivisione applicazioni).</span><span class="sxs-lookup"><span data-stu-id="27e7e-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-212"><a href="lync-server-2013-errorcategory-table.md">Tabella ErrorCategory in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-213">Archivia il nome descrittivo per ogni classificazione diagnostica di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="27e7e-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-214"><a href="lync-server-2013-errordef-table.md">Tabella ErrorDef in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-215">In questa tabella sono archiviate le informazioni relative ai tipi di errori con le relative definizioni.</span><span class="sxs-lookup"><span data-stu-id="27e7e-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-216"><a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-217">In questa tabella sono archiviate le informazioni relative agli errori che si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="27e7e-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-218"><a href="lync-server-2013-progressreport-table.md">Tabella ProgressReport in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="27e7e-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="27e7e-219">Archivia informazioni sui report sullo stato di avanzamento di vari passaggi coinvolti nei processi di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="27e7e-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="27e7e-220">Le tabelle nell'elenco seguente vengono utilizzate internamente da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27e7e-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="27e7e-221">I relativi dettagli non vengono illustrati in questo documento.</span><span class="sxs-lookup"><span data-stu-id="27e7e-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="27e7e-222">Tabelle utilizzate internamente da Lync Server</span><span class="sxs-lookup"><span data-stu-id="27e7e-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27e7e-223">tavolo</span><span class="sxs-lookup"><span data-stu-id="27e7e-223">Table</span></span></th>
<th><span data-ttu-id="27e7e-224">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27e7e-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-226">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-228">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-230">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-231"><strong>Tabella FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-232">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-233"><strong>Tabella MSMQProcessing</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-234">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-236">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-237"><strong>Tabella Syndicators</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-238">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-239"><strong>Tabella SyndicatorsTenantMap</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-240">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-241"><strong>Tabella Task</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-242">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-244">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-246">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-248">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-250">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-252">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-253"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-254">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-256">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-258">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7e-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-260">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7e-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="27e7e-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7e-262">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="27e7e-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

