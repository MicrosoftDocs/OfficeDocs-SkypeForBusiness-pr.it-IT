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
ms.openlocfilehash: fc67c4096cde54252cec432fd8ad2196b05c00e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536943"
---
# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="43911-102">Tabella QRTDDriver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43911-102">DeviceDriver table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43911-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="43911-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="43911-p101">La tabella DeviceDriver è una tabella di supporto. Ogni record rappresenta un driver utilizzato da un dispositivo di acquisizione o di rendering.</span><span class="sxs-lookup"><span data-stu-id="43911-p101">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43911-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="43911-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="43911-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="43911-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="43911-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="43911-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="43911-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="43911-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43911-110"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="43911-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="43911-111">int</span><span class="sxs-lookup"><span data-stu-id="43911-111">int</span></span></p></td>
<td><p><span data-ttu-id="43911-112">Principale</span><span class="sxs-lookup"><span data-stu-id="43911-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="43911-113">Numero univoco che identifica questo record del driver di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="43911-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43911-114"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="43911-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="43911-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="43911-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="43911-116">univoco</span><span class="sxs-lookup"><span data-stu-id="43911-116">unique</span></span></p></td>
<td><p><span data-ttu-id="43911-117">Nome del driver di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="43911-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

