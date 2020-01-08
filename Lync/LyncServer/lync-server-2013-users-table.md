---
title: 'Lync Server 2013: Tabella Users'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6acc63c2271b5ab58e168d0f0f662c6cb3653aac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="76a78-102">Tabella Users in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76a78-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76a78-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="76a78-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="76a78-104">La tabella utenti è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="76a78-104">The Users table is a supporting table.</span></span> <span data-ttu-id="76a78-105">Ogni record nella tabella archivia le informazioni relative a un utente coinvolto in chiamate o sessioni che includono record nel database.</span><span class="sxs-lookup"><span data-stu-id="76a78-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76a78-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="76a78-106">Column</span></span></th>
<th><span data-ttu-id="76a78-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="76a78-107">Data Type</span></span></th>
<th><span data-ttu-id="76a78-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="76a78-108">Key/Index</span></span></th>
<th><span data-ttu-id="76a78-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="76a78-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76a78-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="76a78-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="76a78-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="76a78-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a78-112">Indicatore di data e ora per uso interno.</span><span class="sxs-lookup"><span data-stu-id="76a78-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76a78-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="76a78-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="76a78-114">int</span><span class="sxs-lookup"><span data-stu-id="76a78-114">int</span></span></p></td>
<td><p><span data-ttu-id="76a78-115">Principale</span><span class="sxs-lookup"><span data-stu-id="76a78-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="76a78-116">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="76a78-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76a78-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="76a78-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="76a78-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="76a78-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="76a78-119">URI utente.</span><span class="sxs-lookup"><span data-stu-id="76a78-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76a78-120"><strong>ID tenant</strong></span><span class="sxs-lookup"><span data-stu-id="76a78-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="76a78-121">int</span><span class="sxs-lookup"><span data-stu-id="76a78-121">int</span></span></p></td>
<td><p><span data-ttu-id="76a78-122">Esterna</span><span class="sxs-lookup"><span data-stu-id="76a78-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="76a78-123">ID tenant di questo utente.</span><span class="sxs-lookup"><span data-stu-id="76a78-123">This user’s Tenant ID.</span></span> <span data-ttu-id="76a78-124">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="76a78-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76a78-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="76a78-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="76a78-126">int</span><span class="sxs-lookup"><span data-stu-id="76a78-126">int</span></span></p></td>
<td><p><span data-ttu-id="76a78-127">Esterna</span><span class="sxs-lookup"><span data-stu-id="76a78-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="76a78-128">Tipo di URI di questo utente.</span><span class="sxs-lookup"><span data-stu-id="76a78-128">This user’s URI type.</span></span> <span data-ttu-id="76a78-129">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="76a78-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

