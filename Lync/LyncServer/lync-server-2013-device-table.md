---
title: 'Lync Server 2013: Tabella Device'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fd06db1bd429526826962d5c3ad098642a3a42d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="eeee1-102">Tabella Device in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eeee1-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eeee1-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="eeee1-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="eeee1-104">La tabella Device è una tabella di supporto in cui vengono archiviate le informazioni sui vari dispositivi di acquisizione o rendering.</span><span class="sxs-lookup"><span data-stu-id="eeee1-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="eeee1-105">Ogni record nella tabella rappresenta un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eeee1-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eeee1-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="eeee1-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="eeee1-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="eeee1-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="eeee1-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="eeee1-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="eeee1-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="eeee1-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eeee1-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="eeee1-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="eeee1-111">int</span><span class="sxs-lookup"><span data-stu-id="eeee1-111">int</span></span></p></td>
<td><p><span data-ttu-id="eeee1-112">Principale</span><span class="sxs-lookup"><span data-stu-id="eeee1-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="eeee1-113">Numero univoco che identifica questo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eeee1-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eeee1-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="eeee1-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="eeee1-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="eeee1-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="eeee1-116">DeviceName + DeviceType è univoco</span><span class="sxs-lookup"><span data-stu-id="eeee1-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="eeee1-117">Nome dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eeee1-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eeee1-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="eeee1-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="eeee1-119">po'</span><span class="sxs-lookup"><span data-stu-id="eeee1-119">bit</span></span></p></td>
<td><p><span data-ttu-id="eeee1-120">DeviceName + DeviceType è univoco</span><span class="sxs-lookup"><span data-stu-id="eeee1-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="eeee1-121">Tipo di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eeee1-121">Device type.</span></span> <span data-ttu-id="eeee1-122">1 è un dispositivo di acquisizione, 0 è un dispositivo di rendering.</span><span class="sxs-lookup"><span data-stu-id="eeee1-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

