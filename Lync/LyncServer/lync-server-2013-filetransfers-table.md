---
title: 'Lync Server 2013: tabella FileTransfers'
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
ms.openlocfilehash: 3f98cb2ecafbc67bc4a2c231717d18a728363fe0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="a5d18-102">Tabella FileTransfers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5d18-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5d18-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a5d18-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a5d18-104">Ogni record rappresenta una sessione di trasferimento file.</span><span class="sxs-lookup"><span data-stu-id="a5d18-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5d18-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="a5d18-105">Column</span></span></th>
<th><span data-ttu-id="a5d18-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a5d18-106">Data Type</span></span></th>
<th><span data-ttu-id="a5d18-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="a5d18-107">Key/Index</span></span></th>
<th><span data-ttu-id="a5d18-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a5d18-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5d18-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a5d18-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d18-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a5d18-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a5d18-111">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="a5d18-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5d18-112">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="a5d18-112">Time of session request.</span></span> <span data-ttu-id="a5d18-113">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="a5d18-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a5d18-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a5d18-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d18-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a5d18-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d18-116">int</span><span class="sxs-lookup"><span data-stu-id="a5d18-116">int</span></span></p></td>
<td><p><span data-ttu-id="a5d18-117">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="a5d18-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5d18-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="a5d18-118">ID number to identify the session.</span></span> <span data-ttu-id="a5d18-119">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="a5d18-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a5d18-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a5d18-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d18-121"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="a5d18-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d18-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a5d18-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d18-123">Nome del file.</span><span class="sxs-lookup"><span data-stu-id="a5d18-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d18-124"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="a5d18-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d18-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a5d18-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d18-126">Identificatore univoco che distingue trasferimenti diversi che interessano lo stesso nome file.</span><span class="sxs-lookup"><span data-stu-id="a5d18-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d18-127"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="a5d18-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d18-128">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="a5d18-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a5d18-129">Principale</span><span class="sxs-lookup"><span data-stu-id="a5d18-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="a5d18-130">Valore utilizzato per identificare ogni messaggio successivo come associato a questo.</span><span class="sxs-lookup"><span data-stu-id="a5d18-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d18-131"><strong>Accettare</strong></span><span class="sxs-lookup"><span data-stu-id="a5d18-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d18-132">po'</span><span class="sxs-lookup"><span data-stu-id="a5d18-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d18-p103">Può essere TRUE o NULL. Se TRUE, allora Reject e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="a5d18-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d18-135"><strong>Rifiuta</strong></span><span class="sxs-lookup"><span data-stu-id="a5d18-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d18-136">po'</span><span class="sxs-lookup"><span data-stu-id="a5d18-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d18-p104">Può essere TRUE o NULL. Se TRUE, allora Accept e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="a5d18-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d18-139"><strong>Annulla</strong></span><span class="sxs-lookup"><span data-stu-id="a5d18-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d18-140">po'</span><span class="sxs-lookup"><span data-stu-id="a5d18-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d18-p105">Può essere TRUE o NULL. Se TRUE, allora Accept e Reject saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="a5d18-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

