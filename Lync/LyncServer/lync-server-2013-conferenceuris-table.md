---
title: 'Lync Server 2013: Tabella ConferenceUris'
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
ms.openlocfilehash: 3cacbaf4e8c7c826ae2e00e9c86b44cc8387f315
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="bfbe2-102">Tabella ConferenceUris in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfbe2-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfbe2-103">_**Argomento Ultima modifica:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="bfbe2-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="bfbe2-104">La tabella ConfereneUris è una tabella di supporto in cui è archiviato un elenco dei vari URI di conferenza che hanno partecipato a sessioni di conferenza registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="bfbe2-105">Ogni record nella tabella rappresenta un URI di conferenza.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bfbe2-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="bfbe2-106">Column</span></span></th>
<th><span data-ttu-id="bfbe2-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="bfbe2-107">Data Type</span></span></th>
<th><span data-ttu-id="bfbe2-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="bfbe2-108">Key/Index</span></span></th>
<th><span data-ttu-id="bfbe2-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bfbe2-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfbe2-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="bfbe2-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="bfbe2-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="bfbe2-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="bfbe2-112">Principale</span><span class="sxs-lookup"><span data-stu-id="bfbe2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="bfbe2-113">Indicatore di data e ora, interno usato.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfbe2-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="bfbe2-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="bfbe2-115">int</span><span class="sxs-lookup"><span data-stu-id="bfbe2-115">int</span></span></p></td>
<td><p><span data-ttu-id="bfbe2-116">Principale</span><span class="sxs-lookup"><span data-stu-id="bfbe2-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="bfbe2-117">Numero univoco che identifica questo URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfbe2-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="bfbe2-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="bfbe2-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="bfbe2-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bfbe2-120">URI conferenza.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfbe2-121"><strong>Checksum</strong></span><span class="sxs-lookup"><span data-stu-id="bfbe2-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="bfbe2-122">int</span><span class="sxs-lookup"><span data-stu-id="bfbe2-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bfbe2-123">Checksum di ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="bfbe2-124">Usato per aumentare la velocità delle ricerche nel database.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfbe2-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="bfbe2-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="bfbe2-126">int</span><span class="sxs-lookup"><span data-stu-id="bfbe2-126">int</span></span></p></td>
<td><p><span data-ttu-id="bfbe2-127">Esterna</span><span class="sxs-lookup"><span data-stu-id="bfbe2-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bfbe2-128">Tipo di URI, ad esempio conf: chat per la conferenza di messaggistica istantanea o conf: audio-video per conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="bfbe2-129">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes nella tabella Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfbe2-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

