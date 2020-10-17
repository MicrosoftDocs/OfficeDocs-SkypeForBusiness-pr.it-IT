---
title: 'Lync Server 2013: tabella ConferenceMessageCount'
description: 'Lync Server 2013: tabella ConferenceMessageCount.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 271b654c09ab1aef194eb613e660de208aea1534
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561622"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="a1482-103">Tabella ConferenceMessageCount in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1482-103">ConferenceMessageCount table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1482-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a1482-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a1482-105">Ogni record di questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a1482-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="a1482-106">Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="a1482-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1482-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="a1482-107">Column</span></span></th>
<th><span data-ttu-id="a1482-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a1482-108">Data Type</span></span></th>
<th><span data-ttu-id="a1482-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="a1482-109">Key/Index</span></span></th>
<th><span data-ttu-id="a1482-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a1482-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1482-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a1482-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a1482-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a1482-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="a1482-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="a1482-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a1482-114">Data e ora dell'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a1482-114">Time of conference instance.</span></span> <span data-ttu-id="a1482-115">Utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a1482-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="a1482-116">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a1482-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1482-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a1482-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a1482-118">int</span><span class="sxs-lookup"><span data-stu-id="a1482-118">int</span></span></p></td>
<td><p><span data-ttu-id="a1482-119">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="a1482-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a1482-120">Numero ID per identificare l'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a1482-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="a1482-121">Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="a1482-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="a1482-122">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferences-table.md">tabella conferenze in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a1482-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1482-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a1482-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a1482-124">int</span><span class="sxs-lookup"><span data-stu-id="a1482-124">int</span></span></p></td>
<td><p><span data-ttu-id="a1482-125">Stranieri</span><span class="sxs-lookup"><span data-stu-id="a1482-125">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a1482-126">Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a1482-126">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1482-127"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="a1482-127"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a1482-128">smallint</span><span class="sxs-lookup"><span data-stu-id="a1482-128">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a1482-129">Il numero di messaggi inviati dall'utente durante la conferenza.</span><span class="sxs-lookup"><span data-stu-id="a1482-129">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

