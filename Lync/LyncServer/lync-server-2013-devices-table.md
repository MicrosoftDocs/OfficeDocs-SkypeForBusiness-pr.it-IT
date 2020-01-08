---
title: 'Lync Server 2013: Tabella Devices'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f78e0b4ba3bb5271a2de43e423dfa4b3baf17cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="48e8a-102">Tabella Devices in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48e8a-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48e8a-103">_**Argomento Ultima modifica:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="48e8a-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="48e8a-104">La tabella dispositivi è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="48e8a-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="48e8a-105">Ogni record archivia le informazioni su un dispositivo (telefono da tavolo).</span><span class="sxs-lookup"><span data-stu-id="48e8a-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48e8a-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="48e8a-106">Column</span></span></th>
<th><span data-ttu-id="48e8a-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="48e8a-107">Data Type</span></span></th>
<th><span data-ttu-id="48e8a-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="48e8a-108">Key/Index</span></span></th>
<th><span data-ttu-id="48e8a-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="48e8a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48e8a-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="48e8a-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="48e8a-111">int</span><span class="sxs-lookup"><span data-stu-id="48e8a-111">int</span></span></p></td>
<td><p><span data-ttu-id="48e8a-112">Principale</span><span class="sxs-lookup"><span data-stu-id="48e8a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="48e8a-113">Numero univoco che identifica questa versione hardware.</span><span class="sxs-lookup"><span data-stu-id="48e8a-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48e8a-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="48e8a-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="48e8a-115">int</span><span class="sxs-lookup"><span data-stu-id="48e8a-115">int</span></span></p></td>
<td><p><span data-ttu-id="48e8a-116">Esterna</span><span class="sxs-lookup"><span data-stu-id="48e8a-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="48e8a-117">Fabbricante di questo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="48e8a-117">Manufacturer of this device.</span></span> <span data-ttu-id="48e8a-118">Per altre informazioni, vedere la <a href="lync-server-2013-manufacturers-table.md">tabella produttori in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="48e8a-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48e8a-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="48e8a-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="48e8a-120">int</span><span class="sxs-lookup"><span data-stu-id="48e8a-120">int</span></span></p></td>
<td><p><span data-ttu-id="48e8a-121">Esterna</span><span class="sxs-lookup"><span data-stu-id="48e8a-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="48e8a-122">Versione hardware di questo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="48e8a-122">Hardware version of this device.</span></span> <span data-ttu-id="48e8a-123">Per altre informazioni, vedere la <a href="lync-server-2013-hardwareversions-table.md">tabella HardwareVersions in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="48e8a-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48e8a-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="48e8a-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="48e8a-125">bigint</span><span class="sxs-lookup"><span data-stu-id="48e8a-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48e8a-126">Indirizzo MAC</span><span class="sxs-lookup"><span data-stu-id="48e8a-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

