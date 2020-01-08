---
title: 'Lync Server 2013: Tabella Mcus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf0a34d24bf60770f2b1e2664a89993f5917d854
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="c20ad-102">Tabella Mcus in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c20ad-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c20ad-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c20ad-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c20ad-104">La tabella MCU è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="c20ad-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="c20ad-105">Ogni record archivia le informazioni su un servizio di conferenza.</span><span class="sxs-lookup"><span data-stu-id="c20ad-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="c20ad-106">Questi possono includere il servizio di conferenza di messaggistica istantanea e il servizio di conferenza telefonica (che vengono eseguiti come processi nei server front-end) e il servizio di Web Conferencing e il servizio di conferenza telefonica A/V.</span><span class="sxs-lookup"><span data-stu-id="c20ad-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c20ad-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="c20ad-107">Column</span></span></th>
<th><span data-ttu-id="c20ad-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c20ad-108">Data Type</span></span></th>
<th><span data-ttu-id="c20ad-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="c20ad-109">Key/Index</span></span></th>
<th><span data-ttu-id="c20ad-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c20ad-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c20ad-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="c20ad-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="c20ad-112">int</span><span class="sxs-lookup"><span data-stu-id="c20ad-112">int</span></span></p></td>
<td><p><span data-ttu-id="c20ad-113">Principale</span><span class="sxs-lookup"><span data-stu-id="c20ad-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c20ad-114">Numero univoco che identifica questo server di conferenza.</span><span class="sxs-lookup"><span data-stu-id="c20ad-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c20ad-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="c20ad-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c20ad-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c20ad-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c20ad-117"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="c20ad-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="c20ad-118">inyint</span><span class="sxs-lookup"><span data-stu-id="c20ad-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="c20ad-119"> Esterna</span><span class="sxs-lookup"><span data-stu-id="c20ad-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="c20ad-120">Tipo di server di conferenza, ad esempio conf: chat (per IMs) o conf: audio-video.</span><span class="sxs-lookup"><span data-stu-id="c20ad-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="c20ad-121">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c20ad-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

