---
title: 'Lync Server 2013: Visualizzazione FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4469140f7f92c563a594c883d02f3add1e65c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="16bb5-102">Visualizzazione FileTransfers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16bb5-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16bb5-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="16bb5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="16bb5-104">La visualizzazione filetransfer consente di archiviare informazioni sulle sessioni di trasferimento di file peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="16bb5-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="16bb5-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="16bb5-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="16bb5-106">La Visualizzazione FileTransfers contiene tutte le colonne della <A href="lync-server-2013-sessiondetails-view.md">Visualizzazione SessionDetails in Lync Server 2013</A> , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="16bb5-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16bb5-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="16bb5-107">Column</span></span></th>
<th><span data-ttu-id="16bb5-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="16bb5-108">Data Type</span></span></th>
<th><span data-ttu-id="16bb5-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="16bb5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16bb5-110"><strong>Nome file</strong></span><span class="sxs-lookup"><span data-stu-id="16bb5-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="16bb5-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="16bb5-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16bb5-112">Nome del file trasferito.</span><span class="sxs-lookup"><span data-stu-id="16bb5-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16bb5-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="16bb5-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="16bb5-114">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="16bb5-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="16bb5-115">Usato per identificare ogni messaggio di follow-up associato a questo.</span><span class="sxs-lookup"><span data-stu-id="16bb5-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16bb5-116"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="16bb5-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="16bb5-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="16bb5-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="16bb5-118">Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome file.</span><span class="sxs-lookup"><span data-stu-id="16bb5-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16bb5-119"><strong>Accettare</strong></span><span class="sxs-lookup"><span data-stu-id="16bb5-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="16bb5-120">po'</span><span class="sxs-lookup"><span data-stu-id="16bb5-120">bit</span></span></p></td>
<td><p><span data-ttu-id="16bb5-121">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="16bb5-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="16bb5-122">Se TRUE, quindi Reject e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="16bb5-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16bb5-123"><strong>Rifiutare</strong></span><span class="sxs-lookup"><span data-stu-id="16bb5-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="16bb5-124">po'</span><span class="sxs-lookup"><span data-stu-id="16bb5-124">bit</span></span></p></td>
<td><p><span data-ttu-id="16bb5-125">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="16bb5-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="16bb5-126">Se TRUE, accetta e Annulla sarà NULL.</span><span class="sxs-lookup"><span data-stu-id="16bb5-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16bb5-127"><strong>Annulla</strong></span><span class="sxs-lookup"><span data-stu-id="16bb5-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="16bb5-128">po'</span><span class="sxs-lookup"><span data-stu-id="16bb5-128">bit</span></span></p></td>
<td><p><span data-ttu-id="16bb5-129">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="16bb5-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="16bb5-130">Se TRUE, accetta e rifiuta sarà NULL.</span><span class="sxs-lookup"><span data-stu-id="16bb5-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

