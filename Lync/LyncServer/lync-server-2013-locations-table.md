---
title: 'Lync Server 2013: Tabella Locations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6b26f8c30c0d26fd265d95542b79f919153bc15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="85530-102">Tabella Locations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85530-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85530-103">_**Argomento Ultima modifica:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="85530-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="85530-104">Ogni record rappresenta un riferimento di posizione in una chiamata di emergenza, ad esempio una chiamata E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="85530-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85530-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="85530-105">Column</span></span></th>
<th><span data-ttu-id="85530-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="85530-106">Data Type</span></span></th>
<th><span data-ttu-id="85530-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="85530-107">Key/Index</span></span></th>
<th><span data-ttu-id="85530-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="85530-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85530-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="85530-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="85530-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="85530-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="85530-111">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="85530-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="85530-112">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="85530-112">Time of session request.</span></span> <span data-ttu-id="85530-113">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="85530-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="85530-114">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85530-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85530-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="85530-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="85530-116">int</span><span class="sxs-lookup"><span data-stu-id="85530-116">int</span></span></p></td>
<td><p><span data-ttu-id="85530-117">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="85530-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="85530-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="85530-118">ID number to identify the session.</span></span> <span data-ttu-id="85530-119">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="85530-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="85530-120">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="85530-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85530-121"><strong>Posizione</strong></span><span class="sxs-lookup"><span data-stu-id="85530-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="85530-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="85530-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85530-123">Posizione della chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="85530-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

