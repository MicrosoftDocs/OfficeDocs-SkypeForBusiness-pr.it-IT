---
title: 'Lync Server 2013: Tabella DeRegisterType'
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
ms.openlocfilehash: 58f1bee5dfa5a0f24b46ba51abafee8d0a89b0a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="512b2-102">Tabella DeRegisterType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="512b2-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="512b2-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="512b2-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="512b2-104">La tabella DeRegisterType è una tabella statica in cui è archiviato l'elenco dei possibili tipi di deregistri degli utenti, ad esempio ' client avviato ',' Registrazione scaduta ' oppure ' client interrotto la risposta '.</span><span class="sxs-lookup"><span data-stu-id="512b2-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="512b2-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="512b2-105">Column</span></span></th>
<th><span data-ttu-id="512b2-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="512b2-106">Data Type</span></span></th>
<th><span data-ttu-id="512b2-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="512b2-107">Key/Index</span></span></th>
<th><span data-ttu-id="512b2-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="512b2-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="512b2-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="512b2-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="512b2-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="512b2-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="512b2-111">Principale</span><span class="sxs-lookup"><span data-stu-id="512b2-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="512b2-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="512b2-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="512b2-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="512b2-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="512b2-114">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="512b2-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="512b2-115">0 - Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="512b2-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="512b2-116">1-annullamento della registrazione avviata dal client</span><span class="sxs-lookup"><span data-stu-id="512b2-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="512b2-117">2-Registrazione scaduta</span><span class="sxs-lookup"><span data-stu-id="512b2-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="512b2-118">3 – il client si è bloccato</span><span class="sxs-lookup"><span data-stu-id="512b2-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="512b2-119">4-attributi degli utenti modificati</span><span class="sxs-lookup"><span data-stu-id="512b2-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="512b2-120">5-modifica del registrar preferito</span><span class="sxs-lookup"><span data-stu-id="512b2-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="512b2-121">6-client legacy in modalità sopravvivenza</span><span class="sxs-lookup"><span data-stu-id="512b2-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

