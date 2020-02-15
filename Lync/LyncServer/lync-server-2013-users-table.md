---
title: 'Lync Server 2013: tabella users'
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
ms.openlocfilehash: 67663afbd9e5b61b1b24478e003db91c5be511e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="9d3d3-102">Tabella Users in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d3d3-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d3d3-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9d3d3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9d3d3-104">La tabella Users è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="9d3d3-104">The Users table is a supporting table.</span></span> <span data-ttu-id="9d3d3-105">Ogni record nella tabella archivia le informazioni su un utente coinvolto nelle chiamate o nelle sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="9d3d3-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d3d3-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="9d3d3-106">Column</span></span></th>
<th><span data-ttu-id="9d3d3-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d3d3-107">Data Type</span></span></th>
<th><span data-ttu-id="9d3d3-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="9d3d3-108">Key/Index</span></span></th>
<th><span data-ttu-id="9d3d3-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9d3d3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d3d3-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="9d3d3-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="9d3d3-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9d3d3-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d3d3-112">Indicatore di data e ora per l'utilizzo interno.</span><span class="sxs-lookup"><span data-stu-id="9d3d3-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d3d3-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="9d3d3-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d3d3-114">int</span><span class="sxs-lookup"><span data-stu-id="9d3d3-114">int</span></span></p></td>
<td><p><span data-ttu-id="9d3d3-115">Principale</span><span class="sxs-lookup"><span data-stu-id="9d3d3-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="9d3d3-116">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="9d3d3-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d3d3-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="9d3d3-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9d3d3-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9d3d3-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9d3d3-119">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9d3d3-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d3d3-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="9d3d3-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d3d3-121">int</span><span class="sxs-lookup"><span data-stu-id="9d3d3-121">int</span></span></p></td>
<td><p><span data-ttu-id="9d3d3-122">Stranieri</span><span class="sxs-lookup"><span data-stu-id="9d3d3-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d3d3-123">ID tenant dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9d3d3-123">This user’s Tenant ID.</span></span> <span data-ttu-id="9d3d3-124">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9d3d3-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d3d3-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="9d3d3-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d3d3-126">int</span><span class="sxs-lookup"><span data-stu-id="9d3d3-126">int</span></span></p></td>
<td><p><span data-ttu-id="9d3d3-127">Stranieri</span><span class="sxs-lookup"><span data-stu-id="9d3d3-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9d3d3-128">Tipo di URI di questo utente.</span><span class="sxs-lookup"><span data-stu-id="9d3d3-128">This user’s URI type.</span></span> <span data-ttu-id="9d3d3-129">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9d3d3-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

