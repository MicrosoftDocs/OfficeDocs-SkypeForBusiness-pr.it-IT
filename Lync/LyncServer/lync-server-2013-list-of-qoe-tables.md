---
title: 'Lync Server 2013: Elenco delle tabelle QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c82c38a995fd9e847057fedbbce1422085332b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="d7fee-102">Elenco delle tabelle QoE in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7fee-102">List of QoE tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7fee-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d7fee-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d7fee-104">Lo schema del database è costituito dalle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="d7fee-104">The database schema consists of the following tables.</span></span>

<span data-ttu-id="d7fee-105">**Tabelle di supporto**</span><span class="sxs-lookup"><span data-stu-id="d7fee-105">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7fee-106"><strong>Tabella</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-106"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="d7fee-107"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-107"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabella AppSharingMetricsThreshold in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-109">Consente di archiviare valori ottimali e accettabili per la qualità delle metriche di esperienza usate con la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d7fee-109">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-110"><a href="lync-server-2013-codecdescription-table.md">Tabella CodecDescription in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-110"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-111">Associa gli identificatori di codec univoci al relativo codec.</span><span class="sxs-lookup"><span data-stu-id="d7fee-111">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-112"><a href="lync-server-2013-ipaddress-table.md">Tabella IPAddress in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-112"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-113">Esegue il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci usati altrove nel database qualità di esperienza.</span><span class="sxs-lookup"><span data-stu-id="d7fee-113">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-114"><a href="lync-server-2013-networkconnectiondetail-table.md">Tabella NetworkConnectionDetail in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-114"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-115">Associa i tipi di connessione di rete agli identificatori di connessione di rete usati in un altro punto del database qualità dell'esperienza.</span><span class="sxs-lookup"><span data-stu-id="d7fee-115">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-116"><a href="lync-server-2013-purgesettings-table-qoe.md">Tabella PurgeSettings (QoE) in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-116"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-117">Archivia le informazioni che specificano se (e quando) la qualità obsoleta dei record dell'esperienza verrà eliminata automaticamente dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="d7fee-117">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-118"><a href="lync-server-2013-traceroute-table.md">Tabella TraceRoute in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-118"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-119">Archivia le informazioni di routing per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="d7fee-119">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-120"><a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-120"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-121">Associa gli identificatori dell'agente utente ai nomi descrittivi dell'agente.</span><span class="sxs-lookup"><span data-stu-id="d7fee-121">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-122"><a href="lync-server-2013-videometricsthreshold-table.md">Tabella VideoMetricsThreshold in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-122"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-123">Consente di archiviare valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con videochiamate.</span><span class="sxs-lookup"><span data-stu-id="d7fee-123">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-124"><a href="lync-server-2013-useragent-table.md">Tabella UserAgent in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-124"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-125">Archivia le stringhe degli agenti utente SIP (Session Initiation Protocol) e i tipi UA usati nelle sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-125">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-126"><a href="lync-server-2013-user-table.md">Tabella User in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-126"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-127">Archivia gli URI dell'utente, della conferenza e del telefono usati nelle sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-127">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-128"><a href="lync-server-2013-endpoint-table.md">Tabella Endpoint in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-128"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-129">Archivia i nomi di computer FQDN degli endpoint che partecipano a sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-129">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-130"><a href="lync-server-2013-pool-table.md">Tabella Pool in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-130"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-131">Archivia i nomi dei pool a cui appartengono i dati della metrica.</span><span class="sxs-lookup"><span data-stu-id="d7fee-131">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-132"><a href="lync-server-2013-device-table.md">Tabella Device in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-132"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-133">Archivia i dispositivi di acquisizione e i dispositivi di rendering usati in una chiamata audio/video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-133">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-134"><a href="lync-server-2013-devicedriver-table.md">Tabella DeviceDriver in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-134"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-135">Archivia il driver per il dispositivo di acquisizione e il dispositivo di rendering usato nelle chiamate audio/video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-135">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-136"><a href="lync-server-2013-conference-table.md">Tabella Conference in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-136"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-137">Archivia gli URI della conferenza per gli scenari di conferenza o DialogID per altri scenari.</span><span class="sxs-lookup"><span data-stu-id="d7fee-137">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-138"><a href="lync-server-2013-sessioncorrelation-table.md">Tabella SessionCorrelation in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-138"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-139">Memorizza CorrelationID per le chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="d7fee-139">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-140"><a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-140"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-141">Archivia il codec usato nelle chiamate audio/video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-141">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabella AppliedBandwidthSource in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-143">Archivia l'origine della larghezza di banda usata nelle chiamate audio/video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-143">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-144"><a href="lync-server-2013-macaddress-table.md">Tabella MacAddress in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-144"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-145">Archivia l'indirizzo MAC degli endpoint che partecipano a sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-145">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-146"><a href="lync-server-2013-dialog-table.md">Tabella Dialog in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-146"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-147">Archivia l'ID della finestra di dialogo delle sessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-147">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-148"><a href="lync-server-2013-region-table.md">Tabella Region in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-148"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-149">Archivia l'area di rete definita in impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="d7fee-149">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-150"><a href="lync-server-2013-usersite-table.md">Tabella UserSite in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-150"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-151">Archivia il sito di rete definito nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="d7fee-151">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-152"><a href="lync-server-2013-subnet-table.md">Tabella Subnet in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-152"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-153">Archivia la subnet definita nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="d7fee-153">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-154"><a href="lync-server-2013-monitoredregionlink-table.md">Tabella MonitoredRegionLink in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-154"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-155">Archivia il collegamento all'area geografica definito nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="d7fee-155">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-156"><a href="monitoredusersitelink-table.md">Tabella MonitoredUserSiteLink</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-157">Archivia i collegamenti ai siti di rete definiti nell'impostazione NCS.</span><span class="sxs-lookup"><span data-stu-id="d7fee-157">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-158"><a href="lync-server-2013-endpointsubnet-table.md">Tabella EndpointSubnet in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-158"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-159">Archivia la subnet dell'endpoint che partecipa a una sessione audio e video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-159">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-160"><a href="lync-server-2013-server-table.md">Tabella Server in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-160"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-161">Archivia il nome di dominio completo o l'indirizzo IP del server in cui passa il contenuto multimediale.</span><span class="sxs-lookup"><span data-stu-id="d7fee-161">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d7fee-162">**Tabelle per i dati delle metriche**</span><span class="sxs-lookup"><span data-stu-id="d7fee-162">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7fee-163"><strong>Tabella</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-163"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="d7fee-164"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-164"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-165"><a href="lync-server-2013-appsharingstream-table.md">Tabella AppSharingStream in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-165"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-166">Archivia la qualità delle metriche dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d7fee-166">Stores Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="d7fee-167">Qualità delle metriche dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d7fee-167">Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-168"><a href="lync-server-2013-session-table.md">Tabella Session in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-168"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-169">Archivia informazioni generali su una sessione audio o audio/video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-169">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="d7fee-170">Una sessione viene definita come una finestra di dialogo SIP audio o video tra due endpoint.</span><span class="sxs-lookup"><span data-stu-id="d7fee-170">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-171"><a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-171"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-172">Archivia informazioni su ogni riga multimediale di una sessione.</span><span class="sxs-lookup"><span data-stu-id="d7fee-172">Stores information about each media line in a session.</span></span> <span data-ttu-id="d7fee-173">Una linea media è una raccolta di uno o più flussi audio e video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-173">A media line is a collection of one or more audio and video streams.</span></span> <span data-ttu-id="d7fee-174">In genere, una singola linea multimediale avrà due flussi, audio o video.</span><span class="sxs-lookup"><span data-stu-id="d7fee-174">Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-175"><a href="lync-server-2013-audiostream-table.md">Tabella AudioStream in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-175"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-176">Memorizza le metriche per la qualità del supporto audio per ogni flusso audio nella linea media.</span><span class="sxs-lookup"><span data-stu-id="d7fee-176">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-177"><a href="lync-server-2013-audiosignal-table.md">Tabella AudioSignal in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-177"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-178">Memorizza le metriche di qualità per i supporti audio nella linea media.</span><span class="sxs-lookup"><span data-stu-id="d7fee-178">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="d7fee-179">Sono incluse le metriche per l'annullamento dell'eco acustica (AEC) e il controllo automatico del guadagno (AGC).</span><span class="sxs-lookup"><span data-stu-id="d7fee-179">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-180"><a href="lync-server-2013-videostream-table.md">Tabella VideoStream in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-180"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-181">Archivia le metriche di qualità multimediali video per ogni flusso audio nella linea media.</span><span class="sxs-lookup"><span data-stu-id="d7fee-181">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-182"><a href="lync-server-2013-audioclientevent-table.md">Tabella AudioClientEvent in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-182"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-183">Archivia le metriche di qualità del supporto audio raccolte dall'evento client.</span><span class="sxs-lookup"><span data-stu-id="d7fee-183">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-184"><a href="lync-server-2013-videoclientevent-table.md">Tabella VideoClientEvent in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d7fee-184"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fee-185">Archivia le metriche di qualità multimediali video raccolte dall'evento client.</span><span class="sxs-lookup"><span data-stu-id="d7fee-185">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-186"><strong>Tabella DiagnosticData</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-186"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-187">Archivia i dati di diagnostica solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-187">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d7fee-188">**Tabelle per i dati di riepilogo**</span><span class="sxs-lookup"><span data-stu-id="d7fee-188">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7fee-189"><strong>Tabella</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-189"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="d7fee-190"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-190"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-191"><strong>Tabella ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-191"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-192">Archivia i dati di riepilogo per i server, questi dati vengono usati solo per i report di qualità dell'esperienza (QoE).</span><span class="sxs-lookup"><span data-stu-id="d7fee-192">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-193"><strong>Tabella UserSummary</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-193"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-194">Archivia i dati di riepilogo per gli utenti, questi dati vengono usati solo per i report QoE.</span><span class="sxs-lookup"><span data-stu-id="d7fee-194">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-195"><strong>Tabella CallTypeSummary</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-195"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-196">Archiviare i dati di riepilogo per i tipi di chiamata, questi dati vengono usati solo per i report QoE.</span><span class="sxs-lookup"><span data-stu-id="d7fee-196">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d7fee-197">**Tabelle per l'uso interno tramite Monitoring Server**</span><span class="sxs-lookup"><span data-stu-id="d7fee-197">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7fee-198"><strong>Tabella</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-198"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="d7fee-199"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-199"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-200"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-200"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-201">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-201">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-202"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-202"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-203">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-203">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-204"><strong>Tabella FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-204"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-205">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-205">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-206"><strong>Tabella delle attività</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-206"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-207">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-207">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-208"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-208"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-209">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-209">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-210"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-210"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-211">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-211">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-212"><strong>MetricsThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-212"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-213">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-213">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-214"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-214"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-215">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-215">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-216"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-216"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-217">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-217">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-218"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-218"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-219">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-219">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-220"><strong>Tabella CallSummary</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-220"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-221">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-221">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-222"><strong>Tabella DeviceCallSumary</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-222"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-223">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-223">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-224"><strong>Tabella tenant</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-224"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-225">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-225">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fee-226"><strong>VideoCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-226"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-227">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-227">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fee-228"><strong>ASCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="d7fee-228"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="d7fee-229">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="d7fee-229">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

