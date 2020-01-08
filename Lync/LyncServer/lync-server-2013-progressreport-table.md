---
title: 'Lync Server 2013: Tabella ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8ca0341cd5b85418ef5f71234870ae4171af27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="a9ef1-102">Tabella ProgressReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9ef1-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9ef1-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a9ef1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a9ef1-104">I report sullo stato di avanzamento si basano sui dati caricati dal client nel database dopo il completamento di una chiamata o di una sessione.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="a9ef1-105">I report sullo stato di avanzamento verranno scritti solo per le chiamate e le sessioni che Lync Server 2013 determina può essere utile per scopi diagnostici.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="a9ef1-106">I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non si riferiscono necessariamente agli errori, ma ai messaggi che indicano lo stato delle chiamate o dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9ef1-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="a9ef1-107">Column</span></span></th>
<th><span data-ttu-id="a9ef1-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a9ef1-108">Data Type</span></span></th>
<th><span data-ttu-id="a9ef1-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="a9ef1-109">Key/Index</span></span></th>
<th><span data-ttu-id="a9ef1-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a9ef1-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9ef1-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="a9ef1-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a9ef1-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="a9ef1-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="a9ef1-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="a9ef1-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a9ef1-114">Data e ora del report sugli errori di stato che contiene il report sullo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="a9ef1-115">Per altre informazioni, vedere la <a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a9ef1-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9ef1-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="a9ef1-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="a9ef1-117">int</span><span class="sxs-lookup"><span data-stu-id="a9ef1-117">int</span></span></p></td>
<td><p><span data-ttu-id="a9ef1-118">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="a9ef1-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a9ef1-119">Numero ID usato in combinazione con ErrorTime, ProgressReportSeq per identificare in modo univoco un report di stato.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="a9ef1-120">Per altre informazioni, vedere la <a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a9ef1-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9ef1-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a9ef1-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a9ef1-122">int</span><span class="sxs-lookup"><span data-stu-id="a9ef1-122">int</span></span></p></td>
<td><p><span data-ttu-id="a9ef1-123">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="a9ef1-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a9ef1-124">Numero ID che identifica il report degli errori.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-124">ID number that identifies the error report.</span></span> <span data-ttu-id="a9ef1-125">ErrorReporSeq viene usato in combinazione con ErrorTime per identificare in modo univoco una segnalazione di errori.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="a9ef1-126">Per altre informazioni, vedere la <a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a9ef1-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="a9ef1-127">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9ef1-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a9ef1-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a9ef1-129">int</span><span class="sxs-lookup"><span data-stu-id="a9ef1-129">int</span></span></p></td>
<td><p><span data-ttu-id="a9ef1-130">Principale</span><span class="sxs-lookup"><span data-stu-id="a9ef1-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="a9ef1-131">Numero ID per identificare il rapporto di stato.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-131">ID number to identify the progress report.</span></span> <span data-ttu-id="a9ef1-132">Usato in combinazione con ErrorTime e ErrorReportSeq per identificare in modo univoco un report di stato.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-132">Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9ef1-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="a9ef1-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="a9ef1-134">int</span><span class="sxs-lookup"><span data-stu-id="a9ef1-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a9ef1-135">ID di diagnostica del report sullo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="a9ef1-136">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9ef1-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="a9ef1-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="a9ef1-138">int</span><span class="sxs-lookup"><span data-stu-id="a9ef1-138">int</span></span></p></td>
<td><p><span data-ttu-id="a9ef1-139">Esterna</span><span class="sxs-lookup"><span data-stu-id="a9ef1-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a9ef1-140">Server che ha inviato il report degli errori (se il report è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="a9ef1-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="a9ef1-141">Per altre informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella server in Lync server 2013</a> . Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9ef1-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="a9ef1-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="a9ef1-143">int</span><span class="sxs-lookup"><span data-stu-id="a9ef1-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a9ef1-144">Processo del server Lync in cui si trova il report.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-144">The Lync Server process that the report is about.</span></span> <span data-ttu-id="a9ef1-145">Per altre informazioni, vedere la tabella delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-145">See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9ef1-146"><strong>Dettaglio</strong></span><span class="sxs-lookup"><span data-stu-id="a9ef1-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="a9ef1-147">image</span><span class="sxs-lookup"><span data-stu-id="a9ef1-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a9ef1-148">Dettagli del report sullo stato di avanzamento, archiviati in formato binario per risparmiare spazio. Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a9ef1-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="a9ef1-149">Cast (cast (dettaglio come varbinary (max)) come varchar (max))</span><span class="sxs-lookup"><span data-stu-id="a9ef1-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9ef1-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="a9ef1-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="a9ef1-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="a9ef1-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a9ef1-152">Identificatore univoco che correla le informazioni sull'ora di join per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="a9ef1-153">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9ef1-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="a9ef1-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a9ef1-155">int</span><span class="sxs-lookup"><span data-stu-id="a9ef1-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a9ef1-156">Ora (in millisecondi) per un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="a9ef1-157">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9ef1-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

