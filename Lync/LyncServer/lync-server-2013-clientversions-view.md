---
title: 'Lync Server 2013: Visualizzazione ClientVersions'
description: 'Lync Server 2013: Visualizzazione ClientVersions.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42ede7107a59db3162ac7f5344e47e81a80d57df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542802"
---
# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="74e6b-103">Visualizzazione ClientVersions in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74e6b-103">ClientVersions view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74e6b-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="74e6b-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="74e6b-105">La Visualizzazione ClientVersions archivia le informazioni sui diversi tipi di client e le versioni che hanno partecipato alle sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="74e6b-105">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="74e6b-106">Ogni record nella visualizzazione rappresenta una versione client.</span><span class="sxs-lookup"><span data-stu-id="74e6b-106">Each record in the view represents one client version.</span></span> <span data-ttu-id="74e6b-107">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74e6b-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74e6b-108">Per alcune colonne possono essere presenti più record.</span><span class="sxs-lookup"><span data-stu-id="74e6b-108">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74e6b-109">Colonna</span><span class="sxs-lookup"><span data-stu-id="74e6b-109">Column</span></span></th>
<th><span data-ttu-id="74e6b-110">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74e6b-110">Data Type</span></span></th>
<th><span data-ttu-id="74e6b-111">Dettagli</span><span class="sxs-lookup"><span data-stu-id="74e6b-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74e6b-112"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="74e6b-112"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="74e6b-113">int</span><span class="sxs-lookup"><span data-stu-id="74e6b-113">int</span></span></p></td>
<td><p><span data-ttu-id="74e6b-114">Numero univoco che identifica il tipo di client e la versione.</span><span class="sxs-lookup"><span data-stu-id="74e6b-114">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e6b-115"><strong>Versione</strong></span><span class="sxs-lookup"><span data-stu-id="74e6b-115"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="74e6b-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74e6b-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74e6b-117">Rappresenta l'agente utente.</span><span class="sxs-lookup"><span data-stu-id="74e6b-117">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74e6b-118"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="74e6b-118"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="74e6b-119">int</span><span class="sxs-lookup"><span data-stu-id="74e6b-119">int</span></span></p></td>
<td><p><span data-ttu-id="74e6b-120">Tipo di client.</span><span class="sxs-lookup"><span data-stu-id="74e6b-120">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e6b-121"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="74e6b-121"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="74e6b-122">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="74e6b-122">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="74e6b-123">Categoria a cui appartiene il client.</span><span class="sxs-lookup"><span data-stu-id="74e6b-123">Category that the client belongs to.</span></span> <span data-ttu-id="74e6b-124">Ad esempio, il client Conferencing_Attendant_1 .0 appartiene a ClientCategory CAA.</span><span class="sxs-lookup"><span data-stu-id="74e6b-124">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

