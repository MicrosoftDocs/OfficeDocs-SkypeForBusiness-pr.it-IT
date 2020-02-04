---
title: 'Lync Server 2013: Tabella UserSite'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e316fe33ac77784a681a71b9cabd0613bb1cc1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="5ec61-102">Tabella UserSite in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ec61-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ec61-103">_**Argomento Ultima modifica:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="5ec61-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="5ec61-104">La tabella UserSite è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="5ec61-104">The UserSite table is a supporting table.</span></span> <span data-ttu-id="5ec61-105">Ogni record rappresenta un sito utente definito in impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="5ec61-105">Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ec61-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="5ec61-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5ec61-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="5ec61-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5ec61-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="5ec61-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5ec61-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="5ec61-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ec61-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="5ec61-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="5ec61-111">int</span><span class="sxs-lookup"><span data-stu-id="5ec61-111">int</span></span></p></td>
<td><p><span data-ttu-id="5ec61-112">Principale</span><span class="sxs-lookup"><span data-stu-id="5ec61-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ec61-113">Numero univoco che identifica il sito utente.</span><span class="sxs-lookup"><span data-stu-id="5ec61-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ec61-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="5ec61-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="5ec61-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="5ec61-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5ec61-116">Univoci</span><span class="sxs-lookup"><span data-stu-id="5ec61-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="5ec61-117">Nome del sito utente.</span><span class="sxs-lookup"><span data-stu-id="5ec61-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ec61-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="5ec61-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="5ec61-119">int</span><span class="sxs-lookup"><span data-stu-id="5ec61-119">int</span></span></p></td>
<td><p><span data-ttu-id="5ec61-120">Esterna</span><span class="sxs-lookup"><span data-stu-id="5ec61-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ec61-121">A cui si fa riferimento dalla <a href="lync-server-2013-region-table.md">tabella Region in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5ec61-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

