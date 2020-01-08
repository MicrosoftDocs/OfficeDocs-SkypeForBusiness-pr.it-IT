---
title: 'Lync Server 2013: tblPreference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 652312c5ca48a140ee7f17486ef98debb4e08672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="7597a-102">tblPreference in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7597a-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7597a-103">_**Argomento Ultima modifica:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="7597a-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="7597a-104">tblPreference contiene le preferenze client degli utenti.</span><span class="sxs-lookup"><span data-stu-id="7597a-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="7597a-105">Questa operazione viene in genere usata dai client precedenti a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7597a-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="7597a-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="7597a-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7597a-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="7597a-107">Column</span></span></th>
<th><span data-ttu-id="7597a-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="7597a-108">Type</span></span></th>
<th><span data-ttu-id="7597a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7597a-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7597a-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="7597a-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="7597a-111">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="7597a-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="7597a-112">Etichetta con un formato, ad esempio &lt;: URI&gt;SIP utente | nomeutente. &lt;set&gt;di preferenze.</span><span class="sxs-lookup"><span data-stu-id="7597a-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7597a-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="7597a-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="7597a-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="7597a-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7597a-115">Un numero sequenziale (per etichetta) per scopi di controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="7597a-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7597a-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="7597a-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="7597a-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="7597a-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="7597a-118">Contenuto codificato.</span><span class="sxs-lookup"><span data-stu-id="7597a-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7597a-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="7597a-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="7597a-120">int, not null</span><span class="sxs-lookup"><span data-stu-id="7597a-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7597a-121">ID dell'entità che ha aggiornato la preferenza.</span><span class="sxs-lookup"><span data-stu-id="7597a-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="7597a-122">Chiave</span><span class="sxs-lookup"><span data-stu-id="7597a-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7597a-123">Colonna</span><span class="sxs-lookup"><span data-stu-id="7597a-123">Column</span></span></th>
<th><span data-ttu-id="7597a-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7597a-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7597a-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="7597a-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="7597a-126">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="7597a-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

