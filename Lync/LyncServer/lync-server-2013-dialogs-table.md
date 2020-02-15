---
title: 'Lync Server 2013: tabella Dialogs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be0bb5a603f856aa0faa02074962618fcb82448e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="4ac17-102">Tabella Dialogs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ac17-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ac17-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4ac17-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4ac17-104">La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni relative a DialogIDs per le sessioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="4ac17-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ac17-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="4ac17-105">Column</span></span></th>
<th><span data-ttu-id="4ac17-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4ac17-106">Data Type</span></span></th>
<th><span data-ttu-id="4ac17-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="4ac17-107">Key/Index</span></span></th>
<th><span data-ttu-id="4ac17-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4ac17-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ac17-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4ac17-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4ac17-110">datetime</span><span class="sxs-lookup"><span data-stu-id="4ac17-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ac17-111">Principale</span><span class="sxs-lookup"><span data-stu-id="4ac17-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="4ac17-112">Ora della richiesta di sessione; utilizzato insieme a SessionIDSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="4ac17-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ac17-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4ac17-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4ac17-114">int</span><span class="sxs-lookup"><span data-stu-id="4ac17-114">int</span></span></p></td>
<td><p><span data-ttu-id="4ac17-115">Principale</span><span class="sxs-lookup"><span data-stu-id="4ac17-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="4ac17-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="4ac17-116">ID number to identify the session.</span></span> <span data-ttu-id="4ac17-117">Utilizzato insieme a SessionIDTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="4ac17-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ac17-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="4ac17-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="4ac17-119">int</span><span class="sxs-lookup"><span data-stu-id="4ac17-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ac17-120">Checksum del ExternalID.</span><span class="sxs-lookup"><span data-stu-id="4ac17-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="4ac17-121">Questo campo viene utilizzato per aumentare la velocità delle ricerche di database.</span><span class="sxs-lookup"><span data-stu-id="4ac17-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ac17-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="4ac17-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ac17-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="4ac17-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4ac17-124">ID finestra di dialogo SIP, memorizzato come binario.</span><span class="sxs-lookup"><span data-stu-id="4ac17-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="4ac17-125">Il formato del file binario è:</span><span class="sxs-lookup"><span data-stu-id="4ac17-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="4ac17-126">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="4ac17-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="4ac17-127">Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="4ac17-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

