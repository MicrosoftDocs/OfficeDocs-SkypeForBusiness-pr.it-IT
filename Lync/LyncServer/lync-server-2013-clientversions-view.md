---
title: 'Lync Server 2013: Visualizzazione ClientVersions'
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
ms.openlocfilehash: 3c668f56cfa1d4fdf1c2a189199a6faa960073ff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="de5ed-102">Visualizzazione ClientVersions in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de5ed-102">ClientVersions view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de5ed-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="de5ed-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="de5ed-104">La Visualizzazione ClientVersions archivia le informazioni sui diversi tipi di client e le versioni che hanno partecipato alle sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="de5ed-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="de5ed-105">Ogni record nella visualizzazione rappresenta una versione client.</span><span class="sxs-lookup"><span data-stu-id="de5ed-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="de5ed-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de5ed-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de5ed-107">Per alcune colonne possono essere presenti più record.</span><span class="sxs-lookup"><span data-stu-id="de5ed-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de5ed-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="de5ed-108">Column</span></span></th>
<th><span data-ttu-id="de5ed-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="de5ed-109">Data Type</span></span></th>
<th><span data-ttu-id="de5ed-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="de5ed-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de5ed-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="de5ed-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="de5ed-112">int</span><span class="sxs-lookup"><span data-stu-id="de5ed-112">int</span></span></p></td>
<td><p><span data-ttu-id="de5ed-113">Numero univoco che identifica il tipo di client e la versione.</span><span class="sxs-lookup"><span data-stu-id="de5ed-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de5ed-114"><strong>Versione</strong></span><span class="sxs-lookup"><span data-stu-id="de5ed-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="de5ed-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="de5ed-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="de5ed-116">Rappresenta l'agente utente.</span><span class="sxs-lookup"><span data-stu-id="de5ed-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de5ed-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="de5ed-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="de5ed-118">int</span><span class="sxs-lookup"><span data-stu-id="de5ed-118">int</span></span></p></td>
<td><p><span data-ttu-id="de5ed-119">Tipo di client.</span><span class="sxs-lookup"><span data-stu-id="de5ed-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de5ed-120"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="de5ed-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="de5ed-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="de5ed-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="de5ed-122">Categoria a cui appartiene il client.</span><span class="sxs-lookup"><span data-stu-id="de5ed-122">Category that the client belongs to.</span></span> <span data-ttu-id="de5ed-123">Ad esempio, il client Conferencing_Attendant_1 .0 appartiene a ClientCategory CAA.</span><span class="sxs-lookup"><span data-stu-id="de5ed-123">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

