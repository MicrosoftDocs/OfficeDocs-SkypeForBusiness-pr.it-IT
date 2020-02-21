---
title: 'Lync Server 2013: tabella locations'
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
ms.openlocfilehash: d93300acda297a026af03070680825899a608d86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="a8f71-102">Tabella Locations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8f71-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8f71-103">_**Ultimo argomento modificato:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="a8f71-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="a8f71-104">Ogni record rappresenta un riferimento di posizione in una chiamata di emergenza, ad esempio in una chiamata al servizio 118.</span><span class="sxs-lookup"><span data-stu-id="a8f71-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8f71-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="a8f71-105">Column</span></span></th>
<th><span data-ttu-id="a8f71-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a8f71-106">Data Type</span></span></th>
<th><span data-ttu-id="a8f71-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="a8f71-107">Key/Index</span></span></th>
<th><span data-ttu-id="a8f71-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a8f71-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8f71-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a8f71-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a8f71-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a8f71-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a8f71-111">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="a8f71-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a8f71-112">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="a8f71-112">Time of session request.</span></span> <span data-ttu-id="a8f71-113">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="a8f71-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a8f71-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a8f71-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8f71-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a8f71-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a8f71-116">int</span><span class="sxs-lookup"><span data-stu-id="a8f71-116">int</span></span></p></td>
<td><p><span data-ttu-id="a8f71-117">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="a8f71-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a8f71-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="a8f71-118">ID number to identify the session.</span></span> <span data-ttu-id="a8f71-119">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="a8f71-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a8f71-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a8f71-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8f71-121"><strong>Posizione</strong></span><span class="sxs-lookup"><span data-stu-id="a8f71-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="a8f71-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="a8f71-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a8f71-123">Posizione della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="a8f71-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

