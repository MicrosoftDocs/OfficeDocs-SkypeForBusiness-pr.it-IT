---
title: 'Lync Server 2013: Tabella Subnet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20318d0ed2f487efccda81936b113044f75e2618
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="4ffc0-102">Tabella Subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ffc0-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ffc0-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4ffc0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4ffc0-104">La tabella subnet è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="4ffc0-104">The Subnet table is a supporting table.</span></span> <span data-ttu-id="4ffc0-105">Ogni record rappresenta una subnet definita nell'impostazione di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="4ffc0-105">Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ffc0-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="4ffc0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4ffc0-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="4ffc0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4ffc0-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="4ffc0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4ffc0-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="4ffc0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ffc0-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="4ffc0-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffc0-111">int</span><span class="sxs-lookup"><span data-stu-id="4ffc0-111">int</span></span></p></td>
<td><p><span data-ttu-id="4ffc0-112">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="4ffc0-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffc0-113">Rappresentazione Integer per l'IP della subnet.</span><span class="sxs-lookup"><span data-stu-id="4ffc0-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffc0-114"><strong>SubnetMask</strong></span><span class="sxs-lookup"><span data-stu-id="4ffc0-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffc0-115">int</span><span class="sxs-lookup"><span data-stu-id="4ffc0-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ffc0-116">Subnet mask.</span><span class="sxs-lookup"><span data-stu-id="4ffc0-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ffc0-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="4ffc0-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffc0-118">int</span><span class="sxs-lookup"><span data-stu-id="4ffc0-118">int</span></span></p></td>
<td><p><span data-ttu-id="4ffc0-119">Esterna</span><span class="sxs-lookup"><span data-stu-id="4ffc0-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ffc0-120">A cui si fa riferimento dalla <a href="lync-server-2013-usersite-table.md">tabella UserSite in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4ffc0-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ffc0-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="4ffc0-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="4ffc0-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="4ffc0-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ffc0-123">Descrizione della subnet.</span><span class="sxs-lookup"><span data-stu-id="4ffc0-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

