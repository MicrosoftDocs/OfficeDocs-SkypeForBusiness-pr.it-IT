---
title: 'Lync Server 2013: Visualizzazione FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4228bbe42f2e7bcf88b26f9147e514f09c106ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="38b15-102">Visualizzazione FileTransfers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38b15-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38b15-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="38b15-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="38b15-104">La visualizzazione filetransfer consente di archiviare informazioni sulle sessioni di trasferimento di file peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="38b15-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="38b15-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38b15-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="38b15-106">La Visualizzazione FileTransfers contiene tutte le colonne della <A href="lync-server-2013-sessiondetails-view.md">Visualizzazione SessionDetails in Lync Server 2013</A> , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="38b15-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38b15-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="38b15-107">Column</span></span></th>
<th><span data-ttu-id="38b15-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="38b15-108">Data Type</span></span></th>
<th><span data-ttu-id="38b15-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="38b15-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38b15-110"><strong>Nome file</strong></span><span class="sxs-lookup"><span data-stu-id="38b15-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="38b15-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="38b15-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="38b15-112">Nome del file trasferito.</span><span class="sxs-lookup"><span data-stu-id="38b15-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38b15-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="38b15-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="38b15-114">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="38b15-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="38b15-115">Usato per identificare ogni messaggio di follow-up associato a questo.</span><span class="sxs-lookup"><span data-stu-id="38b15-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38b15-116"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="38b15-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="38b15-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="38b15-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="38b15-118">Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome file.</span><span class="sxs-lookup"><span data-stu-id="38b15-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38b15-119"><strong>Accettare</strong></span><span class="sxs-lookup"><span data-stu-id="38b15-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="38b15-120">po'</span><span class="sxs-lookup"><span data-stu-id="38b15-120">bit</span></span></p></td>
<td><p><span data-ttu-id="38b15-121">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="38b15-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="38b15-122">Se TRUE, quindi Reject e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="38b15-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38b15-123"><strong>Rifiutare</strong></span><span class="sxs-lookup"><span data-stu-id="38b15-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="38b15-124">po'</span><span class="sxs-lookup"><span data-stu-id="38b15-124">bit</span></span></p></td>
<td><p><span data-ttu-id="38b15-125">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="38b15-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="38b15-126">Se TRUE, accetta e Annulla sarà NULL.</span><span class="sxs-lookup"><span data-stu-id="38b15-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38b15-127"><strong>Annulla</strong></span><span class="sxs-lookup"><span data-stu-id="38b15-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="38b15-128">po'</span><span class="sxs-lookup"><span data-stu-id="38b15-128">bit</span></span></p></td>
<td><p><span data-ttu-id="38b15-129">Può essere TRUE o NULL.</span><span class="sxs-lookup"><span data-stu-id="38b15-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="38b15-130">Se TRUE, accetta e rifiuta sarà NULL.</span><span class="sxs-lookup"><span data-stu-id="38b15-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

