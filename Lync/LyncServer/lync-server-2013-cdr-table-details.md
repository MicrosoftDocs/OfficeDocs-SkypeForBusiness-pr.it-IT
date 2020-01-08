---
title: 'Lync Server 2013: Dettagli sulle tabelle di registrazione dettagli chiamata (CDR)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f87e681cc25f9ed64509ff3bdb31abc5fd77101d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a>Dettagli sulle tabelle di registrazione dettagli chiamata (CDR) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

Negli argomenti seguenti sono riportate in dettaglio le colonne in ognuna delle tabelle dello schema del database CDR (Call Detail Records).

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Tabella Application in Lync Server 2013](lync-server-2013-application-table.md)

  - [Tabella CallPriorities in Lync Server 2013](lync-server-2013-callpriorities-table.md)

  - [Tabella CallType in Lync Server 2013](lync-server-2013-calltype-table.md)

  - [Tabella ClientVersions in Lync Server 2013](lync-server-2013-clientversions-table.md)

  - [Tabella ConferenceJoinTimeThresholds in Lync Server 2013](lync-server-2013-conferencejointimethresholds-table.md)

  - [Tabella ConferenceMessageCount in Lync Server 2013](lync-server-2013-conferencemessagecount-table.md)

  - [Tabella Conferences in Lync Server 2013](lync-server-2013-conferences-table.md)

  - [Tabella ConferenceSessionDetails in Lync Server 2013](lync-server-2013-conferencesessiondetails-table.md)

  - [Tabella ConferenceUris in Lync Server 2013](lync-server-2013-conferenceuris-table.md)

  - [Tabella ContentTypes in Lync Server 2013](lync-server-2013-contenttypes-table.md)

  - [Tabella DeRegisterType in Lync Server 2013](lync-server-2013-deregistertype-table.md)

  - [Tabella Devices in Lync Server 2013](lync-server-2013-devices-table.md)

  - [Tabella Dialogs in Lync Server 2013](lync-server-2013-dialogs-table.md)

  - [Tabella EdgeServers in Lync Server 2013](lync-server-2013-edgeservers-table.md)

  - [Tabella ErrorCategory in Lync Server 2013](lync-server-2013-errorcategory-table.md)

  - [Tabella ErrorDef in Lync Server 2013](lync-server-2013-errordef-table.md)

  - [Tabella ErrorReport in Lync Server 2013](lync-server-2013-errorreport-table.md)

  - [Tabella FileTransfers in Lync Server 2013](lync-server-2013-filetransfers-table.md)

  - [Tabella FocusJoinsAndLeaves in Lync Server 2013](lync-server-2013-focusjoinsandleaves-table.md)

  - [Tabella FrontEnd in Lync Server 2013](lync-server-2013-frontend-table.md)

  - [Tabella Gateways in Lync Server 2013](lync-server-2013-gateways-table.md)

  - [Tabella HardwareVersions in Lync Server 2013](lync-server-2013-hardwareversions-table.md)

  - [Tabella IMReportSummary in Lync Server 2013](lync-server-2013-imreportsummary-table.md)

  - [Tabella Locations in Lync Server 2013](lync-server-2013-locations-table.md)

  - [Tabella Manufacturers in Lync Server 2013](lync-server-2013-manufacturers-table.md)

  - [Tabella McuJoinsAndLeaves in Lync Server 2013](lync-server-2013-mcujoinsandleaves-table.md)

  - [Tabella Mcus in Lync Server 2013](lync-server-2013-mcus-table.md)

  - [Tabella Media in Lync Server 2013](lync-server-2013-media-table.md)

  - [Tabella MediaList in Lync Server 2013](lync-server-2013-medialist-table.md)

  - [Tabella MediationServers in Lync Server 2013](lync-server-2013-mediationservers-table.md)

  - [Tabella MSMQProcessing in Lync Server 2013](lync-server-2013-msmqprocessing-table.md)

  - [Tabella Phones in Lync Server 2013](lync-server-2013-phones-table.md)

  - [Tabella Pools in Lync Server 2013](lync-server-2013-pools-table.md)

  - [Tabella ProgressReport in Lync Server 2013](lync-server-2013-progressreport-table.md)

  - [Tabella PurgeSettings in Lync Server 2013](lync-server-2013-purgesettings-table.md)

  - [Tabella Registration in Lync Server 2013](lync-server-2013-registration-table.md)

  - [Tabella Roles in Lync Server 2013](lync-server-2013-roles-table.md)

  - [Tabella Servers in Lync Server 2013](lync-server-2013-servers-table.md)

  - [Tabella SessionDetails in Lync Server 2013](lync-server-2013-sessiondetails-table.md)

  - [Tabella SIPResponseMetaData in Lync Server 2013](lync-server-2013-sipresponsemetadata-table.md)

  - [Tabella sindacati in Lync Server 2013](lync-server-2013-syndicators-table.md)

  - [Tabella SyndicatorsTenantMap in Lync Server 2013](lync-server-2013-syndicatorstenantmap-table.md)

  - [Tabella delle attività in Lync Server 2013](lync-server-2013-task-table.md)

  - [Tabella Tenants in Lync Server 2013](lync-server-2013-tenants-table.md)

  - [Tabella UriTypes in Lync Server 2013](lync-server-2013-uritypes-table.md)

  - [Tabella Users in Lync Server 2013](lync-server-2013-users-table.md)

  - [Tabella UserAgentDef in Lync Server 2013](lync-server-2013-useragentdef-table.md)

  - [Tabella UserStatistics in Lync Server 2013](lync-server-2013-userstatistics-table.md)

  - [Tabella VoipDetails in Lync Server 2013](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

