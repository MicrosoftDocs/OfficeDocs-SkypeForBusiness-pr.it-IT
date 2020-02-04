---
title: 'Lync Server 2013: Elenco delle tabelle QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3161415b65c8e85ace7968ab29d86c0d0c5387a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="c5e39-102">Elenco delle tabelle QoE in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5e39-102">List of QoE tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5e39-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c5e39-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c5e39-104">Lo schema del database è costituito dalle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="c5e39-104">The database schema consists of the following tables.</span></span>

<span data-ttu-id="c5e39-105">**Tabelle di supporto**</span><span class="sxs-lookup"><span data-stu-id="c5e39-105">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5e39-106"><strong>Tabella</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-106"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="c5e39-107"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-107"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabella AppSharingMetricsThreshold in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-109">Consente di archiviare valori ottimali e accettabili per la qualità delle metriche di esperienza usate con la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c5e39-109">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-110"><a href="lync-server-2013-codecdescription-table.md">Tabella CodecDescription in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-110"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-111">Associa gli identificatori di codec univoci al relativo codec.</span><span class="sxs-lookup"><span data-stu-id="c5e39-111">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-112"><a href="lync-server-2013-ipaddress-table.md">Tabella IPAddress in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-112"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-113">Esegue il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci usati altrove nel database qualità di esperienza.</span><span class="sxs-lookup"><span data-stu-id="c5e39-113">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-114"><a href="lync-server-2013-networkconnectiondetail-table.md">Tabella NetworkConnectionDetail in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-114"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-115">Associa i tipi di connessione di rete agli identificatori di connessione di rete usati in un altro punto del database qualità dell'esperienza.</span><span class="sxs-lookup"><span data-stu-id="c5e39-115">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-116"><a href="lync-server-2013-purgesettings-table-qoe.md">Tabella PurgeSettings (QoE) in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-116"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-117">Archivia le informazioni che specificano se (e quando) la qualità obsoleta dei record dell'esperienza verrà eliminata automaticamente dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="c5e39-117">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-118"><a href="lync-server-2013-traceroute-table.md">Tabella TraceRoute in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-118"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-119">Archivia le informazioni di routing per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="c5e39-119">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-120"><a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-120"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-121">Associa gli identificatori dell'agente utente ai nomi descrittivi dell'agente.</span><span class="sxs-lookup"><span data-stu-id="c5e39-121">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-122"><a href="lync-server-2013-videometricsthreshold-table.md">Tabella VideoMetricsThreshold in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-122"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-123">Consente di archiviare valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con videochiamate.</span><span class="sxs-lookup"><span data-stu-id="c5e39-123">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-124"><a href="lync-server-2013-useragent-table.md">Tabella UserAgent in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-124"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-125">Archivia le stringhe degli agenti utente SIP (Session Initiation Protocol) e i tipi UA usati nelle sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-125">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-126"><a href="lync-server-2013-user-table.md">Tabella User in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-126"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-127">Archivia gli URI dell'utente, della conferenza e del telefono usati nelle sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-127">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-128"><a href="lync-server-2013-endpoint-table.md">Tabella Endpoint in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-128"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-129">Archivia i nomi di computer FQDN degli endpoint che partecipano a sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-129">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-130"><a href="lync-server-2013-pool-table.md">Tabella Pool in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-130"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-131">Archivia i nomi dei pool a cui appartengono i dati della metrica.</span><span class="sxs-lookup"><span data-stu-id="c5e39-131">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-132"><a href="lync-server-2013-device-table.md">Tabella Device in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-132"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-133">Archivia i dispositivi di acquisizione e i dispositivi di rendering usati in una chiamata audio/video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-133">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-134"><a href="lync-server-2013-devicedriver-table.md">Tabella DeviceDriver in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-134"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-135">Archivia il driver per il dispositivo di acquisizione e il dispositivo di rendering usato nelle chiamate audio/video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-135">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-136"><a href="lync-server-2013-conference-table.md">Tabella Conference in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-136"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-137">Archivia gli URI della conferenza per gli scenari di conferenza o DialogID per altri scenari.</span><span class="sxs-lookup"><span data-stu-id="c5e39-137">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-138"><a href="lync-server-2013-sessioncorrelation-table.md">Tabella SessionCorrelation in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-138"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-139">Memorizza CorrelationID per le chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="c5e39-139">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-140"><a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-140"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-141">Archivia il codec usato nelle chiamate audio/video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-141">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabella AppliedBandwidthSource in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-143">Archivia l'origine della larghezza di banda usata nelle chiamate audio/video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-143">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-144"><a href="lync-server-2013-macaddress-table.md">Tabella MacAddress in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-144"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-145">Archivia l'indirizzo MAC degli endpoint che partecipano a sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-145">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-146"><a href="lync-server-2013-dialog-table.md">Tabella Dialog in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-146"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-147">Archivia l'ID della finestra di dialogo delle sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-147">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-148"><a href="lync-server-2013-region-table.md">Tabella Region in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-148"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-149">Archivia l'area di rete definita in impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="c5e39-149">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-150"><a href="lync-server-2013-usersite-table.md">Tabella UserSite in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-150"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-151">Archivia il sito di rete definito nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="c5e39-151">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-152"><a href="lync-server-2013-subnet-table.md">Tabella Subnet in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-152"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-153">Archivia la subnet definita nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="c5e39-153">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-154"><a href="lync-server-2013-monitoredregionlink-table.md">Tabella MonitoredRegionLink in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-154"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-155">Archivia il collegamento all'area geografica definito nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="c5e39-155">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-156"><a href="monitoredusersitelink-table.md">Tabella MonitoredUserSiteLink</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-157">Archivia i collegamenti ai siti di rete definiti nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="c5e39-157">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-158"><a href="lync-server-2013-endpointsubnet-table.md">Tabella EndpointSubnet in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-158"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-159">Archivia la subnet dell'endpoint che partecipa a una sessione audio e video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-159">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-160"><a href="lync-server-2013-server-table.md">Tabella Server in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-160"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-161">Archivia il nome di dominio completo o l'indirizzo IP del server in cui passa il contenuto multimediale.</span><span class="sxs-lookup"><span data-stu-id="c5e39-161">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c5e39-162">**Tabelle per i dati delle metriche**</span><span class="sxs-lookup"><span data-stu-id="c5e39-162">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5e39-163"><strong>Tabella</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-163"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="c5e39-164"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-164"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-165"><a href="lync-server-2013-appsharingstream-table.md">Tabella AppSharingStream in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-165"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-166">Archivia la qualità delle metriche dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c5e39-166">Stores Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="c5e39-167">Qualità delle metriche dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c5e39-167">Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-168"><a href="lync-server-2013-session-table.md">Tabella Session in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-168"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-169">Archivia informazioni generali su una sessione audio o audio/video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-169">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="c5e39-170">Una sessione viene definita come una finestra di dialogo SIP audio o video tra due endpoint.</span><span class="sxs-lookup"><span data-stu-id="c5e39-170">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-171"><a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-171"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-172">Archivia informazioni su ogni riga multimediale di una sessione.</span><span class="sxs-lookup"><span data-stu-id="c5e39-172">Stores information about each media line in a session.</span></span> <span data-ttu-id="c5e39-173">Una linea media è una raccolta di uno o più flussi audio e video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-173">A media line is a collection of one or more audio and video streams.</span></span> <span data-ttu-id="c5e39-174">In genere, una singola linea multimediale avrà due flussi, audio o video.</span><span class="sxs-lookup"><span data-stu-id="c5e39-174">Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-175"><a href="lync-server-2013-audiostream-table.md">Tabella AudioStream in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-175"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-176">Memorizza le metriche per la qualità del supporto audio per ogni flusso audio nella linea media.</span><span class="sxs-lookup"><span data-stu-id="c5e39-176">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-177"><a href="lync-server-2013-audiosignal-table.md">Tabella AudioSignal in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-177"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-178">Memorizza le metriche di qualità per i supporti audio nella linea media.</span><span class="sxs-lookup"><span data-stu-id="c5e39-178">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="c5e39-179">Sono incluse le metriche per l'annullamento dell'eco acustica (AEC) e il controllo automatico del guadagno (AGC).</span><span class="sxs-lookup"><span data-stu-id="c5e39-179">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-180"><a href="lync-server-2013-videostream-table.md">Tabella VideoStream in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-180"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-181">Archivia le metriche di qualità multimediali video per ogni flusso audio nella linea media.</span><span class="sxs-lookup"><span data-stu-id="c5e39-181">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-182"><a href="lync-server-2013-audioclientevent-table.md">Tabella AudioClientEvent in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-182"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-183">Archivia le metriche di qualità del supporto audio raccolte dall'evento client.</span><span class="sxs-lookup"><span data-stu-id="c5e39-183">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-184"><a href="lync-server-2013-videoclientevent-table.md">Tabella VideoClientEvent in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c5e39-184"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c5e39-185">Archivia le metriche di qualità multimediali video raccolte dall'evento client.</span><span class="sxs-lookup"><span data-stu-id="c5e39-185">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-186"><strong>Tabella DiagnosticData</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-186"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-187">Archivia i dati di diagnostica solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-187">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c5e39-188">**Tabelle per i dati di riepilogo**</span><span class="sxs-lookup"><span data-stu-id="c5e39-188">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5e39-189"><strong>Tabella</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-189"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="c5e39-190"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-190"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-191"><strong>Tabella ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-191"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-192">Archivia i dati di riepilogo per i server, questi dati vengono usati solo per i report di qualità dell'esperienza (QoE).</span><span class="sxs-lookup"><span data-stu-id="c5e39-192">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-193"><strong>Tabella UserSummary</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-193"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-194">Archivia i dati di riepilogo per gli utenti, questi dati vengono usati solo per i report QoE.</span><span class="sxs-lookup"><span data-stu-id="c5e39-194">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-195"><strong>Tabella CallTypeSummary</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-195"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-196">Archiviare i dati di riepilogo per i tipi di chiamata, questi dati vengono usati solo per i report QoE.</span><span class="sxs-lookup"><span data-stu-id="c5e39-196">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c5e39-197">**Tabelle per l'uso interno tramite Monitoring Server**</span><span class="sxs-lookup"><span data-stu-id="c5e39-197">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5e39-198"><strong>Tabella</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-198"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="c5e39-199"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-199"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-200"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-200"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-201">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-201">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-202"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-202"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-203">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-203">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-204"><strong>Tabella FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-204"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-205">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-205">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-206"><strong>Tabella delle attività</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-206"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-207">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-207">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-208"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-208"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-209">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-209">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-210"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-210"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-211">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-211">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-212"><strong>MetricsThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-212"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-213">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-213">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-214"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-214"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-215">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-215">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-216"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-216"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-217">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-217">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-218"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-218"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-219">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-219">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-220"><strong>Tabella CallSummary</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-220"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-221">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-221">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-222"><strong>Tabella DeviceCallSumary</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-222"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-223">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-223">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-224"><strong>Tabella tenant</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-224"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-225">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-225">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5e39-226"><strong>VideoCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-226"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-227">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-227">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5e39-228"><strong>ASCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="c5e39-228"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="c5e39-229">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="c5e39-229">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

