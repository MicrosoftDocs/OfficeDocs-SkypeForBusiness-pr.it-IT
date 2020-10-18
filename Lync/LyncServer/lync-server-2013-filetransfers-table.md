---
title: 'Lync Server 2013: tabella FileTransfers'
description: 'Lync Server 2013: tabella FileTransfers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccde45fa3743a809499273676d567846ef292ecc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573362"
---
# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="b3ad3-103">Tabella FileTransfers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3ad3-103">FileTransfers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3ad3-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b3ad3-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b3ad3-105">Ogni record rappresenta una sessione di trasferimento file.</span><span class="sxs-lookup"><span data-stu-id="b3ad3-105">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3ad3-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="b3ad3-106">Column</span></span></th>
<th><span data-ttu-id="b3ad3-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b3ad3-107">Data Type</span></span></th>
<th><span data-ttu-id="b3ad3-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="b3ad3-108">Key/Index</span></span></th>
<th><span data-ttu-id="b3ad3-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b3ad3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3ad3-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b3ad3-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3ad3-111">datetime</span><span class="sxs-lookup"><span data-stu-id="b3ad3-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3ad3-112">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="b3ad3-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b3ad3-113">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="b3ad3-113">Time of session request.</span></span> <span data-ttu-id="b3ad3-114">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="b3ad3-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b3ad3-115">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b3ad3-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3ad3-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b3ad3-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b3ad3-117">int</span><span class="sxs-lookup"><span data-stu-id="b3ad3-117">int</span></span></p></td>
<td><p><span data-ttu-id="b3ad3-118">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="b3ad3-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b3ad3-119">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="b3ad3-119">ID number to identify the session.</span></span> <span data-ttu-id="b3ad3-120">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="b3ad3-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b3ad3-121">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b3ad3-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3ad3-122"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="b3ad3-122"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="b3ad3-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3ad3-123">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3ad3-124">Nome del file.</span><span class="sxs-lookup"><span data-stu-id="b3ad3-124">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3ad3-125"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="b3ad3-125"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="b3ad3-126">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b3ad3-126">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3ad3-127">Identificatore univoco che distingue trasferimenti diversi che interessano lo stesso nome file.</span><span class="sxs-lookup"><span data-stu-id="b3ad3-127">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3ad3-128"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="b3ad3-128"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="b3ad3-129">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="b3ad3-129">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b3ad3-130">Principale</span><span class="sxs-lookup"><span data-stu-id="b3ad3-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="b3ad3-131">Valore utilizzato per identificare ogni messaggio successivo come associato a questo.</span><span class="sxs-lookup"><span data-stu-id="b3ad3-131">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3ad3-132"><strong>Accettare</strong></span><span class="sxs-lookup"><span data-stu-id="b3ad3-132"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="b3ad3-133">po'</span><span class="sxs-lookup"><span data-stu-id="b3ad3-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3ad3-p103">Può essere TRUE o NULL. Se TRUE, allora Reject e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="b3ad3-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3ad3-136"><strong>Rifiuta</strong></span><span class="sxs-lookup"><span data-stu-id="b3ad3-136"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="b3ad3-137">po'</span><span class="sxs-lookup"><span data-stu-id="b3ad3-137">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3ad3-p104">Può essere TRUE o NULL. Se TRUE, allora Accept e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="b3ad3-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3ad3-140"><strong>Annulla</strong></span><span class="sxs-lookup"><span data-stu-id="b3ad3-140"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="b3ad3-141">po'</span><span class="sxs-lookup"><span data-stu-id="b3ad3-141">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3ad3-p105">Può essere TRUE o NULL. Se TRUE, allora Accept e Reject saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="b3ad3-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

