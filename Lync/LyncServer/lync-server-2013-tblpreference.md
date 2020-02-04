---
title: 'Lync Server 2013: tblPreference'
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
ms.openlocfilehash: 9cd45dcbd6ade83d6c4404346e1752c1f78254e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="311fc-102">tblPreference in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="311fc-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="311fc-103">_**Argomento Ultima modifica:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="311fc-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="311fc-104">tblPreference contiene le preferenze client degli utenti.</span><span class="sxs-lookup"><span data-stu-id="311fc-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="311fc-105">Questa operazione viene in genere usata dai client precedenti a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="311fc-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="311fc-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="311fc-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="311fc-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="311fc-107">Column</span></span></th>
<th><span data-ttu-id="311fc-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="311fc-108">Type</span></span></th>
<th><span data-ttu-id="311fc-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="311fc-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="311fc-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="311fc-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="311fc-111">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="311fc-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="311fc-112">Etichetta con un formato, ad esempio &lt;: URI&gt;SIP utente | nomeutente. &lt;set&gt;di preferenze.</span><span class="sxs-lookup"><span data-stu-id="311fc-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="311fc-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="311fc-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="311fc-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="311fc-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="311fc-115">Un numero sequenziale (per etichetta) per scopi di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="311fc-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="311fc-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="311fc-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="311fc-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="311fc-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="311fc-118">Contenuto codificato.</span><span class="sxs-lookup"><span data-stu-id="311fc-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="311fc-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="311fc-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="311fc-120">int, not null</span><span class="sxs-lookup"><span data-stu-id="311fc-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="311fc-121">ID dell'entità che ha aggiornato la preferenza.</span><span class="sxs-lookup"><span data-stu-id="311fc-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="311fc-122">Chiave</span><span class="sxs-lookup"><span data-stu-id="311fc-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="311fc-123">Colonna</span><span class="sxs-lookup"><span data-stu-id="311fc-123">Column</span></span></th>
<th><span data-ttu-id="311fc-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="311fc-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="311fc-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="311fc-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="311fc-126">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="311fc-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

