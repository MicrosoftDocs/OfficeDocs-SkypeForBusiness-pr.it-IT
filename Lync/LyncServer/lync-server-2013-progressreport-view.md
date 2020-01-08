---
title: 'Lync Server 2013: Visualizzazione ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 423d99211a89ef328bc62aca89a9b65141e128ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="c5fb3-102">Visualizzazione ProgressReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5fb3-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5fb3-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c5fb3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c5fb3-104">La Visualizzazione ProgressReport archivia le informazioni sulle sessioni completate.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="c5fb3-105">I report sullo stato di avanzamento verranno scritti solo per le chiamate e le sessioni che Lync Server 2013 determina può essere utile per scopi diagnostici.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="c5fb3-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5fb3-107">I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non si riferiscono necessariamente agli errori, ma ai messaggi che indicano lo stato delle chiamate o dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5fb3-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="c5fb3-108">Column</span></span></th>
<th><span data-ttu-id="c5fb3-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c5fb3-109">Data Type</span></span></th>
<th><span data-ttu-id="c5fb3-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c5fb3-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5fb3-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5fb3-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fb3-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="c5fb3-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5fb3-113">Periodo di errore.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-113">Time of error occurred.</span></span> <span data-ttu-id="c5fb3-114">Usato in combinazione con ErrorReportSeq per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fb3-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c5fb3-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fb3-116">int</span><span class="sxs-lookup"><span data-stu-id="c5fb3-116">int</span></span></p></td>
<td><p><span data-ttu-id="c5fb3-117">Numero ID per identificare l'errore.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-117">ID number to identify the error.</span></span> <span data-ttu-id="c5fb3-118">Usato in combinazione con ErrorTime per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fb3-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c5fb3-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fb3-120">int</span><span class="sxs-lookup"><span data-stu-id="c5fb3-120">int</span></span></p></td>
<td><p><span data-ttu-id="c5fb3-121">ID per identificare il report di stato.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-121">ID to identify the progress report.</span></span> <span data-ttu-id="c5fb3-122">Usato per distinguere i report sullo stato dello stesso rapporto di errore.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fb3-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="c5fb3-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fb3-124">int</span><span class="sxs-lookup"><span data-stu-id="c5fb3-124">int</span></span></p></td>
<td><p><span data-ttu-id="c5fb3-125">ID di diagnostica per il report degli errori.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fb3-126"><strong>Fonte</strong></span><span class="sxs-lookup"><span data-stu-id="c5fb3-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fb3-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fb3-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fb3-128">Nome del server che ha originato l'errore (se il report è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="c5fb3-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fb3-129"><strong>Applicazione</strong></span><span class="sxs-lookup"><span data-stu-id="c5fb3-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fb3-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5fb3-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5fb3-131">Nome dell'applicazione che ha originato l'errore (se il report è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="c5fb3-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fb3-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="c5fb3-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fb3-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c5fb3-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c5fb3-134">Identificatore univoco che correla le informazioni sul tempo di join per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5fb3-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5fb3-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fb3-136">int</span><span class="sxs-lookup"><span data-stu-id="c5fb3-136">int</span></span></p></td>
<td><p><span data-ttu-id="c5fb3-137">Ora (in millisecondi) necessaria per un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5fb3-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="c5fb3-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="c5fb3-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="c5fb3-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="c5fb3-140">Altre informazioni sugli errori.</span><span class="sxs-lookup"><span data-stu-id="c5fb3-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

