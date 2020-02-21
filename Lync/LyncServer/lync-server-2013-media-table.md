---
title: 'Lync Server 2013: tabella multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c833ab255741b6a2f28ce9d72f46226c42baea3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="965a0-102">Tabella multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="965a0-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="965a0-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="965a0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="965a0-p101">Ogni record rappresenta un tipo di supporto multimediale utilizzato in una sessione peer-to-peer. Una sessione viene rappresentata da più record nella tabella se viene utilizzato più di un tipo di supporto multimediale.</span><span class="sxs-lookup"><span data-stu-id="965a0-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="965a0-p102">Non utilizzare la tabella Media per calcolare la durata media di una sessione. Questa tabella contiene i dettagli di segnalazione dello scambio multimediale in una sessione. Lo scambio multimediale viene eseguito dalla richiesta INVITE e StartTime indica l'ora di invio di tale richiesta. L'ora di invito non corrisponde necessariamente all'ora di inizio dello scambio multimediale, poiché questo inizia solo dopo che il destinatario ha accettato la sessione. EndTime in genere indica l'ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="965a0-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="965a0-110">Colonna</span><span class="sxs-lookup"><span data-stu-id="965a0-110">Column</span></span></th>
<th><span data-ttu-id="965a0-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="965a0-111">Data Type</span></span></th>
<th><span data-ttu-id="965a0-112">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="965a0-112">Key/Index</span></span></th>
<th><span data-ttu-id="965a0-113">Dettagli</span><span class="sxs-lookup"><span data-stu-id="965a0-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="965a0-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="965a0-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="965a0-115">datetime</span><span class="sxs-lookup"><span data-stu-id="965a0-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="965a0-116">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="965a0-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="965a0-117">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="965a0-117">Time of session request.</span></span> <span data-ttu-id="965a0-118">Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="965a0-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="965a0-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="965a0-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="965a0-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="965a0-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="965a0-121">int</span><span class="sxs-lookup"><span data-stu-id="965a0-121">int</span></span></p></td>
<td><p><span data-ttu-id="965a0-122">Primario, esterno</span><span class="sxs-lookup"><span data-stu-id="965a0-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="965a0-123">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="965a0-123">ID number to identify the session.</span></span> <span data-ttu-id="965a0-124">Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="965a0-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="965a0-125">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="965a0-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="965a0-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="965a0-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="965a0-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="965a0-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="965a0-128">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="965a0-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="965a0-129">Numero univoco che identifica il tipo di elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="965a0-129">Unique number identifying this media type.</span></span> <span data-ttu-id="965a0-130">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialist-table.md">tabella degli elementi multimediali in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="965a0-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="965a0-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="965a0-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="965a0-132">datetime</span><span class="sxs-lookup"><span data-stu-id="965a0-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="965a0-133">Principale</span><span class="sxs-lookup"><span data-stu-id="965a0-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="965a0-p106">Indica l'ora di invio di una richiesta di scambio multimediale e non l'ora di inizio dello scambio multimediale effettivo. <strong>StartTime </strong> include il tempo di configurazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="965a0-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="965a0-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="965a0-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="965a0-137">datetime</span><span class="sxs-lookup"><span data-stu-id="965a0-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="965a0-138">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="965a0-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

