---
title: 'Lync Server 2013: monitoraggio chat di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74897191cac7559237e961b7600a3ed478d11e58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="ad96d-102">Monitoraggio della chat di gruppo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad96d-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad96d-103">_**Argomento Ultima modifica:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="ad96d-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="ad96d-104">Ti consigliamo vivamente di eseguire il [programma di installazione dell'aggiornamento cumulativo](http://support.microsoft.com/kb/968802) più recente disponibile nell'area download Microsoft per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ad96d-104">We highly recommend running the most recent [Cumulative Server Update Installer](http://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="ad96d-105">Supponendo che l'aggiornamento cumulativo sia stato eseguito più tardi, usare la tabella di test di stress seguente per la metrica per capire se i server di chat di gruppo sono in uso in condizioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="ad96d-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="ad96d-106">Ambiente di test e modello utente</span><span class="sxs-lookup"><span data-stu-id="ad96d-106">Test environment and user model</span></span>

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
<td><p><span data-ttu-id="ad96d-107">Tre server di chat di gruppo in un pool di chat di gruppo, ognuno con 8 GB di memoria e 8 processori.</span><span class="sxs-lookup"><span data-stu-id="ad96d-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad96d-108">Due front ends di Lync Server 2013 in Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="ad96d-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad96d-109">60.000 utenti simultanei in tre server di chat di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ad96d-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad96d-110">25.000 canali ospitati dal pool di chat di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ad96d-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad96d-111">Dimensioni canale:</span><span class="sxs-lookup"><span data-stu-id="ad96d-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad96d-112">Dimensioni canale piccolo: 30</span><span class="sxs-lookup"><span data-stu-id="ad96d-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="ad96d-113">Dimensioni canale medio: 150</span><span class="sxs-lookup"><span data-stu-id="ad96d-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="ad96d-114">Dimensioni canale grande: 2500</span><span class="sxs-lookup"><span data-stu-id="ad96d-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad96d-115">Conteggio canali:</span><span class="sxs-lookup"><span data-stu-id="ad96d-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad96d-116">Numero di canali piccoli: 24.000</span><span class="sxs-lookup"><span data-stu-id="ad96d-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="ad96d-117">Numero medio canali 800</span><span class="sxs-lookup"><span data-stu-id="ad96d-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="ad96d-118">Canali numero grande 24</span><span class="sxs-lookup"><span data-stu-id="ad96d-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="ad96d-119">Totale canali 24.824</span><span class="sxs-lookup"><span data-stu-id="ad96d-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad96d-120">Invitare i canali:</span><span class="sxs-lookup"><span data-stu-id="ad96d-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad96d-121">La metà dei canali sono stati invitare canali</span><span class="sxs-lookup"><span data-stu-id="ad96d-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad96d-122">Numero di canali che un utente si unisce:</span><span class="sxs-lookup"><span data-stu-id="ad96d-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad96d-123">Dimensioni minime: 12</span><span class="sxs-lookup"><span data-stu-id="ad96d-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="ad96d-124">Media: 2</span><span class="sxs-lookup"><span data-stu-id="ad96d-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="ad96d-125">Dimensioni: 1</span><span class="sxs-lookup"><span data-stu-id="ad96d-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad96d-126">Tasso di partecipazione:</span><span class="sxs-lookup"><span data-stu-id="ad96d-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad96d-127">10 totale/secondo, 3.33/secondo per server</span><span class="sxs-lookup"><span data-stu-id="ad96d-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad96d-128">Velocità di logout:</span><span class="sxs-lookup"><span data-stu-id="ad96d-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad96d-129">10 totale/secondo, 3.33/secondo per server</span><span class="sxs-lookup"><span data-stu-id="ad96d-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad96d-130">Tariffa chat:</span><span class="sxs-lookup"><span data-stu-id="ad96d-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="ad96d-131">20 totali/secondi, 6.66/secondo per server</span><span class="sxs-lookup"><span data-stu-id="ad96d-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="ad96d-132">I numeri di contatore delle prestazioni seguenti possono variare in caso di utilizzo di specifiche hardware o profili utente diversi.</span><span class="sxs-lookup"><span data-stu-id="ad96d-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="ad96d-133">Contatore delle prestazioni da monitorare</span><span class="sxs-lookup"><span data-stu-id="ad96d-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad96d-134">Contatore delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="ad96d-134">Performance Counter</span></span></th>
<th><span data-ttu-id="ad96d-135">Le soglie</span><span class="sxs-lookup"><span data-stu-id="ad96d-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad96d-136">Processo (ChannelService)-&gt;% tempo processore</span><span class="sxs-lookup"><span data-stu-id="ad96d-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="ad96d-137">Min: 0</span><span class="sxs-lookup"><span data-stu-id="ad96d-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

