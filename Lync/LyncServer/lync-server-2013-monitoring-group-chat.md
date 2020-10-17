---
title: 'Lync Server 2013: monitoraggio chat di gruppo'
description: 'Lync Server 2013: monitoraggio chat di gruppo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625e45f455e8dba50a5fa64240b62cb010623d16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562032"
---
# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="dffe2-103">Monitoraggio chat di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dffe2-103">Monitoring group chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dffe2-104">_**Ultimo argomento modificato:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="dffe2-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="dffe2-105">È consigliabile eseguire il [programma di installazione degli aggiornamenti cumulativi del server](https://support.microsoft.com/kb/968802) più recente disponibile nell'area download Microsoft per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="dffe2-105">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="dffe2-106">Presupponendo che si esegua l'aggiornamento cumulativo più recente, utilizzare la tabella di test di stress seguente per valutare se i server di chat di gruppo sono in esecuzione in condizioni di integrità ottimali.</span><span class="sxs-lookup"><span data-stu-id="dffe2-106">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="dffe2-107">Ambiente di testing e modello utente</span><span class="sxs-lookup"><span data-stu-id="dffe2-107">Test environment and user model</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dffe2-108">Tre server chat di gruppo in un pool di chat di gruppo, ognuno con 8 GB di memoria e 8 processori.</span><span class="sxs-lookup"><span data-stu-id="dffe2-108">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dffe2-109">Due front-end di Lync Server 2013 in Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="dffe2-109">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dffe2-110">60.000 utenti simultanei su tre server chat di gruppo.</span><span class="sxs-lookup"><span data-stu-id="dffe2-110">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dffe2-111">25.000 canali ospitati dal pool di chat di gruppo.</span><span class="sxs-lookup"><span data-stu-id="dffe2-111">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dffe2-112">Dimensione canale:</span><span class="sxs-lookup"><span data-stu-id="dffe2-112">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="dffe2-113">Dimensione canale piccolo: 30</span><span class="sxs-lookup"><span data-stu-id="dffe2-113">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="dffe2-114">Dimensione canale medio: 150</span><span class="sxs-lookup"><span data-stu-id="dffe2-114">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="dffe2-115">Dimensione canale di grandi dimensioni: 2500</span><span class="sxs-lookup"><span data-stu-id="dffe2-115">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dffe2-116">Conteggio canali:</span><span class="sxs-lookup"><span data-stu-id="dffe2-116">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="dffe2-117">Canali di piccole dimensioni: 24.000</span><span class="sxs-lookup"><span data-stu-id="dffe2-117">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="dffe2-118">Numero medio di canali 800</span><span class="sxs-lookup"><span data-stu-id="dffe2-118">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="dffe2-119">Numero di canali di grandi dimensioni 24</span><span class="sxs-lookup"><span data-stu-id="dffe2-119">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="dffe2-120">Totale canali 24.824</span><span class="sxs-lookup"><span data-stu-id="dffe2-120">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dffe2-121">Invitare i canali:</span><span class="sxs-lookup"><span data-stu-id="dffe2-121">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="dffe2-122">La metà dei canali sono stati invitare i canali</span><span class="sxs-lookup"><span data-stu-id="dffe2-122">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dffe2-123">Numero di canali che un utente unisce:</span><span class="sxs-lookup"><span data-stu-id="dffe2-123">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="dffe2-124">Piccolo: 12</span><span class="sxs-lookup"><span data-stu-id="dffe2-124">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="dffe2-125">Media: 2</span><span class="sxs-lookup"><span data-stu-id="dffe2-125">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="dffe2-126">Grande: 1</span><span class="sxs-lookup"><span data-stu-id="dffe2-126">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dffe2-127">Tasso di partecipazione:</span><span class="sxs-lookup"><span data-stu-id="dffe2-127">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="dffe2-128">10 totale/secondo, 3,33/secondo per server</span><span class="sxs-lookup"><span data-stu-id="dffe2-128">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dffe2-129">Velocità di logout:</span><span class="sxs-lookup"><span data-stu-id="dffe2-129">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="dffe2-130">10 totale/secondo, 3,33/secondo per server</span><span class="sxs-lookup"><span data-stu-id="dffe2-130">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dffe2-131">Velocità chat:</span><span class="sxs-lookup"><span data-stu-id="dffe2-131">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="dffe2-132">20 totale/secondo, 6.66/secondo per server</span><span class="sxs-lookup"><span data-stu-id="dffe2-132">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="dffe2-133">I numeri di contatore delle prestazioni seguenti variano probabilmente quando si utilizzano specifiche hardware o profili utente diversi.</span><span class="sxs-lookup"><span data-stu-id="dffe2-133">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="dffe2-134">Contatore delle prestazioni da monitorare</span><span class="sxs-lookup"><span data-stu-id="dffe2-134">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dffe2-135">Contatore delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="dffe2-135">Performance Counter</span></span></th>
<th><span data-ttu-id="dffe2-136">Soglie</span><span class="sxs-lookup"><span data-stu-id="dffe2-136">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dffe2-137">Processo (ChannelService)- &gt; % tempo processore</span><span class="sxs-lookup"><span data-stu-id="dffe2-137">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="dffe2-138">Min: 0</span><span class="sxs-lookup"><span data-stu-id="dffe2-138">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

