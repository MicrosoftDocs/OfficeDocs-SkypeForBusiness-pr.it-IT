---
title: 'Lync Server 2013: Tabella FileTransfers'
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
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="e1b59-102">Tabella FileTransfers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1b59-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1b59-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e1b59-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e1b59-104">Ogni record rappresenta una sessione di trasferimento file.</span><span class="sxs-lookup"><span data-stu-id="e1b59-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1b59-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="e1b59-105">Column</span></span></th>
<th><span data-ttu-id="e1b59-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e1b59-106">Data Type</span></span></th>
<th><span data-ttu-id="e1b59-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="e1b59-107">Key/Index</span></span></th>
<th><span data-ttu-id="e1b59-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e1b59-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1b59-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e1b59-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b59-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="e1b59-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e1b59-111">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="e1b59-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1b59-112">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="e1b59-112">Time of session request.</span></span> <span data-ttu-id="e1b59-113">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="e1b59-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e1b59-114">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e1b59-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b59-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e1b59-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b59-116">int</span><span class="sxs-lookup"><span data-stu-id="e1b59-116">int</span></span></p></td>
<td><p><span data-ttu-id="e1b59-117">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="e1b59-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1b59-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="e1b59-118">ID number to identify the session.</span></span> <span data-ttu-id="e1b59-119">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="e1b59-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e1b59-120">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e1b59-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b59-121"><strong>Nome file</strong></span><span class="sxs-lookup"><span data-stu-id="e1b59-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b59-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e1b59-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b59-123">Nome del file.</span><span class="sxs-lookup"><span data-stu-id="e1b59-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b59-124"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="e1b59-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b59-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e1b59-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b59-126">Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome file.</span><span class="sxs-lookup"><span data-stu-id="e1b59-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b59-127"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="e1b59-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b59-128">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="e1b59-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e1b59-129">Principale</span><span class="sxs-lookup"><span data-stu-id="e1b59-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="e1b59-130">Usato per identificare ogni messaggio di follow-up associato a questo.</span><span class="sxs-lookup"><span data-stu-id="e1b59-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b59-131"><strong>Accettare</strong></span><span class="sxs-lookup"><span data-stu-id="e1b59-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b59-132">po'</span><span class="sxs-lookup"><span data-stu-id="e1b59-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b59-133">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="e1b59-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="e1b59-134">Se TRUE, quindi Reject e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="e1b59-134">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b59-135"><strong>Rifiutare</strong></span><span class="sxs-lookup"><span data-stu-id="e1b59-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b59-136">po'</span><span class="sxs-lookup"><span data-stu-id="e1b59-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b59-137">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="e1b59-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="e1b59-138">Se TRUE, accetta e Annulla sarà NULL.</span><span class="sxs-lookup"><span data-stu-id="e1b59-138">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b59-139"><strong>Annulla</strong></span><span class="sxs-lookup"><span data-stu-id="e1b59-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="e1b59-140">po'</span><span class="sxs-lookup"><span data-stu-id="e1b59-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1b59-141">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="e1b59-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="e1b59-142">Se TRUE, accetta e rifiuta sarà NULL.</span><span class="sxs-lookup"><span data-stu-id="e1b59-142">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

