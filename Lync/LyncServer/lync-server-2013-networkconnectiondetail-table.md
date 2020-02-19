---
title: 'Lync Server 2013: tabella NetworkConnectionDetail'
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
ms.openlocfilehash: bb192385cfd5d04712b0e66169326aedd6c0f1b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42128329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="d9c1b-102">Tabella NetworkConnectionDetail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9c1b-102">NetworkConnectionDetail table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9c1b-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d9c1b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d9c1b-104">Nella tabella NetworkConnectionDetail i tipi di connessione di rete sono mappati agli identificatori di connessione di rete utilizzati in altre posizioni nel database della qualità percepita dagli utenti (QoE).</span><span class="sxs-lookup"><span data-stu-id="d9c1b-104">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="d9c1b-105">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9c1b-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9c1b-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="d9c1b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d9c1b-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="d9c1b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d9c1b-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="d9c1b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d9c1b-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="d9c1b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9c1b-110"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="d9c1b-110"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d9c1b-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="d9c1b-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d9c1b-112">Principale</span><span class="sxs-lookup"><span data-stu-id="d9c1b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d9c1b-113">Identificatore univoco del tipo di connessione di rete.</span><span class="sxs-lookup"><span data-stu-id="d9c1b-113">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9c1b-114"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="d9c1b-114"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="d9c1b-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9c1b-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9c1b-116">Univoco</span><span class="sxs-lookup"><span data-stu-id="d9c1b-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="d9c1b-p102">Tipo di connessione di rete che corrisponde a NetworkConnectionDetailKey. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="d9c1b-p102">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="d9c1b-119">0 - Cablata</span><span class="sxs-lookup"><span data-stu-id="d9c1b-119">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="d9c1b-120">1 - Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d9c1b-120">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="d9c1b-121">2 - Ethernet</span><span class="sxs-lookup"><span data-stu-id="d9c1b-121">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

