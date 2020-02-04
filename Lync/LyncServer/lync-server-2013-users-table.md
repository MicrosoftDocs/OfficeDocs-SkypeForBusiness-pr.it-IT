---
title: 'Lync Server 2013: Tabella Users'
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
ms.openlocfilehash: c2be643f8a593af01ee47ad93d3910d44ee86e48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="564bd-102">Tabella Users in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="564bd-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="564bd-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="564bd-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="564bd-104">La tabella utenti è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="564bd-104">The Users table is a supporting table.</span></span> <span data-ttu-id="564bd-105">Ogni record nella tabella archivia le informazioni relative a un utente coinvolto in chiamate o sessioni che includono record nel database.</span><span class="sxs-lookup"><span data-stu-id="564bd-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="564bd-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="564bd-106">Column</span></span></th>
<th><span data-ttu-id="564bd-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="564bd-107">Data Type</span></span></th>
<th><span data-ttu-id="564bd-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="564bd-108">Key/Index</span></span></th>
<th><span data-ttu-id="564bd-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="564bd-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="564bd-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="564bd-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="564bd-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="564bd-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="564bd-112">Indicatore di data e ora per uso interno.</span><span class="sxs-lookup"><span data-stu-id="564bd-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="564bd-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="564bd-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="564bd-114">int</span><span class="sxs-lookup"><span data-stu-id="564bd-114">int</span></span></p></td>
<td><p><span data-ttu-id="564bd-115">Principale</span><span class="sxs-lookup"><span data-stu-id="564bd-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="564bd-116">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="564bd-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="564bd-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="564bd-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="564bd-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="564bd-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="564bd-119">URI utente.</span><span class="sxs-lookup"><span data-stu-id="564bd-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="564bd-120"><strong>ID tenant</strong></span><span class="sxs-lookup"><span data-stu-id="564bd-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="564bd-121">int</span><span class="sxs-lookup"><span data-stu-id="564bd-121">int</span></span></p></td>
<td><p><span data-ttu-id="564bd-122">Esterna</span><span class="sxs-lookup"><span data-stu-id="564bd-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="564bd-123">ID tenant di questo utente.</span><span class="sxs-lookup"><span data-stu-id="564bd-123">This user’s Tenant ID.</span></span> <span data-ttu-id="564bd-124">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="564bd-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="564bd-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="564bd-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="564bd-126">int</span><span class="sxs-lookup"><span data-stu-id="564bd-126">int</span></span></p></td>
<td><p><span data-ttu-id="564bd-127">Esterna</span><span class="sxs-lookup"><span data-stu-id="564bd-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="564bd-128">Tipo di URI di questo utente.</span><span class="sxs-lookup"><span data-stu-id="564bd-128">This user’s URI type.</span></span> <span data-ttu-id="564bd-129">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="564bd-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

