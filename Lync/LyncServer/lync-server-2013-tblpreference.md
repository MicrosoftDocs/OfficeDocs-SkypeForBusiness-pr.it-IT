---
title: 'Lync Server 2013: tblPreference'
description: 'Lync Server 2013: tblPreference.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86e8b81a6af93e9bf1d7673e54492579a1bed08e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547512"
---
# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="e192c-103">tblPreference in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e192c-103">tblPreference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e192c-104">_**Ultimo argomento modificato:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="e192c-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="e192c-105">tblPreference contiene le preferenze client degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e192c-105">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="e192c-106">Questo è in genere utilizzato dai client precedenti a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e192c-106">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="e192c-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="e192c-107">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e192c-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="e192c-108">Column</span></span></th>
<th><span data-ttu-id="e192c-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="e192c-109">Type</span></span></th>
<th><span data-ttu-id="e192c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e192c-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e192c-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="e192c-111">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="e192c-112">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="e192c-112">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="e192c-113">Etichetta con un formato, ad esempio: &lt; URI SIP utente &gt; | nome utente. &lt; set di preferenze &gt; .</span><span class="sxs-lookup"><span data-stu-id="e192c-113">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e192c-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="e192c-114">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="e192c-115">int, not null</span><span class="sxs-lookup"><span data-stu-id="e192c-115">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e192c-116">Un numero sequenziale (per etichetta) per scopi di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="e192c-116">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e192c-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="e192c-117">prefContent</span></span></p></td>
<td><p><span data-ttu-id="e192c-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="e192c-118">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="e192c-119">Contenuto codificato.</span><span class="sxs-lookup"><span data-stu-id="e192c-119">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e192c-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="e192c-120">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="e192c-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="e192c-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e192c-122">ID dell'entità che ha aggiornato la preferenza.</span><span class="sxs-lookup"><span data-stu-id="e192c-122">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="e192c-123">Chiave</span><span class="sxs-lookup"><span data-stu-id="e192c-123">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e192c-124">Colonna</span><span class="sxs-lookup"><span data-stu-id="e192c-124">Column</span></span></th>
<th><span data-ttu-id="e192c-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e192c-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e192c-126">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="e192c-126">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e192c-127">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="e192c-127">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

