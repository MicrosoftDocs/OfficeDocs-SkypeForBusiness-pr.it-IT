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
ms.openlocfilehash: f2b96e0c8bba14e58e6d800b5c5634a5a655ef35
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="f5e1e-102">Visualizzazione ProgressReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5e1e-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5e1e-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f5e1e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f5e1e-104">Nella visualizzazione ProgressReport vengono archiviate le informazioni relative alle sessioni completate.</span><span class="sxs-lookup"><span data-stu-id="f5e1e-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="f5e1e-105">Tali rapporti sullo stato verranno scritti solo per le chiamate e le sessioni ritenute utili da Lync Server 2013 a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="f5e1e-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="f5e1e-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5e1e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5e1e-107">I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non fanno riferimento necessariamente a errori, bensì a messaggi in cui viene indicato lo stato delle chiamate o dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="f5e1e-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5e1e-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="f5e1e-108">Column</span></span></th>
<th><span data-ttu-id="f5e1e-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f5e1e-109">Data Type</span></span></th>
<th><span data-ttu-id="f5e1e-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f5e1e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5e1e-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="f5e1e-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f5e1e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f5e1e-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f5e1e-p102">Data/ora in cui si è verificato l'errore. Valore utilizzato con ErrorReportSeq per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="f5e1e-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5e1e-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f5e1e-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f5e1e-116">int</span><span class="sxs-lookup"><span data-stu-id="f5e1e-116">int</span></span></p></td>
<td><p><span data-ttu-id="f5e1e-p103">ID che identifica l'errore. Questo valore viene utilizzato insieme a ErrorTime per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="f5e1e-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5e1e-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f5e1e-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f5e1e-120">int</span><span class="sxs-lookup"><span data-stu-id="f5e1e-120">int</span></span></p></td>
<td><p><span data-ttu-id="f5e1e-121">ID che identifica il rapporto sullo stato.</span><span class="sxs-lookup"><span data-stu-id="f5e1e-121">ID to identify the progress report.</span></span> <span data-ttu-id="f5e1e-122">Questo valore viene utilizzato per distinguere i rapporti sullo stato della stessa segnalazione di errore.</span><span class="sxs-lookup"><span data-stu-id="f5e1e-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5e1e-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="f5e1e-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="f5e1e-124">int</span><span class="sxs-lookup"><span data-stu-id="f5e1e-124">int</span></span></p></td>
<td><p><span data-ttu-id="f5e1e-125">ID diagnostica della segnalazione di errore.</span><span class="sxs-lookup"><span data-stu-id="f5e1e-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5e1e-126"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="f5e1e-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="f5e1e-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5e1e-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5e1e-128">Nome del server che ha dato origine all'errore (se il rapporto è stato inviato da un componente del server).</span><span class="sxs-lookup"><span data-stu-id="f5e1e-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5e1e-129"><strong>Applicazione</strong></span><span class="sxs-lookup"><span data-stu-id="f5e1e-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="f5e1e-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5e1e-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5e1e-131">Nome dell'applicazione da cui ha avuto origine l'errore (se la segnalazione è stata inviata da un componente server).</span><span class="sxs-lookup"><span data-stu-id="f5e1e-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5e1e-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="f5e1e-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="f5e1e-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="f5e1e-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f5e1e-134">Identificatore univoco di correlazione delle informazioni sul tempo di partecipazione per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="f5e1e-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5e1e-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="f5e1e-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f5e1e-136">int</span><span class="sxs-lookup"><span data-stu-id="f5e1e-136">int</span></span></p></td>
<td><p><span data-ttu-id="f5e1e-137">Intervallo di tempo, in millisecondi, necessario a un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="f5e1e-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5e1e-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="f5e1e-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="f5e1e-139">varchar (massimo)</span><span class="sxs-lookup"><span data-stu-id="f5e1e-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="f5e1e-140">Ulteriori informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="f5e1e-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

