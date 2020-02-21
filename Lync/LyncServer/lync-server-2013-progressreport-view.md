---
title: 'Lync Server 2013: Visualizzazione ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac09e1b22e4807b039daf4b5da4778a54cb91d4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="44204-102">Visualizzazione ProgressReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44204-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44204-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="44204-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="44204-104">Nella visualizzazione ProgressReport vengono archiviate le informazioni relative alle sessioni completate.</span><span class="sxs-lookup"><span data-stu-id="44204-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="44204-105">Tali rapporti sullo stato verranno scritti solo per le chiamate e le sessioni ritenute utili da Lync Server 2013 a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="44204-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="44204-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="44204-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44204-107">I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non fanno riferimento necessariamente a errori, bensì a messaggi in cui viene indicato lo stato delle chiamate o dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="44204-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44204-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="44204-108">Column</span></span></th>
<th><span data-ttu-id="44204-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="44204-109">Data Type</span></span></th>
<th><span data-ttu-id="44204-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="44204-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44204-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="44204-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="44204-112">datetime</span><span class="sxs-lookup"><span data-stu-id="44204-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="44204-p102">Data/ora in cui si è verificato l'errore. Valore utilizzato con ErrorReportSeq per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="44204-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44204-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="44204-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="44204-116">int</span><span class="sxs-lookup"><span data-stu-id="44204-116">int</span></span></p></td>
<td><p><span data-ttu-id="44204-p103">ID che identifica l'errore. Questo valore viene utilizzato insieme a ErrorTime per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="44204-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44204-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="44204-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="44204-120">int</span><span class="sxs-lookup"><span data-stu-id="44204-120">int</span></span></p></td>
<td><p><span data-ttu-id="44204-121">ID che identifica il rapporto sullo stato.</span><span class="sxs-lookup"><span data-stu-id="44204-121">ID to identify the progress report.</span></span> <span data-ttu-id="44204-122">Questo valore viene utilizzato per distinguere i rapporti sullo stato della stessa segnalazione di errore.</span><span class="sxs-lookup"><span data-stu-id="44204-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44204-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="44204-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="44204-124">int</span><span class="sxs-lookup"><span data-stu-id="44204-124">int</span></span></p></td>
<td><p><span data-ttu-id="44204-125">ID diagnostica della segnalazione di errore.</span><span class="sxs-lookup"><span data-stu-id="44204-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44204-126"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="44204-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="44204-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="44204-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="44204-128">Nome del server che ha dato origine all'errore (se il rapporto è stato inviato da un componente del server).</span><span class="sxs-lookup"><span data-stu-id="44204-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44204-129"><strong>Applicazione</strong></span><span class="sxs-lookup"><span data-stu-id="44204-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="44204-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="44204-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="44204-131">Nome dell'applicazione da cui ha avuto origine l'errore (se la segnalazione è stata inviata da un componente server).</span><span class="sxs-lookup"><span data-stu-id="44204-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44204-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="44204-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="44204-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="44204-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="44204-134">Identificatore univoco di correlazione delle informazioni sul tempo di partecipazione per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="44204-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44204-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="44204-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="44204-136">int</span><span class="sxs-lookup"><span data-stu-id="44204-136">int</span></span></p></td>
<td><p><span data-ttu-id="44204-137">Intervallo di tempo, in millisecondi, necessario a un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="44204-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44204-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="44204-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="44204-139">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="44204-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="44204-140">Ulteriori informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="44204-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

