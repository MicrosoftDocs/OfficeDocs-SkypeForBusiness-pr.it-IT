---
title: 'Lync Server 2013: tabella NetworkConnectionDetail'
description: 'Lync Server 2013: tabella NetworkConnectionDetail.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd0f429999b6629826a9f9369d154afe3c1af2f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561402"
---
# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="4b18a-103">Tabella NetworkConnectionDetail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b18a-103">NetworkConnectionDetail table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b18a-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4b18a-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4b18a-105">Nella tabella NetworkConnectionDetail i tipi di connessione di rete sono mappati agli identificatori di connessione di rete utilizzati in altre posizioni nel database della qualità percepita dagli utenti (QoE).</span><span class="sxs-lookup"><span data-stu-id="4b18a-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="4b18a-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b18a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b18a-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="4b18a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4b18a-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="4b18a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4b18a-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="4b18a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4b18a-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="4b18a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b18a-111"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="4b18a-111"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4b18a-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="4b18a-112">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4b18a-113">Principale</span><span class="sxs-lookup"><span data-stu-id="4b18a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="4b18a-114">Identificatore univoco del tipo di connessione di rete.</span><span class="sxs-lookup"><span data-stu-id="4b18a-114">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b18a-115"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="4b18a-115"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="4b18a-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b18a-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b18a-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="4b18a-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="4b18a-p102">Tipo di connessione di rete che corrisponde a NetworkConnectionDetailKey. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="4b18a-p102">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="4b18a-120">0 - Cablata</span><span class="sxs-lookup"><span data-stu-id="4b18a-120">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="4b18a-121">1 - Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="4b18a-121">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="4b18a-122">2 - Ethernet</span><span class="sxs-lookup"><span data-stu-id="4b18a-122">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

