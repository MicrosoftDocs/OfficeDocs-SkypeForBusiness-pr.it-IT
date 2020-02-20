---
title: 'Lync Server 2013: tabella QRTDDriver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a4638676371b2de3673fbb7ff805b401ffb00dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="e9a5d-102">Tabella QRTDDriver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9a5d-102">DeviceDriver table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9a5d-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e9a5d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e9a5d-p101">La tabella DeviceDriver è una tabella di supporto. Ogni record rappresenta un driver utilizzato da un dispositivo di acquisizione o di rendering.</span><span class="sxs-lookup"><span data-stu-id="e9a5d-p101">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9a5d-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="e9a5d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e9a5d-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="e9a5d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e9a5d-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="e9a5d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e9a5d-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="e9a5d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9a5d-110"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="e9a5d-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e9a5d-111">int</span><span class="sxs-lookup"><span data-stu-id="e9a5d-111">int</span></span></p></td>
<td><p><span data-ttu-id="e9a5d-112">Principale</span><span class="sxs-lookup"><span data-stu-id="e9a5d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e9a5d-113">Numero univoco che identifica questo record del driver di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9a5d-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9a5d-114"><strong>QRTDDriver</strong></span><span class="sxs-lookup"><span data-stu-id="e9a5d-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="e9a5d-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e9a5d-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e9a5d-116">univoco</span><span class="sxs-lookup"><span data-stu-id="e9a5d-116">unique</span></span></p></td>
<td><p><span data-ttu-id="e9a5d-117">Nome del driver di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9a5d-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

