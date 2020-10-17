---
title: 'Lync Server 2013: Tabella DeRegisterType'
description: 'Lync Server 2013: Tabella DeRegisterType.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afad63c2abeba3e91565e07dac75d0ac6c96ca3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555352"
---
# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="58ed2-103">Tabella DeRegisterType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58ed2-103">DeRegisterType table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58ed2-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="58ed2-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="58ed2-105">La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di deregistri degli utenti, ad esempio ' client avviato ',' Registrazione scaduta ' oppure ' client interrotto la risposta '.</span><span class="sxs-lookup"><span data-stu-id="58ed2-105">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58ed2-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="58ed2-106">Column</span></span></th>
<th><span data-ttu-id="58ed2-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="58ed2-107">Data Type</span></span></th>
<th><span data-ttu-id="58ed2-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="58ed2-108">Key/Index</span></span></th>
<th><span data-ttu-id="58ed2-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="58ed2-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58ed2-110"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="58ed2-110"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="58ed2-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="58ed2-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="58ed2-112">Principale</span><span class="sxs-lookup"><span data-stu-id="58ed2-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58ed2-113"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="58ed2-113"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="58ed2-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="58ed2-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="58ed2-115">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="58ed2-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="58ed2-116">0 - Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="58ed2-116">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="58ed2-117">1-annullamento della registrazione avviata dal client</span><span class="sxs-lookup"><span data-stu-id="58ed2-117">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="58ed2-118">2-Registrazione scaduta</span><span class="sxs-lookup"><span data-stu-id="58ed2-118">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="58ed2-119">3 – il client si è bloccato</span><span class="sxs-lookup"><span data-stu-id="58ed2-119">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="58ed2-120">4-attributi degli utenti modificati</span><span class="sxs-lookup"><span data-stu-id="58ed2-120">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="58ed2-121">5-modifica del registrar preferito</span><span class="sxs-lookup"><span data-stu-id="58ed2-121">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="58ed2-122">6-client legacy in modalità sopravvivenza</span><span class="sxs-lookup"><span data-stu-id="58ed2-122">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

