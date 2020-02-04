---
title: Introduzione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 893205127b6b1ccba958a0882c3aa0d1360a7c06
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="bb455-102">Introduzione</span><span class="sxs-lookup"><span data-stu-id="bb455-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb455-103">_**Argomento Ultima modifica:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="bb455-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="bb455-104">Lo strumento di stress e prestazioni di Lync Server 2013 (denominato LyncPerfTool) può simulare il caricamento degli utenti dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb455-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb455-105">Messaggistica istantanea (IM) e presenza</span><span class="sxs-lookup"><span data-stu-id="bb455-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="bb455-106">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="bb455-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb455-107">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="bb455-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="bb455-108">Voice over IP (VoIP), inclusa la simulazione PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="bb455-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb455-109">Servizi di conferenza client di Web Access</span><span class="sxs-lookup"><span data-stu-id="bb455-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="bb455-110">Assistente di Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bb455-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb455-111">Response Group</span><span class="sxs-lookup"><span data-stu-id="bb455-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="bb455-112">Espansione della lista di distribuzione</span><span class="sxs-lookup"><span data-stu-id="bb455-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb455-113">Query di download e Rubrica per la Rubrica</span><span class="sxs-lookup"><span data-stu-id="bb455-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="bb455-114">Chiamate e profilo della posizione avanzati di 9-1-1 (E9-1-1) (dial plan)</span><span class="sxs-lookup"><span data-stu-id="bb455-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb455-115">MultiView</span><span class="sxs-lookup"><span data-stu-id="bb455-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="bb455-116">Visualizzazione di più flussi da una conferenza</span><span class="sxs-lookup"><span data-stu-id="bb455-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bb455-117">Lo strumento per lo stress e le prestazioni di Lync Server 2013 supporta la generazione di carichi tra pool e la Federazione tramite la configurazione avanzata.</span><span class="sxs-lookup"><span data-stu-id="bb455-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="bb455-118">Lo strumento non simula inoltre il caricamento degli utenti per i client seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb455-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="bb455-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="bb455-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="bb455-120">Chat persistente di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bb455-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="bb455-121">Di conseguenza, lo strumento di analisi dello stress e delle prestazioni di Lync Server 2013 non supporta i test dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb455-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="bb455-122">Chat persistente di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bb455-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="bb455-123">Scenari di integrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="bb455-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="bb455-124">Applicazioni e file inclusi nello strumento per lo stress e le prestazioni di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb455-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="bb455-125">Le applicazioni seguenti sono incluse nello strumento per lo stress e le prestazioni di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="bb455-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb455-126">Strumento</span><span class="sxs-lookup"><span data-stu-id="bb455-126">Tool</span></span></th>
<th><span data-ttu-id="bb455-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb455-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb455-128">UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="bb455-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="bb455-129">Strumento di provisioning degli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb455-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="bb455-130">Questo strumento viene usato per creare utenti e contatti.</span><span class="sxs-lookup"><span data-stu-id="bb455-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb455-131">UserProfileGenerator. exe</span><span class="sxs-lookup"><span data-stu-id="bb455-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="bb455-132">Strumento di configurazione del caricamento di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb455-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="bb455-133">Questo strumento viene usato per configurare le caratteristiche del carico utente da simulare.</span><span class="sxs-lookup"><span data-stu-id="bb455-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb455-134">LyncPerfTool. exe</span><span class="sxs-lookup"><span data-stu-id="bb455-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="bb455-135">Strumento di stress e prestazioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb455-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="bb455-136">LyncPerfTool è lo strumento che simula il caricamento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bb455-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb455-137">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="bb455-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="bb455-138">Per usare lo strumento di registrazione di Lync Server 2013 è necessario default. TMX.</span><span class="sxs-lookup"><span data-stu-id="bb455-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb455-139">Esempio di provisioning di script</span><span class="sxs-lookup"><span data-stu-id="bb455-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="bb455-140">Questi esempi vengono usati per configurare la topologia per l'eseguire test di carico, in base a scenari specifici</span><span class="sxs-lookup"><span data-stu-id="bb455-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

