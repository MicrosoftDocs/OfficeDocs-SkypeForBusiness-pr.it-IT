---
title: 'Lync Server 2013: tabella UserStatistics'
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
ms.openlocfilehash: 98c24093f332f568daadfb0cd336f0d5fde3eb35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="927ac-102">Tabella UserStatistics in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="927ac-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="927ac-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="927ac-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="927ac-104">La tabella UserStatistics è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="927ac-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="927ac-105">Ogni record della tabella memorizza informazioni sull'utilizzo del sistema da parte di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="927ac-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="927ac-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="927ac-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="927ac-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="927ac-107">Column</span></span></th>
<th><span data-ttu-id="927ac-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="927ac-108">Data Type</span></span></th>
<th><span data-ttu-id="927ac-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="927ac-109">Key/Index</span></span></th>
<th><span data-ttu-id="927ac-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="927ac-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="927ac-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="927ac-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="927ac-112">int</span><span class="sxs-lookup"><span data-stu-id="927ac-112">int</span></span></p></td>
<td><p><span data-ttu-id="927ac-113">Principale</span><span class="sxs-lookup"><span data-stu-id="927ac-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="927ac-114">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="927ac-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="927ac-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="927ac-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="927ac-116">datetime</span><span class="sxs-lookup"><span data-stu-id="927ac-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="927ac-117">Data/ora dell'ultimo accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="927ac-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="927ac-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="927ac-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="927ac-119">datetime</span><span class="sxs-lookup"><span data-stu-id="927ac-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="927ac-120">Data/ora dell'ultima conferenza organizzata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="927ac-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="927ac-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="927ac-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="927ac-122">datetime</span><span class="sxs-lookup"><span data-stu-id="927ac-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="927ac-123">Data/ora dell'ultimo errore di chiamata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="927ac-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="927ac-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="927ac-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="927ac-125">datetime</span><span class="sxs-lookup"><span data-stu-id="927ac-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="927ac-126">Data/ora dell'ultimo errore di chiamata dell'utente in qualità di organizzatore di una conferenza.</span><span class="sxs-lookup"><span data-stu-id="927ac-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

