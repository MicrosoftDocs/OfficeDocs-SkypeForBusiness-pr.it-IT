---
title: 'Lync Server 2013: Tabella Media'
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
ms.openlocfilehash: 69f9ad10c5c06ab8a9d2bc95eddceb67b20e745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="71c6b-102">Tabella Media in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71c6b-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71c6b-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="71c6b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="71c6b-104">Ogni record rappresenta un tipo di elemento multimediale usato in una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="71c6b-104">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="71c6b-105">Una sessione verrebbe rappresentata da più record nella tabella, se viene usato più di un tipo di elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="71c6b-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="71c6b-106">La tabella multimediale non deve essere usata per calcolare la durata del supporto per una sessione.</span><span class="sxs-lookup"><span data-stu-id="71c6b-106">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="71c6b-107">Questa tabella contiene i dettagli di segnalazione dello scambio multimediale in una sessione.</span><span class="sxs-lookup"><span data-stu-id="71c6b-107">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="71c6b-108">Lo scambio multimediale viene eseguito dalla richiesta di invito e StartTime indica l'ora in cui è stato inviato l'invito. Il tempo di invito non significa necessariamente l'ora di inizio dell'elemento multimediale, perché il supporto viene avviato solo dopo che la sessione viene accettata.</span><span class="sxs-lookup"><span data-stu-id="71c6b-108">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="71c6b-109">Il EndTime in genere indica l'ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="71c6b-109">The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="71c6b-110">Colonna</span><span class="sxs-lookup"><span data-stu-id="71c6b-110">Column</span></span></th>
<th><span data-ttu-id="71c6b-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="71c6b-111">Data Type</span></span></th>
<th><span data-ttu-id="71c6b-112">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="71c6b-112">Key/Index</span></span></th>
<th><span data-ttu-id="71c6b-113">Dettagli</span><span class="sxs-lookup"><span data-stu-id="71c6b-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71c6b-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="71c6b-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71c6b-115">DateTime</span><span class="sxs-lookup"><span data-stu-id="71c6b-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="71c6b-116">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="71c6b-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="71c6b-117">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="71c6b-117">Time of session request.</span></span> <span data-ttu-id="71c6b-118">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="71c6b-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="71c6b-119">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71c6b-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c6b-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="71c6b-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="71c6b-121">int</span><span class="sxs-lookup"><span data-stu-id="71c6b-121">int</span></span></p></td>
<td><p><span data-ttu-id="71c6b-122">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="71c6b-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="71c6b-123">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="71c6b-123">ID number to identify the session.</span></span> <span data-ttu-id="71c6b-124">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="71c6b-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="71c6b-125">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71c6b-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c6b-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="71c6b-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="71c6b-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="71c6b-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71c6b-128">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="71c6b-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="71c6b-129">Numero univoco che identifica questo tipo di elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="71c6b-129">Unique number identifying this media type.</span></span> <span data-ttu-id="71c6b-130">Per altre informazioni, vedere la <a href="lync-server-2013-medialist-table.md">tabella degli elementi multimediali in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="71c6b-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c6b-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="71c6b-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71c6b-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="71c6b-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="71c6b-133">Principale</span><span class="sxs-lookup"><span data-stu-id="71c6b-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="71c6b-134">Questo è il momento in cui è stata inviata una richiesta multimediale, non l'ora di inizio del media reale.</span><span class="sxs-lookup"><span data-stu-id="71c6b-134">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="71c6b-135"><strong>StartTime</strong> include il tempo di configurazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="71c6b-135"><strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c6b-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="71c6b-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71c6b-137">DateTime</span><span class="sxs-lookup"><span data-stu-id="71c6b-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71c6b-138">Questa è l'ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="71c6b-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

