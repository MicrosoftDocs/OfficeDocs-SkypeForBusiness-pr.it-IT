---
title: 'Lync Server 2013: tabella UserStatistics'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0f684850625f61ca72bbcc9c4bc53b56fcc6b38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="5e2aa-102">Tabella UserStatistics in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e2aa-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e2aa-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5e2aa-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5e2aa-104">La tabella UserStatistics è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="5e2aa-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="5e2aa-105">Ogni record nella tabella archivia le informazioni sull'uso di un singolo utente del sistema.</span><span class="sxs-lookup"><span data-stu-id="5e2aa-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="5e2aa-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2aa-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e2aa-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="5e2aa-107">Column</span></span></th>
<th><span data-ttu-id="5e2aa-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5e2aa-108">Data Type</span></span></th>
<th><span data-ttu-id="5e2aa-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="5e2aa-109">Key/Index</span></span></th>
<th><span data-ttu-id="5e2aa-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5e2aa-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e2aa-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="5e2aa-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e2aa-112">int</span><span class="sxs-lookup"><span data-stu-id="5e2aa-112">int</span></span></p></td>
<td><p><span data-ttu-id="5e2aa-113">Principale</span><span class="sxs-lookup"><span data-stu-id="5e2aa-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="5e2aa-114">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="5e2aa-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e2aa-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e2aa-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e2aa-116">DateTime</span><span class="sxs-lookup"><span data-stu-id="5e2aa-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e2aa-117">Ultima volta che l'utente ha effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5e2aa-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e2aa-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e2aa-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e2aa-119">DateTime</span><span class="sxs-lookup"><span data-stu-id="5e2aa-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e2aa-120">L'ultima volta che l'utente ha organizzato una conferenza.</span><span class="sxs-lookup"><span data-stu-id="5e2aa-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e2aa-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e2aa-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e2aa-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="5e2aa-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e2aa-123">L'ultima volta che l'utente ha riscontrato un errore di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5e2aa-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e2aa-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e2aa-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e2aa-125">DateTime</span><span class="sxs-lookup"><span data-stu-id="5e2aa-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e2aa-126">L'ultima volta che l'utente ha sperimentato un errore di chiamata come organizzatore di conferenze.</span><span class="sxs-lookup"><span data-stu-id="5e2aa-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

