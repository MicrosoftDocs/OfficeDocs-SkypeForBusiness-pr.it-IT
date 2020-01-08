---
title: 'Lync Server 2013: Tabella Media'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8b3aaff56e782307f3146fdcee7d4410340198
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="8efda-102">Tabella Media in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8efda-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8efda-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8efda-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8efda-104">Ogni record rappresenta un tipo di elemento multimediale usato in una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="8efda-104">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="8efda-105">Una sessione verrebbe rappresentata da più record nella tabella, se viene usato più di un tipo di elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="8efda-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8efda-106">La tabella multimediale non deve essere usata per calcolare la durata del supporto per una sessione.</span><span class="sxs-lookup"><span data-stu-id="8efda-106">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="8efda-107">Questa tabella contiene i dettagli di segnalazione dello scambio multimediale in una sessione.</span><span class="sxs-lookup"><span data-stu-id="8efda-107">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="8efda-108">Lo scambio multimediale viene eseguito dalla richiesta di invito e StartTime indica l'ora in cui è stato inviato l'invito. Il tempo di invito non significa necessariamente l'ora di inizio dell'elemento multimediale, perché il supporto viene avviato solo dopo che la sessione viene accettata.</span><span class="sxs-lookup"><span data-stu-id="8efda-108">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="8efda-109">Il EndTime in genere indica l'ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="8efda-109">The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="8efda-110">Colonna</span><span class="sxs-lookup"><span data-stu-id="8efda-110">Column</span></span></th>
<th><span data-ttu-id="8efda-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="8efda-111">Data Type</span></span></th>
<th><span data-ttu-id="8efda-112">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="8efda-112">Key/Index</span></span></th>
<th><span data-ttu-id="8efda-113">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8efda-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8efda-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8efda-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8efda-115">DateTime</span><span class="sxs-lookup"><span data-stu-id="8efda-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="8efda-116">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="8efda-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8efda-117">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="8efda-117">Time of session request.</span></span> <span data-ttu-id="8efda-118">Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="8efda-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8efda-119">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8efda-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8efda-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8efda-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8efda-121">int</span><span class="sxs-lookup"><span data-stu-id="8efda-121">int</span></span></p></td>
<td><p><span data-ttu-id="8efda-122">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="8efda-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8efda-123">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="8efda-123">ID number to identify the session.</span></span> <span data-ttu-id="8efda-124">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="8efda-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8efda-125">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8efda-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8efda-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="8efda-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="8efda-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="8efda-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8efda-128">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="8efda-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8efda-129">Numero univoco che identifica questo tipo di elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="8efda-129">Unique number identifying this media type.</span></span> <span data-ttu-id="8efda-130">Per altre informazioni, vedere la <a href="lync-server-2013-medialist-table.md">tabella degli elementi multimediali in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8efda-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8efda-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="8efda-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8efda-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="8efda-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="8efda-133">Principale</span><span class="sxs-lookup"><span data-stu-id="8efda-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="8efda-134">Questo è il momento in cui è stata inviata una richiesta multimediale, non l'ora di inizio del media reale.</span><span class="sxs-lookup"><span data-stu-id="8efda-134">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="8efda-135"><strong>StartTime</strong> include il tempo di configurazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="8efda-135"><strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8efda-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="8efda-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8efda-137">DateTime</span><span class="sxs-lookup"><span data-stu-id="8efda-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8efda-138">Questa è l'ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="8efda-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

