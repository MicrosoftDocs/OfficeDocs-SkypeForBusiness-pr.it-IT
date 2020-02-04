---
title: 'Lync Server 2013: Dettagli sulle tabelle di registrazione dettagli chiamata (CDR)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 650caa5244eaf796c066f1388f2fcbb5d3b0703a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="0085c-102">Dettagli sulle tabelle di registrazione dettagli chiamata (CDR) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0085c-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="0085c-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="0085c-104">Negli argomenti seguenti sono riportate in dettaglio le colonne in ognuna delle tabelle dello schema del database CDR (Call Detail Records).</span><span class="sxs-lookup"><span data-stu-id="0085c-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0085c-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0085c-105">In This Section</span></span>

  - [<span data-ttu-id="0085c-106">Tabella Application in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="0085c-107">Tabella CallPriorities in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="0085c-108">Tabella CallType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="0085c-109">Tabella ClientVersions in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="0085c-110">Tabella ConferenceJoinTimeThresholds in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="0085c-111">Tabella ConferenceMessageCount in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="0085c-112">Tabella Conferences in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="0085c-113">Tabella ConferenceSessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="0085c-114">Tabella ConferenceUris in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="0085c-115">Tabella ContentTypes in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="0085c-116">Tabella DeRegisterType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="0085c-117">Tabella Devices in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="0085c-118">Tabella Dialogs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="0085c-119">Tabella EdgeServers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="0085c-120">Tabella ErrorCategory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="0085c-121">Tabella ErrorDef in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="0085c-122">Tabella ErrorReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="0085c-123">Tabella FileTransfers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="0085c-124">Tabella FocusJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="0085c-125">Tabella FrontEnd in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="0085c-126">Tabella Gateways in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="0085c-127">Tabella HardwareVersions in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="0085c-128">Tabella IMReportSummary in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="0085c-129">Tabella Locations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="0085c-130">Tabella Manufacturers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="0085c-131">Tabella McuJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="0085c-132">Tabella Mcus in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="0085c-133">Tabella Media in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="0085c-134">Tabella MediaList in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="0085c-135">Tabella MediationServers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="0085c-136">Tabella MSMQProcessing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="0085c-137">Tabella Phones in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="0085c-138">Tabella Pools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="0085c-139">Tabella ProgressReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="0085c-140">Tabella PurgeSettings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="0085c-141">Tabella Registration in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="0085c-142">Tabella Roles in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="0085c-143">Tabella Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="0085c-144">Tabella SessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="0085c-145">Tabella SIPResponseMetaData in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="0085c-146">Tabella sindacati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="0085c-147">Tabella SyndicatorsTenantMap in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="0085c-148">Tabella delle attività in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="0085c-149">Tabella Tenants in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="0085c-150">Tabella UriTypes in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="0085c-151">Tabella Users in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="0085c-152">Tabella UserAgentDef in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="0085c-153">Tabella UserStatistics in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="0085c-154">Tabella VoipDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0085c-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

