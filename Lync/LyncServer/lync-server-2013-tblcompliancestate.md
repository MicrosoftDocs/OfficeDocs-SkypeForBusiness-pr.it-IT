---
title: 'Lync Server 2013: tblComplianceState'
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
ms.openlocfilehash: a744a29d36106e921c65925588f285af6d1390e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="34982-102">tblComplianceState in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34982-102">tblComplianceState in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34982-103">_**Ultimo argomento modificato:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="34982-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="34982-104">tblComplianceState contiene informazioni sullo stato della conformità a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="34982-104">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="34982-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="34982-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34982-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="34982-106">Column</span></span></th>
<th><span data-ttu-id="34982-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="34982-107">Type</span></span></th>
<th><span data-ttu-id="34982-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34982-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34982-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="34982-109">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="34982-110">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="34982-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="34982-111">ID dell'ultimo evento di conformità elaborato.</span><span class="sxs-lookup"><span data-stu-id="34982-111">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34982-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="34982-112">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="34982-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="34982-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="34982-114">ID del server di conformità che detiene il blocco esclusivo sul database, o -1 se assente.</span><span class="sxs-lookup"><span data-stu-id="34982-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34982-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="34982-115">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="34982-116">datetime2, not null</span><span class="sxs-lookup"><span data-stu-id="34982-116">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="34982-117">Ora di scadenza del blocco (se activeServerID è diverso da  -1).</span><span class="sxs-lookup"><span data-stu-id="34982-117">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

