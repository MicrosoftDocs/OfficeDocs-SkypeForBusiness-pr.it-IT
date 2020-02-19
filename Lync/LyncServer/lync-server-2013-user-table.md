---
title: 'Lync Server 2013: tabella utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9ccf7fad4b7b84746c70384269c2a903b840b6f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="b78df-102">Tabella user in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b78df-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b78df-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b78df-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b78df-p101">La tabella User è una tabella di supporto in cui è archiviato un elenco dei diversi utenti che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta un utente.</span><span class="sxs-lookup"><span data-stu-id="b78df-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b78df-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="b78df-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b78df-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="b78df-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b78df-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="b78df-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b78df-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="b78df-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b78df-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="b78df-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b78df-111">int</span><span class="sxs-lookup"><span data-stu-id="b78df-111">int</span></span></p></td>
<td><p><span data-ttu-id="b78df-112">Principale</span><span class="sxs-lookup"><span data-stu-id="b78df-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b78df-113">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="b78df-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b78df-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="b78df-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="b78df-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b78df-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b78df-116">Univoco</span><span class="sxs-lookup"><span data-stu-id="b78df-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="b78df-117">Stringa URI.</span><span class="sxs-lookup"><span data-stu-id="b78df-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b78df-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="b78df-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="b78df-119">int</span><span class="sxs-lookup"><span data-stu-id="b78df-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b78df-120">1 è un tipo di URI sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b78df-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="b78df-121">2 è un URI utente.</span><span class="sxs-lookup"><span data-stu-id="b78df-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="b78df-122">4 è un URI conferenza.</span><span class="sxs-lookup"><span data-stu-id="b78df-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="b78df-123">8 è un URI telefono.</span><span class="sxs-lookup"><span data-stu-id="b78df-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b78df-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="b78df-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b78df-125">int</span><span class="sxs-lookup"><span data-stu-id="b78df-125">int</span></span></p></td>
<td><p><span data-ttu-id="b78df-126">Stranieri</span><span class="sxs-lookup"><span data-stu-id="b78df-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b78df-127">Tenant dell'utente, cui viene fatto riferimento dalla tabella Tenant.</span><span class="sxs-lookup"><span data-stu-id="b78df-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b78df-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="b78df-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b78df-129">datetime</span><span class="sxs-lookup"><span data-stu-id="b78df-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b78df-130">Ultimo indicatore di data e ora in cui si è verificata una chiamata audio di qualità scadente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="b78df-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b78df-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="b78df-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="b78df-132">datetime</span><span class="sxs-lookup"><span data-stu-id="b78df-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b78df-133">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="b78df-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

