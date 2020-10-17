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
ms.openlocfilehash: e0fdfae0cefafc7ee6273af75e84e0ea6545188b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500873"
---
# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="1b852-102">Visualizzazione FileTransfers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b852-102">FileTransfers view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b852-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1b852-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1b852-104">La visualizzazione filetransfer archivia le informazioni sulle sessioni di trasferimento file peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="1b852-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="1b852-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b852-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b852-106">La Visualizzazione FileTransfers contiene tutte le colonne della <A href="lync-server-2013-sessiondetails-view.md">Visualizzazione SessionDetails in Lync Server 2013</A> , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="1b852-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b852-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="1b852-107">Column</span></span></th>
<th><span data-ttu-id="1b852-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1b852-108">Data Type</span></span></th>
<th><span data-ttu-id="1b852-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1b852-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b852-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="1b852-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="1b852-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1b852-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1b852-112">Nome del file trasferito.</span><span class="sxs-lookup"><span data-stu-id="1b852-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b852-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="1b852-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="1b852-114">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="1b852-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="1b852-115">Valore utilizzato per identificare ogni messaggio successivo come associato a questo.</span><span class="sxs-lookup"><span data-stu-id="1b852-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b852-116"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="1b852-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b852-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="1b852-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1b852-118">Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome di file.</span><span class="sxs-lookup"><span data-stu-id="1b852-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b852-119"><strong>Accettare</strong></span><span class="sxs-lookup"><span data-stu-id="1b852-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="1b852-120">po'</span><span class="sxs-lookup"><span data-stu-id="1b852-120">bit</span></span></p></td>
<td><p><span data-ttu-id="1b852-p102">Può essere TRUE o NULL. Se TRUE, allora Reject e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="1b852-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b852-123"><strong>Rifiuta</strong></span><span class="sxs-lookup"><span data-stu-id="1b852-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="1b852-124">po'</span><span class="sxs-lookup"><span data-stu-id="1b852-124">bit</span></span></p></td>
<td><p><span data-ttu-id="1b852-p103">Può essere TRUE o NULL. Se TRUE, allora Accept e Cancel saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="1b852-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b852-127"><strong>Annulla</strong></span><span class="sxs-lookup"><span data-stu-id="1b852-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="1b852-128">po'</span><span class="sxs-lookup"><span data-stu-id="1b852-128">bit</span></span></p></td>
<td><p><span data-ttu-id="1b852-p104">Può essere TRUE o NULL. Se TRUE, allora Accept e Reject saranno NULL.</span><span class="sxs-lookup"><span data-stu-id="1b852-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

