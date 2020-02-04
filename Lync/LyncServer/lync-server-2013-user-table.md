---
title: 'Lync Server 2013: Tabella User'
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
ms.openlocfilehash: 8256dec91c93ca6e8f0fd3cfff65280a417324e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="f2bc3-102">Tabella User in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2bc3-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2bc3-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f2bc3-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f2bc3-104">La tabella utente è una tabella di supporto in cui è archiviato un elenco dei vari utenti che hanno partecipato a sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="f2bc3-104">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="f2bc3-105">Ogni record nella tabella rappresenta un solo utente.</span><span class="sxs-lookup"><span data-stu-id="f2bc3-105">Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2bc3-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="f2bc3-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f2bc3-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="f2bc3-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f2bc3-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="f2bc3-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f2bc3-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="f2bc3-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2bc3-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="f2bc3-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f2bc3-111">int</span><span class="sxs-lookup"><span data-stu-id="f2bc3-111">int</span></span></p></td>
<td><p><span data-ttu-id="f2bc3-112">Principale</span><span class="sxs-lookup"><span data-stu-id="f2bc3-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f2bc3-113">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="f2bc3-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2bc3-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="f2bc3-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="f2bc3-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f2bc3-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f2bc3-116">Univoci</span><span class="sxs-lookup"><span data-stu-id="f2bc3-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="f2bc3-117">Stringa URI.</span><span class="sxs-lookup"><span data-stu-id="f2bc3-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2bc3-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="f2bc3-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="f2bc3-119">int</span><span class="sxs-lookup"><span data-stu-id="f2bc3-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2bc3-120">1 è un tipo URI sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f2bc3-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="f2bc3-121">2 è l'URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f2bc3-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="f2bc3-122">4 è l'URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="f2bc3-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="f2bc3-123">8 è l'URI del telefono.</span><span class="sxs-lookup"><span data-stu-id="f2bc3-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2bc3-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="f2bc3-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f2bc3-125">int</span><span class="sxs-lookup"><span data-stu-id="f2bc3-125">int</span></span></p></td>
<td><p><span data-ttu-id="f2bc3-126">Esterna</span><span class="sxs-lookup"><span data-stu-id="f2bc3-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2bc3-127">Tenant dell'utente, a cui si fa riferimento dalla tabella tenant.</span><span class="sxs-lookup"><span data-stu-id="f2bc3-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2bc3-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="f2bc3-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f2bc3-129">DateTime</span><span class="sxs-lookup"><span data-stu-id="f2bc3-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2bc3-130">Indicatore di data e ora più recente quando l'utente ha ricevuto una chiamata audio scadente.</span><span class="sxs-lookup"><span data-stu-id="f2bc3-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2bc3-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="f2bc3-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f2bc3-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="f2bc3-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2bc3-133">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f2bc3-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

