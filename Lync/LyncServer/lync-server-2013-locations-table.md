---
title: 'Lync Server 2013: tabella locations'
description: 'Lync Server 2013: tabella locations.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d07b6d3d3820f4efb3310adf0734a7e10c53e6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570582"
---
# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="827b5-103">Tabella Locations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="827b5-103">Locations table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="827b5-104">_**Ultimo argomento modificato:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="827b5-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="827b5-105">Ogni record rappresenta un riferimento di posizione in una chiamata di emergenza, ad esempio in una chiamata al servizio 118.</span><span class="sxs-lookup"><span data-stu-id="827b5-105">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="827b5-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="827b5-106">Column</span></span></th>
<th><span data-ttu-id="827b5-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="827b5-107">Data Type</span></span></th>
<th><span data-ttu-id="827b5-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="827b5-108">Key/Index</span></span></th>
<th><span data-ttu-id="827b5-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="827b5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="827b5-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="827b5-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="827b5-111">datetime</span><span class="sxs-lookup"><span data-stu-id="827b5-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="827b5-112">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="827b5-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="827b5-113">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="827b5-113">Time of session request.</span></span> <span data-ttu-id="827b5-114">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="827b5-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="827b5-115">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="827b5-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="827b5-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="827b5-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="827b5-117">int</span><span class="sxs-lookup"><span data-stu-id="827b5-117">int</span></span></p></td>
<td><p><span data-ttu-id="827b5-118">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="827b5-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="827b5-119">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="827b5-119">ID number to identify the session.</span></span> <span data-ttu-id="827b5-120">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="827b5-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="827b5-121">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="827b5-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="827b5-122"><strong>Posizione</strong></span><span class="sxs-lookup"><span data-stu-id="827b5-122"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="827b5-123">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="827b5-123">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="827b5-124">Posizione della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="827b5-124">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

