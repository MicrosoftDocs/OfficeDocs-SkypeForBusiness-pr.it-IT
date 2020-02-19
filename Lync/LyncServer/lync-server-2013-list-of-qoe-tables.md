---
title: 'Lync Server 2013: elenco delle tabelle QoE'
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
ms.openlocfilehash: d47dc5b2623467feec340a6c918e6b43917593ee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="82111-102">Elenco delle tabelle QoE in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82111-102">List of QoE tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82111-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="82111-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="82111-104">Lo schema del database è costituito dalle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="82111-104">The database schema consists of the following tables.</span></span>

<span data-ttu-id="82111-105">**Tabelle di supporto**</span><span class="sxs-lookup"><span data-stu-id="82111-105">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82111-106"><strong>tavolo</strong></span><span class="sxs-lookup"><span data-stu-id="82111-106"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="82111-107"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="82111-107"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82111-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabella AppSharingMetricsThreshold in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-109">Archivia i valori ottimali e accettabili per le metriche sulla qualità delle esperienze utilizzate con la condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="82111-109">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-110"><a href="lync-server-2013-codecdescription-table.md">Tabella CodecDescription in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-110"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-111">Consente di mappare gli identificatori di codec univoci al codec corrispondente.</span><span class="sxs-lookup"><span data-stu-id="82111-111">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-112"><a href="lync-server-2013-ipaddress-table.md">Tabella IPAddress in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-112"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-113">Consente di eseguire il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci utilizzati altrove nel database Quality of Experience.</span><span class="sxs-lookup"><span data-stu-id="82111-113">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-114"><a href="lync-server-2013-networkconnectiondetail-table.md">Tabella NetworkConnectionDetail in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-114"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-115">Esegue il mapping dei tipi di connessione di rete agli identificatori di connessione di rete utilizzati in altri punti del database Quality of Experience.</span><span class="sxs-lookup"><span data-stu-id="82111-115">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-116"><a href="lync-server-2013-purgesettings-table-qoe.md">Tabella PurgeSettings (QoE) in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-116"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-117">Archivia le informazioni che specificano se (e quando) i record di qualità di esperienza obsoleti verranno eliminati automaticamente dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="82111-117">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-118"><a href="lync-server-2013-traceroute-table.md">Tabella TraceRoute in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-118"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-119">Archivia le informazioni di routing per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="82111-119">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-120"><a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-120"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-121">Questa tabella contiene il mapping degli identificatori degli agenti utente ai nomi descrittivi degli agenti.</span><span class="sxs-lookup"><span data-stu-id="82111-121">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-122"><a href="lync-server-2013-videometricsthreshold-table.md">Tabella VideoMetricsThreshold in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-122"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-123">Archivia valori ottimali e accettabili per le metriche sulla qualità delle esperienze utilizzate con le videochiamate.</span><span class="sxs-lookup"><span data-stu-id="82111-123">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-124"><a href="lync-server-2013-useragent-table.md">Tabella UserAgent in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-124"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-125">Archivia le stringhe degli agenti utente SIP (Session Initiation Protocol) e i tipi UA utilizzati nelle sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="82111-125">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-126"><a href="lync-server-2013-user-table.md">Tabella user in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-126"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-127">Archivia gli URI degli utenti, delle conferenze e dei telefoni utilizzati nelle sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="82111-127">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-128"><a href="lync-server-2013-endpoint-table.md">Tabella endpoint in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-128"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-129">Archivia i nomi dei computer FQDN degli endpoint che partecipano alle sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="82111-129">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-130"><a href="lync-server-2013-pool-table.md">Tabella del pool in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-130"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-131">Archivia i nomi dei pool a cui appartengono i dati della metrica.</span><span class="sxs-lookup"><span data-stu-id="82111-131">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-132"><a href="lync-server-2013-device-table.md">Tabella Device in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-132"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-133">Archivia i dispositivi di acquisizione e i dispositivi di rendering utilizzati nelle chiamate audio/video.</span><span class="sxs-lookup"><span data-stu-id="82111-133">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-134"><a href="lync-server-2013-devicedriver-table.md">Tabella QRTDDriver in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-134"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-135">Archivia il driver per il dispositivo di acquisizione e il dispositivo di rendering utilizzati nelle chiamate audio/video.</span><span class="sxs-lookup"><span data-stu-id="82111-135">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-136"><a href="lync-server-2013-conference-table.md">Tabella conferenze in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-136"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-137">Archivia gli URI di conferenza per gli scenari di conferenza o DialogID per altri scenari.</span><span class="sxs-lookup"><span data-stu-id="82111-137">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-138"><a href="lync-server-2013-sessioncorrelation-table.md">Tabella SessionCorrelation in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-138"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-139">Consente di archiviare CorrelationID per le chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="82111-139">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-140"><a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-140"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-141">Archivia il codec utilizzato nelle chiamate audio/video.</span><span class="sxs-lookup"><span data-stu-id="82111-141">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabella AppliedBandwidthSource in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-143">Archivia l'origine della larghezza di banda utilizzata nelle chiamate audio/video.</span><span class="sxs-lookup"><span data-stu-id="82111-143">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-144"><a href="lync-server-2013-macaddress-table.md">Tabella MacAddress in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-144"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-145">Archivia l'indirizzo MAC degli endpoint che partecipano alle sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="82111-145">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-146"><a href="lync-server-2013-dialog-table.md">Tabella Dialog in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-146"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-147">Archivia l'ID della finestra di dialogo delle sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="82111-147">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-148"><a href="lync-server-2013-region-table.md">Tabella Region in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-148"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-149">Archivia l'area di rete definita nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="82111-149">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-150"><a href="lync-server-2013-usersite-table.md">Tabella UserSite in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-150"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-151">Archivia il sito di rete definito nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="82111-151">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-152"><a href="lync-server-2013-subnet-table.md">Tabella subnet in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-152"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-153">Archivia la subnet definita nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="82111-153">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-154"><a href="lync-server-2013-monitoredregionlink-table.md">Tabella MonitoredRegionLink in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-154"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-155">Archivia il collegamento area definito nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="82111-155">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-156"><a href="monitoredusersitelink-table.md">Tabella MonitoredUserSiteLink</a></span><span class="sxs-lookup"><span data-stu-id="82111-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="82111-157">Archivia i collegamenti di sito di rete definiti nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="82111-157">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-158"><a href="lync-server-2013-endpointsubnet-table.md">Tabella EndpointSubnet in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-158"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-159">Archivia la subnet dell'endpoint che partecipa a una sessione audio e video.</span><span class="sxs-lookup"><span data-stu-id="82111-159">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-160"><a href="lync-server-2013-server-table.md">Tabella server in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-160"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-161">Archivia il nome di dominio completo o l'indirizzo IP del server che passa attraverso il supporto.</span><span class="sxs-lookup"><span data-stu-id="82111-161">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82111-162">**Tabelle per i dati di metrica**</span><span class="sxs-lookup"><span data-stu-id="82111-162">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82111-163"><strong>tavolo</strong></span><span class="sxs-lookup"><span data-stu-id="82111-163"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="82111-164"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="82111-164"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82111-165"><a href="lync-server-2013-appsharingstream-table.md">Tabella AppSharingStream in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-165"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-166">Archivia le metriche relative alla qualità delle esperienze per i flussi di rete utilizzati per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="82111-166">Stores Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="82111-167">Metriche sulla qualità delle esperienze per i flussi di rete utilizzati per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="82111-167">Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-168"><a href="lync-server-2013-session-table.md">Tabella di sessione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-168"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-169">Archivia le informazioni generali su una sessione audio o audio/video.</span><span class="sxs-lookup"><span data-stu-id="82111-169">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="82111-170">Una sessione è definita come una finestra di dialogo SIP audio o video tra due endpoint.</span><span class="sxs-lookup"><span data-stu-id="82111-170">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-171"><a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-171"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-172">Archivia informazioni su ogni linea multimediale in una sessione.</span><span class="sxs-lookup"><span data-stu-id="82111-172">Stores information about each media line in a session.</span></span> <span data-ttu-id="82111-173">Una linea multimediale è una raccolta di uno o più flussi audio e video.</span><span class="sxs-lookup"><span data-stu-id="82111-173">A media line is a collection of one or more audio and video streams.</span></span> <span data-ttu-id="82111-174">In genere, una singola linea multimediale avrà due flussi, audio o video.</span><span class="sxs-lookup"><span data-stu-id="82111-174">Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-175"><a href="lync-server-2013-audiostream-table.md">Tabella AudioStream in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-175"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-176">Archivia le metriche per la qualità del supporto audio per ogni flusso audio della linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="82111-176">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-177"><a href="lync-server-2013-audiosignal-table.md">Tabella AudioSignal in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-177"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-178">Archivia le metriche relative alla qualità multimediale audio nella linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="82111-178">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="82111-179">Sono incluse le metriche di annullamento dell'eco acustico (AEC) e di controllo di guadagno automatico (AGC).</span><span class="sxs-lookup"><span data-stu-id="82111-179">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-180"><a href="lync-server-2013-videostream-table.md">Tabella VideoStream in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-180"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-181">Archivia le metriche di qualità multimediale video per ogni flusso audio nella linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="82111-181">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-182"><a href="lync-server-2013-audioclientevent-table.md">Tabella AudioClientEvent in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-182"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-183">Archivia le metriche di qualità multimediale audio raccolte dall'evento client.</span><span class="sxs-lookup"><span data-stu-id="82111-183">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-184"><a href="lync-server-2013-videoclientevent-table.md">Tabella VideoClientEvent in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="82111-184"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="82111-185">Archivia le metriche di qualità multimediale video raccolte dall'evento client.</span><span class="sxs-lookup"><span data-stu-id="82111-185">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-186"><strong>Tabella DiagnosticData</strong></span><span class="sxs-lookup"><span data-stu-id="82111-186"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-187">Archivia i dati di diagnostica solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-187">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82111-188">**Tabelle per i dati di riepilogo**</span><span class="sxs-lookup"><span data-stu-id="82111-188">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82111-189"><strong>tavolo</strong></span><span class="sxs-lookup"><span data-stu-id="82111-189"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="82111-190"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="82111-190"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82111-191"><strong>Tabella ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="82111-191"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-192">Archivia i dati di riepilogo per i server, questi dati vengono utilizzati solo per i report di qualità di esperienza (QoE).</span><span class="sxs-lookup"><span data-stu-id="82111-192">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-193"><strong>Tabella UserSummary</strong></span><span class="sxs-lookup"><span data-stu-id="82111-193"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-194">Archivia i dati di riepilogo per gli utenti, questi dati vengono utilizzati solo per i report QoE.</span><span class="sxs-lookup"><span data-stu-id="82111-194">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-195"><strong>Tabella CallTypeSummary</strong></span><span class="sxs-lookup"><span data-stu-id="82111-195"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-196">Archivia i dati di riepilogo per i tipi di chiamata, questi dati vengono utilizzati solo per i report QoE.</span><span class="sxs-lookup"><span data-stu-id="82111-196">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82111-197">**Tabelle per l'utilizzo interno da parte di Monitoring Server**</span><span class="sxs-lookup"><span data-stu-id="82111-197">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82111-198"><strong>tavolo</strong></span><span class="sxs-lookup"><span data-stu-id="82111-198"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="82111-199"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="82111-199"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82111-200"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="82111-200"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-201">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-201">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-202"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="82111-202"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-203">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-203">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-204"><strong>Tabella FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="82111-204"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-205">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-205">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-206"><strong>Tabella Task</strong></span><span class="sxs-lookup"><span data-stu-id="82111-206"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-207">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-207">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-208"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="82111-208"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-209">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-209">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-210"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="82111-210"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-211">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-211">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-212"><strong>MetricsThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="82111-212"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-213">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-213">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-214"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="82111-214"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-215">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-215">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-216"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="82111-216"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-217">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-217">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-218"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="82111-218"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-219">Solo per utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="82111-219">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-220"><strong>Tabella CallSummary</strong></span><span class="sxs-lookup"><span data-stu-id="82111-220"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-221">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-221">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-222"><strong>Tabella DeviceCallSumary</strong></span><span class="sxs-lookup"><span data-stu-id="82111-222"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-223">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-223">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-224"><strong>Tabella Tenant</strong></span><span class="sxs-lookup"><span data-stu-id="82111-224"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-225">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-225">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82111-226"><strong>VideoCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="82111-226"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-227">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-227">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82111-228"><strong>ASCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="82111-228"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="82111-229">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="82111-229">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

