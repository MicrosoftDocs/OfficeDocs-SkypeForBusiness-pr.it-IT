---
title: 'Lync Server 2013: Tabella Dialogs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a25ae1d298f1cf5908c4669a78485491fadd617d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="957c1-102">Tabella Dialogs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957c1-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="957c1-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="957c1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="957c1-104">La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni su DialogIDs per le sessioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="957c1-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="957c1-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="957c1-105">Column</span></span></th>
<th><span data-ttu-id="957c1-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="957c1-106">Data Type</span></span></th>
<th><span data-ttu-id="957c1-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="957c1-107">Key/Index</span></span></th>
<th><span data-ttu-id="957c1-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="957c1-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="957c1-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="957c1-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="957c1-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="957c1-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="957c1-111">Principale</span><span class="sxs-lookup"><span data-stu-id="957c1-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="957c1-112">Ora della richiesta di sessione; usato in combinazione con SessionIDSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="957c1-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="957c1-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="957c1-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="957c1-114">int</span><span class="sxs-lookup"><span data-stu-id="957c1-114">int</span></span></p></td>
<td><p><span data-ttu-id="957c1-115">Principale</span><span class="sxs-lookup"><span data-stu-id="957c1-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="957c1-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="957c1-116">ID number to identify the session.</span></span> <span data-ttu-id="957c1-117">Usato in combinazione con SessionIDTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="957c1-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="957c1-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="957c1-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="957c1-119">int</span><span class="sxs-lookup"><span data-stu-id="957c1-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="957c1-120">Checksum della ExternalID.</span><span class="sxs-lookup"><span data-stu-id="957c1-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="957c1-121">Questo campo viene usato per aumentare la velocità delle ricerche di database.</span><span class="sxs-lookup"><span data-stu-id="957c1-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="957c1-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="957c1-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="957c1-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="957c1-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="957c1-124">ID finestra di dialogo SIP, archiviato come binario.</span><span class="sxs-lookup"><span data-stu-id="957c1-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="957c1-125">Il formato del file binario è:</span><span class="sxs-lookup"><span data-stu-id="957c1-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="957c1-126">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="957c1-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="957c1-127">Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="957c1-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

