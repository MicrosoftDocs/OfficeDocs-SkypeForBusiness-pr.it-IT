---
title: 'Lync Server 2013: Tabella Devices'
description: 'Lync Server 2013: Tabella Devices.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 763e1788e2874f9f9831c089ffe8fa077621b030
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576242"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="65946-103">Tabella Devices in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65946-103">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65946-104">_**Ultimo argomento modificato:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="65946-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="65946-p101">La tabella Devices è una tabella di supporto. In ogni record sono archiviate informazioni relative a un dispositivo (telefono da tavolo).</span><span class="sxs-lookup"><span data-stu-id="65946-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65946-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="65946-107">Column</span></span></th>
<th><span data-ttu-id="65946-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="65946-108">Data Type</span></span></th>
<th><span data-ttu-id="65946-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="65946-109">Key/Index</span></span></th>
<th><span data-ttu-id="65946-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="65946-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65946-111"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="65946-111"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="65946-112">int</span><span class="sxs-lookup"><span data-stu-id="65946-112">int</span></span></p></td>
<td><p><span data-ttu-id="65946-113">Principale</span><span class="sxs-lookup"><span data-stu-id="65946-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="65946-114">Numero univoco che identifica questa versione hardware.</span><span class="sxs-lookup"><span data-stu-id="65946-114">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65946-115"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="65946-115"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="65946-116">int</span><span class="sxs-lookup"><span data-stu-id="65946-116">int</span></span></p></td>
<td><p><span data-ttu-id="65946-117">Stranieri</span><span class="sxs-lookup"><span data-stu-id="65946-117">Foreign</span></span></p></td>
<td><p><span data-ttu-id="65946-118">Produttore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="65946-118">Manufacturer of this device.</span></span> <span data-ttu-id="65946-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-manufacturers-table.md">tabella Manufacturers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="65946-119">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65946-120"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="65946-120"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="65946-121">int</span><span class="sxs-lookup"><span data-stu-id="65946-121">int</span></span></p></td>
<td><p><span data-ttu-id="65946-122">Stranieri</span><span class="sxs-lookup"><span data-stu-id="65946-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="65946-123">Versione hardware del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="65946-123">Hardware version of this device.</span></span> <span data-ttu-id="65946-124">Per ulteriori informazioni, vedere la <a href="lync-server-2013-hardwareversions-table.md">tabella HardwareVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="65946-124">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65946-125"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="65946-125"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="65946-126">bigint</span><span class="sxs-lookup"><span data-stu-id="65946-126">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="65946-127">Indirizzo MAC</span><span class="sxs-lookup"><span data-stu-id="65946-127">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

