---
title: Introduzione
description: Introduzione.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb847c499bde077ccaf2aa050de801ceeedcc6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565282"
---
# <a name="introduction"></a><span data-ttu-id="85eed-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="85eed-103">Introduction</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85eed-104">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="85eed-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="85eed-105">Lo strumento di stress e prestazioni di Lync Server 2013 (denominato LyncPerfTool) può simulare il carico degli utenti dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="85eed-105">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85eed-106">Servizi di messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="85eed-106">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="85eed-107">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="85eed-107">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85eed-108">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="85eed-108">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="85eed-109">VoIP (Voice over IP), inclusa la simulazione PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="85eed-109">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85eed-110">Servizi di conferenza client di accesso Web</span><span class="sxs-lookup"><span data-stu-id="85eed-110">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="85eed-111">Operatore Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="85eed-111">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85eed-112">Response Group</span><span class="sxs-lookup"><span data-stu-id="85eed-112">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="85eed-113">Espansione della lista di distribuzione</span><span class="sxs-lookup"><span data-stu-id="85eed-113">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85eed-114">Download della Rubrica e query della Rubrica</span><span class="sxs-lookup"><span data-stu-id="85eed-114">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="85eed-115">Chiamate e profili delle posizioni migliorati di 9-1-1 (E9-1-1) (dial plan)</span><span class="sxs-lookup"><span data-stu-id="85eed-115">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85eed-116">MultiView</span><span class="sxs-lookup"><span data-stu-id="85eed-116">MultiView</span></span></p></td>
<td><p><span data-ttu-id="85eed-117">Visualizzazione di più flussi da una conferenza</span><span class="sxs-lookup"><span data-stu-id="85eed-117">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85eed-118">Lo strumento Lync Server 2013 stress and performance supporta la generazione e la Federazione dei carichi tra pool solo tramite la configurazione avanzata.</span><span class="sxs-lookup"><span data-stu-id="85eed-118">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="85eed-119">Nello strumento non è inoltre possibile simulare il carico utente per i client seguenti:</span><span class="sxs-lookup"><span data-stu-id="85eed-119">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="85eed-120">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="85eed-120">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="85eed-121">Lync 2013 Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="85eed-121">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="85eed-122">Di conseguenza, lo strumento di analisi dello stress e delle prestazioni di Lync Server 2013 non supporterà i test dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="85eed-122">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="85eed-123">Lync 2013 Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="85eed-123">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="85eed-124">Scenari di integrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="85eed-124">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="85eed-125">Applicazioni e file inclusi nello strumento di stress e prestazioni di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85eed-125">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="85eed-126">Nello strumento di stress e prestazioni di Lync Server 2013 sono incluse le applicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85eed-126">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85eed-127">Strumento</span><span class="sxs-lookup"><span data-stu-id="85eed-127">Tool</span></span></th>
<th><span data-ttu-id="85eed-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85eed-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85eed-129">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="85eed-129">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="85eed-130">Lo strumento di provisioning degli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85eed-130">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="85eed-131">Questo strumento viene utilizzato per creare utenti e contatti.</span><span class="sxs-lookup"><span data-stu-id="85eed-131">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85eed-132">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="85eed-132">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="85eed-133">Strumento di configurazione del caricamento di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85eed-133">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="85eed-134">Questo strumento viene utilizzato per configurare le caratteristiche del carico utente da simulare.</span><span class="sxs-lookup"><span data-stu-id="85eed-134">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85eed-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="85eed-135">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="85eed-136">Strumento di stress e prestazioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85eed-136">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="85eed-137">LyncPerfTool è lo strumento che simula il caricamento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="85eed-137">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85eed-138">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="85eed-138">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="85eed-139">Default. TMX è necessario per utilizzare lo strumento di registrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85eed-139">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85eed-140">Script di provisioning di esempio</span><span class="sxs-lookup"><span data-stu-id="85eed-140">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="85eed-141">Questi esempi vengono utilizzati per configurare la topologia per l'esecuzione di test di carico, in base a scenari specifici</span><span class="sxs-lookup"><span data-stu-id="85eed-141">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

