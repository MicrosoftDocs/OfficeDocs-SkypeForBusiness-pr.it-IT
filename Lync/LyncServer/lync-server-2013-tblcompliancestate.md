---
title: 'Lync Server 2013: tblComplianceState'
description: 'Lync Server 2013: tblComplianceState.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6eaf35eee8b4e24ec4d04e607fa77fd91b91e4e8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568082"
---
# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="e4f01-103">tblComplianceState in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4f01-103">tblComplianceState in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4f01-104">_**Ultimo argomento modificato:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="e4f01-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="e4f01-105">tblComplianceState contiene informazioni sullo stato della conformità a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="e4f01-105">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="e4f01-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="e4f01-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4f01-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="e4f01-107">Column</span></span></th>
<th><span data-ttu-id="e4f01-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="e4f01-108">Type</span></span></th>
<th><span data-ttu-id="e4f01-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4f01-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4f01-110">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="e4f01-110">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="e4f01-111">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="e4f01-111">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="e4f01-112">ID dell'ultimo evento di conformità elaborato.</span><span class="sxs-lookup"><span data-stu-id="e4f01-112">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f01-113">activeServerID</span><span class="sxs-lookup"><span data-stu-id="e4f01-113">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="e4f01-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="e4f01-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e4f01-115">ID del server di conformità che detiene il blocco esclusivo sul database, o -1 se assente.</span><span class="sxs-lookup"><span data-stu-id="e4f01-115">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f01-116">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="e4f01-116">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="e4f01-117">datetime2, not null</span><span class="sxs-lookup"><span data-stu-id="e4f01-117">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="e4f01-118">Ora di scadenza del blocco (se activeServerID è diverso da  -1).</span><span class="sxs-lookup"><span data-stu-id="e4f01-118">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

