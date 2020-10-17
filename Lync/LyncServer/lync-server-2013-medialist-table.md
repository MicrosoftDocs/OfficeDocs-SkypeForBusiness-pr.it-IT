---
title: 'Lync Server 2013: tabella multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a22ef9b9e0ef429fcac96a7f7d5c87093f79a02
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505723"
---
# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="a683f-102">Tabella media in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a683f-102">MediaList table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a683f-103">_**Ultimo argomento modificato:** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="a683f-103">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="a683f-104">La tabella MediaList è una tabella statica in cui è archiviato l'elenco di diversi tipi di elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="a683f-104">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a683f-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="a683f-105">Column</span></span></th>
<th><span data-ttu-id="a683f-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a683f-106">Data Type</span></span></th>
<th><span data-ttu-id="a683f-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="a683f-107">Key/Index</span></span></th>
<th><span data-ttu-id="a683f-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a683f-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a683f-109"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="a683f-109"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="a683f-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="a683f-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a683f-111">Principale</span><span class="sxs-lookup"><span data-stu-id="a683f-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="a683f-112">Valori: 1-7</span><span class="sxs-lookup"><span data-stu-id="a683f-112">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a683f-113"><strong>Contenuti multimediali</strong></span><span class="sxs-lookup"><span data-stu-id="a683f-113"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="a683f-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a683f-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a683f-115">Mapping statico dei valori di MediaID e media:</span><span class="sxs-lookup"><span data-stu-id="a683f-115">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="a683f-116">1-MESSAGGISTICA ISTANTANEA</span><span class="sxs-lookup"><span data-stu-id="a683f-116">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="a683f-117">2 -- Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="a683f-117">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="a683f-118">3 -- Assistenza remota</span><span class="sxs-lookup"><span data-stu-id="a683f-118">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="a683f-119">4 -- Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="a683f-119">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="a683f-120">5 – audio</span><span class="sxs-lookup"><span data-stu-id="a683f-120">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="a683f-121">6 – video</span><span class="sxs-lookup"><span data-stu-id="a683f-121">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="a683f-122">7 -- Invito applicazione</span><span class="sxs-lookup"><span data-stu-id="a683f-122">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a683f-123">Se si sta tentando di determinare il tipo di modalità per i valori in LcsCDR. SessionDetailsView. MediaTypes, è necessario utilizzare il seguente frammento di join:</span><span class="sxs-lookup"><span data-stu-id="a683f-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

