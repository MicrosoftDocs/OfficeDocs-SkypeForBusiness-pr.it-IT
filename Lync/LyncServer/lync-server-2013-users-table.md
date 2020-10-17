---
title: 'Lync Server 2013: tabella users'
description: 'Lync Server 2013: tabella users.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b1418e162a04e46ee0dfeca082aa66b0665fc77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548632"
---
# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="ce20d-103">Tabella Users in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce20d-103">Users table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce20d-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ce20d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ce20d-105">La tabella Users è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="ce20d-105">The Users table is a supporting table.</span></span> <span data-ttu-id="ce20d-106">Ogni record nella tabella archivia le informazioni su un utente coinvolto nelle chiamate o nelle sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="ce20d-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce20d-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="ce20d-107">Column</span></span></th>
<th><span data-ttu-id="ce20d-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ce20d-108">Data Type</span></span></th>
<th><span data-ttu-id="ce20d-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="ce20d-109">Key/Index</span></span></th>
<th><span data-ttu-id="ce20d-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ce20d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce20d-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="ce20d-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ce20d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ce20d-112">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ce20d-113">Indicatore di data e ora per l'utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="ce20d-113">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce20d-114"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="ce20d-114"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ce20d-115">int</span><span class="sxs-lookup"><span data-stu-id="ce20d-115">int</span></span></p></td>
<td><p><span data-ttu-id="ce20d-116">Principale</span><span class="sxs-lookup"><span data-stu-id="ce20d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="ce20d-117">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="ce20d-117">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce20d-118"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="ce20d-118"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ce20d-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ce20d-119">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce20d-120">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ce20d-120">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce20d-121"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="ce20d-121"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="ce20d-122">int</span><span class="sxs-lookup"><span data-stu-id="ce20d-122">int</span></span></p></td>
<td><p><span data-ttu-id="ce20d-123">Stranieri</span><span class="sxs-lookup"><span data-stu-id="ce20d-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ce20d-124">ID tenant dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ce20d-124">This user’s Tenant ID.</span></span> <span data-ttu-id="ce20d-125">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce20d-125">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce20d-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ce20d-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ce20d-127">int</span><span class="sxs-lookup"><span data-stu-id="ce20d-127">int</span></span></p></td>
<td><p><span data-ttu-id="ce20d-128">Stranieri</span><span class="sxs-lookup"><span data-stu-id="ce20d-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ce20d-129">Tipo di URI di questo utente.</span><span class="sxs-lookup"><span data-stu-id="ce20d-129">This user’s URI type.</span></span> <span data-ttu-id="ce20d-130">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ce20d-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

