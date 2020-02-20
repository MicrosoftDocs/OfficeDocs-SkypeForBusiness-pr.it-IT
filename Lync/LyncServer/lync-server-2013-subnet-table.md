---
title: 'Lync Server 2013: tabella subnet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cdf1ded3a63d790db78476b91a458d07921200a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="04e1b-102">Tabella subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e1b-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04e1b-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="04e1b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="04e1b-p101">La tabella Subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="04e1b-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04e1b-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="04e1b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="04e1b-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="04e1b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="04e1b-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="04e1b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="04e1b-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="04e1b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04e1b-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="04e1b-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="04e1b-111">int</span><span class="sxs-lookup"><span data-stu-id="04e1b-111">int</span></span></p></td>
<td><p><span data-ttu-id="04e1b-112">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="04e1b-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="04e1b-113">Rappresentazione in forma di numero intero dell'IP della subnet.</span><span class="sxs-lookup"><span data-stu-id="04e1b-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04e1b-114"><strong>SubnetMask</strong></span><span class="sxs-lookup"><span data-stu-id="04e1b-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="04e1b-115">int</span><span class="sxs-lookup"><span data-stu-id="04e1b-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04e1b-116">Subnet mask.</span><span class="sxs-lookup"><span data-stu-id="04e1b-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04e1b-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="04e1b-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="04e1b-118">int</span><span class="sxs-lookup"><span data-stu-id="04e1b-118">int</span></span></p></td>
<td><p><span data-ttu-id="04e1b-119">Stranieri</span><span class="sxs-lookup"><span data-stu-id="04e1b-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="04e1b-120">A cui viene fatto riferimento dalla <a href="lync-server-2013-usersite-table.md">tabella UserSite in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="04e1b-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04e1b-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="04e1b-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="04e1b-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="04e1b-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04e1b-123">Descrizione della subnet.</span><span class="sxs-lookup"><span data-stu-id="04e1b-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

