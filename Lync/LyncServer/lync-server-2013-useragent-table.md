---
title: 'Lync Server 2013: tabella UserAgent'
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
ms.openlocfilehash: 0ba13a18436c7a55ca68931ff2794fd584be84f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="b7518-102">Tabella UserAgent in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7518-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7518-103">_**Ultimo argomento modificato:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="b7518-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="b7518-104">La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato a sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="b7518-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="b7518-105">Ogni record nella tabella rappresenta un solo agente utente</span><span class="sxs-lookup"><span data-stu-id="b7518-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7518-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="b7518-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b7518-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="b7518-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b7518-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="b7518-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b7518-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="b7518-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7518-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="b7518-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b7518-111">int</span><span class="sxs-lookup"><span data-stu-id="b7518-111">int</span></span></p></td>
<td><p><span data-ttu-id="b7518-112">Principale</span><span class="sxs-lookup"><span data-stu-id="b7518-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b7518-113">Numero univoco che identifica l'agente utente.</span><span class="sxs-lookup"><span data-stu-id="b7518-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7518-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="b7518-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="b7518-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b7518-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7518-116">Univoco</span><span class="sxs-lookup"><span data-stu-id="b7518-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="b7518-117">Stringa dell'agente utente.</span><span class="sxs-lookup"><span data-stu-id="b7518-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7518-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="b7518-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="b7518-119">smallint</span><span class="sxs-lookup"><span data-stu-id="b7518-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b7518-120">1 è Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="b7518-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="b7518-121">2 è A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="b7518-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="b7518-122">4 è Lync.</span><span class="sxs-lookup"><span data-stu-id="b7518-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="b7518-123">8 è il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="b7518-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="b7518-124">16 è la console di Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="b7518-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="b7518-125">32 è lo strumento di convalida della distribuzione (TVP).</span><span class="sxs-lookup"><span data-stu-id="b7518-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="b7518-126">64 è Lync nei computer Macintosh.</span><span class="sxs-lookup"><span data-stu-id="b7518-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="b7518-127">128 è assistente di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b7518-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="b7518-128">256 è il servizio Annuncio conferenza.</span><span class="sxs-lookup"><span data-stu-id="b7518-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="b7518-129">512 è operatore automatico di conferenza.</span><span class="sxs-lookup"><span data-stu-id="b7518-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="b7518-130">1024 è un'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="b7518-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="b7518-131">2048 è un controllo vocale esterno.</span><span class="sxs-lookup"><span data-stu-id="b7518-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

