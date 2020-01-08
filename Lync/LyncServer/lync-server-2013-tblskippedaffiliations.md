---
title: 'Lync Server 2013: tblSkippedAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06269ede55a46757f78595d7573f3cd77414d1d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="24a94-102">tblSkippedAffiliations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24a94-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24a94-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="24a94-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="24a94-104">tblSkippedAffiliations contiene le affiliazioni che non è stato possibile leggere (in genere a causa di errori di accesso ai servizi di dominio Active Directory).</span><span class="sxs-lookup"><span data-stu-id="24a94-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="24a94-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="24a94-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24a94-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="24a94-106">Column</span></span></th>
<th><span data-ttu-id="24a94-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="24a94-107">Type</span></span></th>
<th><span data-ttu-id="24a94-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24a94-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24a94-109">prinID</span><span class="sxs-lookup"><span data-stu-id="24a94-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="24a94-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="24a94-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="24a94-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="24a94-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a94-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="24a94-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="24a94-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="24a94-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="24a94-114">Stringa che identifica l'affiliazione.</span><span class="sxs-lookup"><span data-stu-id="24a94-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="24a94-115">Il formato è: GUID: {0} URI: {1} &gt; ID:{2}</span><span class="sxs-lookup"><span data-stu-id="24a94-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a94-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="24a94-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="24a94-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="24a94-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="24a94-118">ID dell'entità che ha aggiornato la riga.</span><span class="sxs-lookup"><span data-stu-id="24a94-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="24a94-119">È sempre 1 (utente di sistema) perché Active Directory Sync è l'unica fonte per queste voci.</span><span class="sxs-lookup"><span data-stu-id="24a94-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="24a94-120">Tasti</span><span class="sxs-lookup"><span data-stu-id="24a94-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24a94-121">Colonne</span><span class="sxs-lookup"><span data-stu-id="24a94-121">Column(s)</span></span></th>
<th><span data-ttu-id="24a94-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24a94-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24a94-123">&lt;prinID, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="24a94-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="24a94-124">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="24a94-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a94-125">prinID</span><span class="sxs-lookup"><span data-stu-id="24a94-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="24a94-126">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="24a94-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

