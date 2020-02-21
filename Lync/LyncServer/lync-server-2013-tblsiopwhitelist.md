---
title: 'Lync Server 2013: tblSiopWhiteList'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48183310
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625400f6b6cd602de247cc0bdf612e81713e1663
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="484de-102">tblSiopWhiteList in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="484de-102">tblSiopWhiteList in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="484de-103">_**Ultimo argomento modificato:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="484de-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="484de-104">tblSiopWhiteList è l'elenco dei componenti aggiuntivi registrati che possono essere associati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="484de-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="484de-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="484de-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="484de-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="484de-106">Column</span></span></th>
<th><span data-ttu-id="484de-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="484de-107">Type</span></span></th>
<th><span data-ttu-id="484de-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="484de-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="484de-109">siopID</span><span class="sxs-lookup"><span data-stu-id="484de-109">siopID</span></span></p></td>
<td><p><span data-ttu-id="484de-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="484de-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="484de-111">GUID del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="484de-111">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="484de-112">siopName</span><span class="sxs-lookup"><span data-stu-id="484de-112">siopName</span></span></p></td>
<td><p><span data-ttu-id="484de-113">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="484de-113">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="484de-114">Nome visualizzato del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="484de-114">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="484de-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="484de-115">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="484de-116">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="484de-116">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="484de-117">URL del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="484de-117">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="484de-118">Chiave</span><span class="sxs-lookup"><span data-stu-id="484de-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="484de-119">Colonna</span><span class="sxs-lookup"><span data-stu-id="484de-119">Column</span></span></th>
<th><span data-ttu-id="484de-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="484de-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="484de-121">siopID</span><span class="sxs-lookup"><span data-stu-id="484de-121">siopID</span></span></p></td>
<td><p><span data-ttu-id="484de-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="484de-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

