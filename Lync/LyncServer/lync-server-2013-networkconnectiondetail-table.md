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
ms.openlocfilehash: 58935c4043246a0c5a6c5d4d9cde19ca27627dcc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="ad508-102">Tabella NetworkConnectionDetail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad508-102">NetworkConnectionDetail table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad508-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ad508-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ad508-104">Nella tabella NetworkConnectionDetail i tipi di connessione di rete sono mappati agli identificatori di connessione di rete utilizzati in altre posizioni nel database della qualità percepita dagli utenti (QoE).</span><span class="sxs-lookup"><span data-stu-id="ad508-104">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="ad508-105">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad508-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad508-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="ad508-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ad508-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="ad508-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ad508-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="ad508-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ad508-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="ad508-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad508-110"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="ad508-110"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ad508-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="ad508-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ad508-112">Principale</span><span class="sxs-lookup"><span data-stu-id="ad508-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ad508-113">Identificatore univoco del tipo di connessione di rete.</span><span class="sxs-lookup"><span data-stu-id="ad508-113">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad508-114"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="ad508-114"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="ad508-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ad508-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ad508-116">Univoco</span><span class="sxs-lookup"><span data-stu-id="ad508-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="ad508-p102">Tipo di connessione di rete che corrisponde a NetworkConnectionDetailKey. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="ad508-p102">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="ad508-119">0 - Cablata</span><span class="sxs-lookup"><span data-stu-id="ad508-119">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="ad508-120">1 - Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ad508-120">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="ad508-121">2 - Ethernet</span><span class="sxs-lookup"><span data-stu-id="ad508-121">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

