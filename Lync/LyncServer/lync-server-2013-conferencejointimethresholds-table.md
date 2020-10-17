---
title: 'Lync Server 2013: tabella ConferenceJoinTimeThresholds'
description: 'Lync Server 2013: tabella ConferenceJoinTimeThresholds.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e38c8b99f444e16309882b6a8885d166fdceb9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561672"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="f3d1e-103">Tabella ConferenceJoinTimeThresholds in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3d1e-103">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3d1e-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f3d1e-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f3d1e-p101">La tabella ConferenceJoinTimeThresholds include i limiti di classificazione utilizzati dal rapporto riepilogativo Tempo di partecipazione alla conferenza. Questo rapporto riepiloga la quantità di tempo richiesto agli utenti per partecipare a una conferenza. I valori temporali vengono riportati come media e in una delle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3d1e-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="f3d1e-107">Meno di 2 secondi.</span><span class="sxs-lookup"><span data-stu-id="f3d1e-107">Less than 2 seconds.</span></span>

  - <span data-ttu-id="f3d1e-108">Tra 2 e 5 secondi.</span><span class="sxs-lookup"><span data-stu-id="f3d1e-108">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="f3d1e-109">Tra 5 e 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="f3d1e-109">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="f3d1e-110">Più di 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="f3d1e-110">More than 10 seconds.</span></span>

<span data-ttu-id="f3d1e-111">La tabella ConferenceJoinTimeThresholds include i valori di classificazione 2 secondi, 5 secondi e 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="f3d1e-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="f3d1e-112">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3d1e-112">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3d1e-113">Colonna</span><span class="sxs-lookup"><span data-stu-id="f3d1e-113">Column</span></span></th>
<th><span data-ttu-id="f3d1e-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f3d1e-114">Data Type</span></span></th>
<th><span data-ttu-id="f3d1e-115">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="f3d1e-115">Key/Index</span></span></th>
<th><span data-ttu-id="f3d1e-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f3d1e-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3d1e-117"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="f3d1e-117"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="f3d1e-118">int</span><span class="sxs-lookup"><span data-stu-id="f3d1e-118">int</span></span></p></td>
<td><p><span data-ttu-id="f3d1e-119">Principale</span><span class="sxs-lookup"><span data-stu-id="f3d1e-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="f3d1e-120">Identificatore univoco della classificazione.</span><span class="sxs-lookup"><span data-stu-id="f3d1e-120">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3d1e-121"><strong>ThresholdValue:</strong></span><span class="sxs-lookup"><span data-stu-id="f3d1e-121"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="f3d1e-122">int</span><span class="sxs-lookup"><span data-stu-id="f3d1e-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f3d1e-p102">Limite superiore per la classificazione. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="f3d1e-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="f3d1e-125">2</span><span class="sxs-lookup"><span data-stu-id="f3d1e-125">2</span></span></p></li>
<li><p><span data-ttu-id="f3d1e-126">5 </span><span class="sxs-lookup"><span data-stu-id="f3d1e-126">5</span></span></p></li>
<li><p><span data-ttu-id="f3d1e-127">10  </span><span class="sxs-lookup"><span data-stu-id="f3d1e-127">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

