---
title: 'Lync Server 2013: dettagli della tabella CDR'
description: 'Lync Server 2013: dettagli della tabella CDR.'
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
ms.openlocfilehash: 331a3dfd4ffccac2ac4a442eeb9ad9171defb41c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544392"
---
# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="61077-103">Dettagli della tabella CDR in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-103">CDR table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61077-104">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="61077-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="61077-105">Negli argomenti seguenti vengono descritte le colonne di ogni tabella dello schema di database di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="61077-105">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="61077-106">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="61077-106">In This Section</span></span>

  - [<span data-ttu-id="61077-107">Tabella Application in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-107">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="61077-108">Tabella CallPriorities in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-108">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="61077-109">Tabella CallType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-109">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="61077-110">Tabella ClientVersions in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-110">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="61077-111">Tabella ConferenceJoinTimeThresholds in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-111">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="61077-112">Tabella ConferenceMessageCount in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-112">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="61077-113">Tabella Conferences in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-113">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="61077-114">Tabella ConferenceSessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-114">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="61077-115">Tabella ConferenceUris in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-115">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="61077-116">Tabella ContentTypes in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-116">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="61077-117">Tabella DeRegisterType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-117">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="61077-118">Tabella Devices in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-118">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="61077-119">Tabella Dialogs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-119">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="61077-120">Tabella EdgeServers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-120">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="61077-121">Tabella ErrorCategory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-121">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="61077-122">Tabella ErrorDef in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-122">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="61077-123">Tabella ErrorReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-123">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="61077-124">Tabella FileTransfers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-124">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="61077-125">Tabella FocusJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-125">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="61077-126">Tabella front-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-126">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="61077-127">Tabella Gateways in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-127">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="61077-128">Tabella HardwareVersions in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-128">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="61077-129">Tabella IMReportSummary in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-129">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="61077-130">Tabella Locations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-130">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="61077-131">Tabella Manufacturers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-131">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="61077-132">Tabella McuJoinsAndLeaves in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-132">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="61077-133">Tabella MCU in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-133">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="61077-134">Tabella multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-134">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="61077-135">Tabella media in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-135">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="61077-136">Tabella MediationServers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-136">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="61077-137">Tabella MSMQProcessing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-137">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="61077-138">Tabella Phones in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-138">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="61077-139">Tabella Pools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-139">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="61077-140">Tabella ProgressReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-140">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="61077-141">Tabella PurgeSettings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-141">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="61077-142">Tabella di registrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-142">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="61077-143">Tabella Roles in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-143">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="61077-144">Tabella Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-144">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="61077-145">Tabella SessionDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-145">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="61077-146">Tabella SIPResponseMetaData in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-146">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="61077-147">Tabella Syndicates in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-147">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="61077-148">Tabella SyndicatorsTenantMap in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-148">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="61077-149">Tabella delle attività in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-149">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="61077-150">Tabella Tenants in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-150">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="61077-151">Tabella UriTypes in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-151">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="61077-152">Tabella Users in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-152">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="61077-153">Tabella UserAgentDef in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-153">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="61077-154">Tabella UserStatistics in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-154">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="61077-155">Tabella VoipDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61077-155">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

