---
title: 'Lync Server 2013: tabella UserAgent'
description: 'Lync Server 2013: tabella UserAgent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b701d8384313d0267dd566e0c32242f6cc077472
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558892"
---
# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="7ccb7-103">Tabella UserAgent in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ccb7-103">UserAgent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ccb7-104">_**Ultimo argomento modificato:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="7ccb7-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="7ccb7-105">La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato a sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="7ccb7-106">Ogni record nella tabella rappresenta un solo agente utente</span><span class="sxs-lookup"><span data-stu-id="7ccb7-106">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ccb7-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="7ccb7-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7ccb7-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="7ccb7-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7ccb7-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="7ccb7-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7ccb7-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="7ccb7-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ccb7-111"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="7ccb7-111"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7ccb7-112">int</span><span class="sxs-lookup"><span data-stu-id="7ccb7-112">int</span></span></p></td>
<td><p><span data-ttu-id="7ccb7-113">Principale</span><span class="sxs-lookup"><span data-stu-id="7ccb7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="7ccb7-114">Numero univoco che identifica l'agente utente.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-114">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ccb7-115"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="7ccb7-115"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="7ccb7-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7ccb7-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7ccb7-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="7ccb7-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="7ccb7-118">Stringa dell'agente utente.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-118">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ccb7-119"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="7ccb7-119"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="7ccb7-120">smallint</span><span class="sxs-lookup"><span data-stu-id="7ccb7-120">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ccb7-121">1 è Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-121">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="7ccb7-122">2 è A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-122">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="7ccb7-123">4 è Lync.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-123">4 is Lync.</span></span></p>
<p><span data-ttu-id="7ccb7-124">8 è il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-124">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="7ccb7-125">16 è la console di Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-125">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="7ccb7-126">32 è lo strumento di convalida della distribuzione (TVP).</span><span class="sxs-lookup"><span data-stu-id="7ccb7-126">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="7ccb7-127">64 è Lync nei computer Macintosh.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-127">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="7ccb7-128">128 è assistente di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-128">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="7ccb7-129">256 è il servizio Annuncio conferenza.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-129">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="7ccb7-130">512 è operatore automatico di conferenza.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-130">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="7ccb7-131">1024 è un'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-131">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="7ccb7-132">2048 è un controllo vocale esterno.</span><span class="sxs-lookup"><span data-stu-id="7ccb7-132">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

