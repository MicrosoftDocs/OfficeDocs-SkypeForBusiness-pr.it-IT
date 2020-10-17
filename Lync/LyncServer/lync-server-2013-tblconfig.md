---
title: 'Lync Server 2013: tblConfig'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2efbed57d88e7312bc1da3a9da8f8057fd6696a5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509373"
---
# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="ad5c5-102">tblConfig in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad5c5-102">tblConfig in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad5c5-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ad5c5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ad5c5-104">tblConfig contiene una configurazione non supportata del server Chat persistente, in una riga.</span><span class="sxs-lookup"><span data-stu-id="ad5c5-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="ad5c5-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="ad5c5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad5c5-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="ad5c5-106">Column</span></span></th>
<th><span data-ttu-id="ad5c5-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="ad5c5-107">Type</span></span></th>
<th><span data-ttu-id="ad5c5-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad5c5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad5c5-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="ad5c5-109">configLabel</span></span></p></td>
<td><p><span data-ttu-id="ad5c5-110">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="ad5c5-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="ad5c5-111">Contiene &quot; pool.&quot;</span><span class="sxs-lookup"><span data-stu-id="ad5c5-111">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad5c5-112">configContent</span><span class="sxs-lookup"><span data-stu-id="ad5c5-112">configContent</span></span></p></td>
<td><p><span data-ttu-id="ad5c5-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="ad5c5-113">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="ad5c5-114">Contenuto della configurazione.</span><span class="sxs-lookup"><span data-stu-id="ad5c5-114">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad5c5-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="ad5c5-115">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="ad5c5-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="ad5c5-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="ad5c5-117">ID univoco dell'istanza di database.</span><span class="sxs-lookup"><span data-stu-id="ad5c5-117">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="ad5c5-118">Chiave</span><span class="sxs-lookup"><span data-stu-id="ad5c5-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad5c5-119">Colonna</span><span class="sxs-lookup"><span data-stu-id="ad5c5-119">Column</span></span></th>
<th><span data-ttu-id="ad5c5-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad5c5-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad5c5-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="ad5c5-121">configLabel</span></span></p></td>
<td><p><span data-ttu-id="ad5c5-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="ad5c5-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

