---
title: 'Lync Server 2013: tabella ConferenceUris'
description: 'Lync Server 2013: tabella ConferenceUris.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a142aa9ad1fe4d3ae92aa3e21aa9eee505457cbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566742"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="a63ad-103">Tabella ConferenceUris in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a63ad-103">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a63ad-104">_**Ultimo argomento modificato:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="a63ad-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="a63ad-p101">La tabella ConferenceUris è una tabella di supporto in cui viene archiviato un elenco dei diversi URI conferenza che hanno partecipato a sessioni di conferenze registrate nel database. Ogni record della tabella rappresenta un URI conferenza.</span><span class="sxs-lookup"><span data-stu-id="a63ad-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a63ad-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="a63ad-107">Column</span></span></th>
<th><span data-ttu-id="a63ad-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a63ad-108">Data Type</span></span></th>
<th><span data-ttu-id="a63ad-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="a63ad-109">Key/Index</span></span></th>
<th><span data-ttu-id="a63ad-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a63ad-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a63ad-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="a63ad-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="a63ad-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a63ad-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="a63ad-113">Principale</span><span class="sxs-lookup"><span data-stu-id="a63ad-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a63ad-114">Timestamp, utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="a63ad-114">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a63ad-115"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="a63ad-115"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="a63ad-116">int</span><span class="sxs-lookup"><span data-stu-id="a63ad-116">int</span></span></p></td>
<td><p><span data-ttu-id="a63ad-117">Principale</span><span class="sxs-lookup"><span data-stu-id="a63ad-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="a63ad-118">Numero univoco che identifica l'URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="a63ad-118">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a63ad-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="a63ad-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a63ad-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a63ad-120">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a63ad-121">URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="a63ad-121">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a63ad-122"><strong>Checksum</strong></span><span class="sxs-lookup"><span data-stu-id="a63ad-122"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="a63ad-123">int</span><span class="sxs-lookup"><span data-stu-id="a63ad-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a63ad-p102">Checksum di ConferenceUri. Utilizzato per aumentare la velocità delle ricerche nel database.</span><span class="sxs-lookup"><span data-stu-id="a63ad-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a63ad-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="a63ad-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="a63ad-127">int</span><span class="sxs-lookup"><span data-stu-id="a63ad-127">int</span></span></p></td>
<td><p><span data-ttu-id="a63ad-128">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a63ad-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a63ad-129">Tipo di URI, ad esempio conf:chat per la conferenza di messaggistica istantanea o conf:audio-video per la conferenza audio e video.</span><span class="sxs-lookup"><span data-stu-id="a63ad-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="a63ad-130">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes nella tabella Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a63ad-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

