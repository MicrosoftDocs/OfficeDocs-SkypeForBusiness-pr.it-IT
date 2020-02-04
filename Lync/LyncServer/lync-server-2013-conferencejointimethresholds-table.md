---
title: 'Lync Server 2013: tabella ConferenceJoinTimeThresholds'
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
ms.openlocfilehash: baf29af4b9d1f2b026271b84cb54436e8f4b233f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="08544-102">Tabella ConferenceJoinTimeThresholds in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08544-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08544-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="08544-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="08544-104">La tabella ConferenceJoinTimeThresholds contiene i limiti di classificazione usati dal report di riepilogo dell'ora di partecipazione alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="08544-104">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="08544-105">Il report Riepilogo temporale per la conferenza di partecipazione riepiloga il tempo necessario per consentire agli utenti di partecipare a una conferenza con successo. questi valori temporali vengono segnalati sia come media che in una delle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="08544-105">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="08544-106">Meno di 2 secondi.</span><span class="sxs-lookup"><span data-stu-id="08544-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="08544-107">Tra 2 secondi e 5 secondi.</span><span class="sxs-lookup"><span data-stu-id="08544-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="08544-108">Tra 5 secondi e 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="08544-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="08544-109">Più di 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="08544-109">More than 10 seconds.</span></span>

<span data-ttu-id="08544-110">La tabella ConferenceJoinTimeThresholds contiene i valori di classificazione 2 secondi, 5 secondi e 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="08544-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="08544-111">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="08544-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08544-112">Colonna</span><span class="sxs-lookup"><span data-stu-id="08544-112">Column</span></span></th>
<th><span data-ttu-id="08544-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="08544-113">Data Type</span></span></th>
<th><span data-ttu-id="08544-114">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="08544-114">Key/Index</span></span></th>
<th><span data-ttu-id="08544-115">Dettagli</span><span class="sxs-lookup"><span data-stu-id="08544-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08544-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="08544-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="08544-117">int</span><span class="sxs-lookup"><span data-stu-id="08544-117">int</span></span></p></td>
<td><p><span data-ttu-id="08544-118">Principale</span><span class="sxs-lookup"><span data-stu-id="08544-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="08544-119">Identificatore univoco per la classificazione.</span><span class="sxs-lookup"><span data-stu-id="08544-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08544-120"><strong>ThresholdValue:</strong></span><span class="sxs-lookup"><span data-stu-id="08544-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="08544-121">int</span><span class="sxs-lookup"><span data-stu-id="08544-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="08544-122">Limite superiore per la classificazione.</span><span class="sxs-lookup"><span data-stu-id="08544-122">Upper limit for the classification.</span></span> <span data-ttu-id="08544-123">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="08544-123">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="08544-124">2</span><span class="sxs-lookup"><span data-stu-id="08544-124">2</span></span></p></li>
<li><p><span data-ttu-id="08544-125">5</span><span class="sxs-lookup"><span data-stu-id="08544-125">5</span></span></p></li>
<li><p><span data-ttu-id="08544-126">10</span><span class="sxs-lookup"><span data-stu-id="08544-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

