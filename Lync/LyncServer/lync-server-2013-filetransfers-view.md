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
ms.openlocfilehash: 95cc6790766d68ee478cf1b80326c974f7c15f1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="696e3-102">Visualizzazione FileTransfers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="696e3-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="696e3-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="696e3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="696e3-104">La visualizzazione filetransfer archivia le informazioni sulle sessioni di trasferimento file peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="696e3-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="696e3-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="696e3-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="696e3-106">La Visualizzazione FileTransfers contiene tutte le colonne della <A href="lync-server-2013-sessiondetails-view.md">Visualizzazione SessionDetails in Lync Server 2013</A> , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="696e3-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="696e3-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="696e3-107">Column</span></span></th>
<th><span data-ttu-id="696e3-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="696e3-108">Data Type</span></span></th>
<th><span data-ttu-id="696e3-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="696e3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="696e3-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="696e3-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="696e3-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="696e3-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="696e3-112">Nome del file trasferito.</span><span class="sxs-lookup"><span data-stu-id="696e3-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="696e3-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="696e3-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="696e3-114">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="696e3-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="696e3-115">Valore utilizzato per identificare ogni messaggio successivo come associato a questo.</span><span class="sxs-lookup"><span data-stu-id="696e3-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="696e3-116"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="696e3-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="696e3-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="696e3-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="696e3-118">Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome di file.</span><span class="sxs-lookup"><span data-stu-id="696e3-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="696e3-119"><strong>Accettare</strong></span><span class="sxs-lookup"><span data-stu-id="696e3-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="696e3-120">po'</span><span class="sxs-lookup"><span data-stu-id="696e3-120">bit</span></span></p></td>
<td><p><span data-ttu-id="696e3-p102">Può essere TRUE o NULL. Se TRUE, allora Reject e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="696e3-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="696e3-123"><strong>Rifiuta</strong></span><span class="sxs-lookup"><span data-stu-id="696e3-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="696e3-124">po'</span><span class="sxs-lookup"><span data-stu-id="696e3-124">bit</span></span></p></td>
<td><p><span data-ttu-id="696e3-p103">Può essere TRUE o NULL. Se TRUE, allora Accept e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="696e3-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="696e3-127"><strong>Annulla</strong></span><span class="sxs-lookup"><span data-stu-id="696e3-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="696e3-128">po'</span><span class="sxs-lookup"><span data-stu-id="696e3-128">bit</span></span></p></td>
<td><p><span data-ttu-id="696e3-p104">Può essere TRUE o NULL. Se TRUE, allora Accept e Reject saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="696e3-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

