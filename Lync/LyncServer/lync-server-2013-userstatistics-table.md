---
title: 'Lync Server 2013: tabella UserStatistics'
description: 'Lync Server 2013: tabella UserStatistics.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75b34fa3c34af4cc9cf2cacc6ae7feb4d217114c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548532"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="4b3eb-103">Tabella UserStatistics in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b3eb-103">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b3eb-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4b3eb-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4b3eb-105">La tabella UserStatistics è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="4b3eb-105">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="4b3eb-106">Ogni record della tabella memorizza informazioni sull'utilizzo del sistema da parte di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="4b3eb-106">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="4b3eb-107">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b3eb-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b3eb-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="4b3eb-108">Column</span></span></th>
<th><span data-ttu-id="4b3eb-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4b3eb-109">Data Type</span></span></th>
<th><span data-ttu-id="4b3eb-110">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="4b3eb-110">Key/Index</span></span></th>
<th><span data-ttu-id="4b3eb-111">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4b3eb-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b3eb-112"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="4b3eb-112"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4b3eb-113">int</span><span class="sxs-lookup"><span data-stu-id="4b3eb-113">int</span></span></p></td>
<td><p><span data-ttu-id="4b3eb-114">Principale</span><span class="sxs-lookup"><span data-stu-id="4b3eb-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="4b3eb-115">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="4b3eb-115">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b3eb-116"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="4b3eb-116"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4b3eb-117">datetime</span><span class="sxs-lookup"><span data-stu-id="4b3eb-117">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4b3eb-118">Data/ora dell'ultimo accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4b3eb-118">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b3eb-119"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="4b3eb-119"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4b3eb-120">datetime</span><span class="sxs-lookup"><span data-stu-id="4b3eb-120">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4b3eb-121">Data/ora dell'ultima conferenza organizzata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4b3eb-121">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b3eb-122"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="4b3eb-122"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4b3eb-123">datetime</span><span class="sxs-lookup"><span data-stu-id="4b3eb-123">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4b3eb-124">Data/ora dell'ultimo errore di chiamata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4b3eb-124">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b3eb-125"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="4b3eb-125"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4b3eb-126">datetime</span><span class="sxs-lookup"><span data-stu-id="4b3eb-126">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4b3eb-127">Data/ora dell'ultimo errore di chiamata dell'utente in qualità di organizzatore di una conferenza.</span><span class="sxs-lookup"><span data-stu-id="4b3eb-127">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

