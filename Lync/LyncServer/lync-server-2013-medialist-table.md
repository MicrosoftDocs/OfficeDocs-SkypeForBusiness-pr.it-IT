---
title: 'Lync Server 2013: Tabella MediaList'
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
ms.openlocfilehash: b92c8a0a6957eed00cf4e25f60ce2e0ff24d1fd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="80e71-102">Tabella MediaList in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80e71-102">MediaList table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80e71-103">_**Argomento Ultima modifica:** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="80e71-103">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="80e71-104">La tabella degli elementi multimediali è una tabella statica in cui è archiviato l'elenco di vari tipi di elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="80e71-104">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80e71-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="80e71-105">Column</span></span></th>
<th><span data-ttu-id="80e71-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="80e71-106">Data Type</span></span></th>
<th><span data-ttu-id="80e71-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="80e71-107">Key/Index</span></span></th>
<th><span data-ttu-id="80e71-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="80e71-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80e71-109"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="80e71-109"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="80e71-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="80e71-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="80e71-111">Principale</span><span class="sxs-lookup"><span data-stu-id="80e71-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="80e71-112">Valori: 1-7</span><span class="sxs-lookup"><span data-stu-id="80e71-112">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80e71-113"><strong>Contenuti multimediali</strong></span><span class="sxs-lookup"><span data-stu-id="80e71-113"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="80e71-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="80e71-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80e71-115">Mapping statico di valori MediaID e media:</span><span class="sxs-lookup"><span data-stu-id="80e71-115">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="80e71-116">1-MESSAGGISTICA ISTANTANEA</span><span class="sxs-lookup"><span data-stu-id="80e71-116">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="80e71-117">2-trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="80e71-117">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="80e71-118">3-assistenza remota</span><span class="sxs-lookup"><span data-stu-id="80e71-118">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="80e71-119">4-condivisione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="80e71-119">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="80e71-120">5-audio</span><span class="sxs-lookup"><span data-stu-id="80e71-120">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="80e71-121">6-video</span><span class="sxs-lookup"><span data-stu-id="80e71-121">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="80e71-122">7-invito all'app</span><span class="sxs-lookup"><span data-stu-id="80e71-122">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="80e71-123">Se si sta provando a determinare il tipo di modalità per i valori in LcsCDR. SessionDetailsView. MediaTypes, è necessario usare il frammento di join seguente:</span><span class="sxs-lookup"><span data-stu-id="80e71-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

