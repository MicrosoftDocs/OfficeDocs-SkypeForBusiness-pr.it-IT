---
title: 'Lync Server 2013: Tabella Devices'
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
ms.openlocfilehash: 1270557e5d02fd1764957d75441ecc33ad11588c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="66e1b-102">Tabella Devices in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66e1b-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66e1b-103">_**Ultimo argomento modificato:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="66e1b-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="66e1b-p101">La tabella Devices è una tabella di supporto. In ogni record sono archiviate informazioni relative a un dispositivo (telefono da tavolo).</span><span class="sxs-lookup"><span data-stu-id="66e1b-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66e1b-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="66e1b-106">Column</span></span></th>
<th><span data-ttu-id="66e1b-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="66e1b-107">Data Type</span></span></th>
<th><span data-ttu-id="66e1b-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="66e1b-108">Key/Index</span></span></th>
<th><span data-ttu-id="66e1b-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="66e1b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66e1b-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="66e1b-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="66e1b-111">int</span><span class="sxs-lookup"><span data-stu-id="66e1b-111">int</span></span></p></td>
<td><p><span data-ttu-id="66e1b-112">Principale</span><span class="sxs-lookup"><span data-stu-id="66e1b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="66e1b-113">Numero univoco che identifica questa versione hardware.</span><span class="sxs-lookup"><span data-stu-id="66e1b-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e1b-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="66e1b-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="66e1b-115">int</span><span class="sxs-lookup"><span data-stu-id="66e1b-115">int</span></span></p></td>
<td><p><span data-ttu-id="66e1b-116">Stranieri</span><span class="sxs-lookup"><span data-stu-id="66e1b-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66e1b-117">Produttore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66e1b-117">Manufacturer of this device.</span></span> <span data-ttu-id="66e1b-118">Per ulteriori informazioni, vedere la <a href="lync-server-2013-manufacturers-table.md">tabella Manufacturers in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66e1b-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e1b-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="66e1b-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="66e1b-120">int</span><span class="sxs-lookup"><span data-stu-id="66e1b-120">int</span></span></p></td>
<td><p><span data-ttu-id="66e1b-121">Stranieri</span><span class="sxs-lookup"><span data-stu-id="66e1b-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66e1b-122">Versione hardware del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66e1b-122">Hardware version of this device.</span></span> <span data-ttu-id="66e1b-123">Per ulteriori informazioni, vedere la <a href="lync-server-2013-hardwareversions-table.md">tabella HardwareVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66e1b-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e1b-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="66e1b-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="66e1b-125">bigint</span><span class="sxs-lookup"><span data-stu-id="66e1b-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e1b-126">Indirizzo MAC</span><span class="sxs-lookup"><span data-stu-id="66e1b-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

