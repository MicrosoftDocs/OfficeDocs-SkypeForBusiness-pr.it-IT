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
ms.openlocfilehash: 7609747848e1943a08eff2fa77b87f0168710f81
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="c07ce-102">Tabella UserStatistics in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c07ce-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c07ce-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c07ce-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c07ce-104">La tabella UserStatistics è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="c07ce-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="c07ce-105">Ogni record nella tabella archivia le informazioni sull'uso di un singolo utente del sistema.</span><span class="sxs-lookup"><span data-stu-id="c07ce-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="c07ce-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c07ce-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c07ce-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="c07ce-107">Column</span></span></th>
<th><span data-ttu-id="c07ce-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c07ce-108">Data Type</span></span></th>
<th><span data-ttu-id="c07ce-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="c07ce-109">Key/Index</span></span></th>
<th><span data-ttu-id="c07ce-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c07ce-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c07ce-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="c07ce-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="c07ce-112">int</span><span class="sxs-lookup"><span data-stu-id="c07ce-112">int</span></span></p></td>
<td><p><span data-ttu-id="c07ce-113">Principale</span><span class="sxs-lookup"><span data-stu-id="c07ce-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c07ce-114">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="c07ce-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c07ce-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="c07ce-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c07ce-116">DateTime</span><span class="sxs-lookup"><span data-stu-id="c07ce-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c07ce-117">Ultima volta che l'utente ha effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="c07ce-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c07ce-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="c07ce-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c07ce-119">DateTime</span><span class="sxs-lookup"><span data-stu-id="c07ce-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c07ce-120">L'ultima volta che l'utente ha organizzato una conferenza.</span><span class="sxs-lookup"><span data-stu-id="c07ce-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c07ce-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="c07ce-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c07ce-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="c07ce-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c07ce-123">L'ultima volta che l'utente ha riscontrato un errore di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c07ce-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c07ce-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="c07ce-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c07ce-125">DateTime</span><span class="sxs-lookup"><span data-stu-id="c07ce-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c07ce-126">L'ultima volta che l'utente ha sperimentato un errore di chiamata come organizzatore di conferenze.</span><span class="sxs-lookup"><span data-stu-id="c07ce-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

