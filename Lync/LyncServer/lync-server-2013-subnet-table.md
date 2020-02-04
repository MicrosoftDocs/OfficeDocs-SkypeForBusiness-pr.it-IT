---
title: 'Lync Server 2013: Tabella Subnet'
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
ms.openlocfilehash: d107889b49ec16c51224b075a8fb7f7a7cec1b00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="5b708-102">Tabella Subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b708-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b708-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5b708-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5b708-104">La tabella subnet è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="5b708-104">The Subnet table is a supporting table.</span></span> <span data-ttu-id="5b708-105">Ogni record rappresenta una subnet definita nell'impostazione di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="5b708-105">Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b708-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="5b708-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5b708-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="5b708-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5b708-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="5b708-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5b708-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="5b708-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b708-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="5b708-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="5b708-111">int</span><span class="sxs-lookup"><span data-stu-id="5b708-111">int</span></span></p></td>
<td><p><span data-ttu-id="5b708-112">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="5b708-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b708-113">Rappresentazione Integer per l'IP della subnet.</span><span class="sxs-lookup"><span data-stu-id="5b708-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b708-114"><strong>SubnetMask</strong></span><span class="sxs-lookup"><span data-stu-id="5b708-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="5b708-115">int</span><span class="sxs-lookup"><span data-stu-id="5b708-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b708-116">Subnet mask.</span><span class="sxs-lookup"><span data-stu-id="5b708-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b708-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="5b708-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="5b708-118">int</span><span class="sxs-lookup"><span data-stu-id="5b708-118">int</span></span></p></td>
<td><p><span data-ttu-id="5b708-119">Esterna</span><span class="sxs-lookup"><span data-stu-id="5b708-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5b708-120">A cui si fa riferimento dalla <a href="lync-server-2013-usersite-table.md">tabella UserSite in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5b708-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b708-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="5b708-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="5b708-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="5b708-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b708-123">Descrizione della subnet.</span><span class="sxs-lookup"><span data-stu-id="5b708-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

