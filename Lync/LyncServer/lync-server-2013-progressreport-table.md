---
title: 'Lync Server 2013: Tabella ProgressReport'
description: 'Lync Server 2013: Tabella ProgressReport.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d36ee2ab75410ea2462da4b647ef5b45afefb1bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579822"
---
# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="247fd-103">Tabella ProgressReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="247fd-103">ProgressReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="247fd-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="247fd-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="247fd-105">I rapporti sullo stato sono basati sui dati caricati dal client nel database al termine di una chiamata o di una sessione.</span><span class="sxs-lookup"><span data-stu-id="247fd-105">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="247fd-106">Tali rapporti sullo stato verranno scritti solo per le chiamate e le sessioni ritenute utili da Lync Server 2013 a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="247fd-106">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="247fd-107">I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non fanno riferimento necessariamente a errori, bensì a messaggi in cui viene indicato lo stato delle chiamate o dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="247fd-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="247fd-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="247fd-108">Column</span></span></th>
<th><span data-ttu-id="247fd-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="247fd-109">Data Type</span></span></th>
<th><span data-ttu-id="247fd-110">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="247fd-110">Key/Index</span></span></th>
<th><span data-ttu-id="247fd-111">Dettagli</span><span class="sxs-lookup"><span data-stu-id="247fd-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="247fd-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="247fd-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="247fd-113">datetime</span><span class="sxs-lookup"><span data-stu-id="247fd-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="247fd-114">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="247fd-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="247fd-115">Data e ora della segnalazione degli errori di stato inclusa nel rapporto sullo stato.</span><span class="sxs-lookup"><span data-stu-id="247fd-115">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="247fd-116">Per ulteriori informazioni, vedere la <a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="247fd-116">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="247fd-117"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="247fd-117"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="247fd-118">int</span><span class="sxs-lookup"><span data-stu-id="247fd-118">int</span></span></p></td>
<td><p><span data-ttu-id="247fd-119">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="247fd-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="247fd-120">Numero ID utilizzato insieme a ErrorTime e ProgressReportSeq per identificare in modo univoco un rapporto sullo stato.</span><span class="sxs-lookup"><span data-stu-id="247fd-120">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="247fd-121">Per ulteriori informazioni, vedere la <a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="247fd-121">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="247fd-122"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="247fd-122"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="247fd-123">int</span><span class="sxs-lookup"><span data-stu-id="247fd-123">int</span></span></p></td>
<td><p><span data-ttu-id="247fd-124">Primaria/o, esterna/o</span><span class="sxs-lookup"><span data-stu-id="247fd-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="247fd-125">Numero ID che identifica la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="247fd-125">ID number that identifies the error report.</span></span> <span data-ttu-id="247fd-126">ErrorReporSeq viene utilizzato insieme a ErrorTime per identificare in modo univoco un rapporto di errore.</span><span class="sxs-lookup"><span data-stu-id="247fd-126">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="247fd-127">Per ulteriori informazioni, vedere la <a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="247fd-127">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="247fd-128">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="247fd-128">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="247fd-129"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="247fd-129"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="247fd-130">int</span><span class="sxs-lookup"><span data-stu-id="247fd-130">int</span></span></p></td>
<td><p><span data-ttu-id="247fd-131">Principale</span><span class="sxs-lookup"><span data-stu-id="247fd-131">Primary</span></span></p></td>
<td><p><span data-ttu-id="247fd-p105">Numero ID per identificare il rapporto sullo stato. Utilizzato insieme a ErrorTime ed ErrorReportSeq per identificare in modo univoco un rapporto sullo stato.</span><span class="sxs-lookup"><span data-stu-id="247fd-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="247fd-134"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="247fd-134"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="247fd-135">int</span><span class="sxs-lookup"><span data-stu-id="247fd-135">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="247fd-136">ID diagnostica del rapporto sullo stato.</span><span class="sxs-lookup"><span data-stu-id="247fd-136">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="247fd-137">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="247fd-137">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="247fd-138"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="247fd-138"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="247fd-139">int</span><span class="sxs-lookup"><span data-stu-id="247fd-139">int</span></span></p></td>
<td><p><span data-ttu-id="247fd-140">Stranieri</span><span class="sxs-lookup"><span data-stu-id="247fd-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="247fd-141">Server che ha inviato la segnalazione errori (se il rapporto è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="247fd-141">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="247fd-142">Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> . Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="247fd-142">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="247fd-143"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="247fd-143"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="247fd-144">int</span><span class="sxs-lookup"><span data-stu-id="247fd-144">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="247fd-p107">Processo di Lync Server a cui fa riferimento il rapporto. Per ulteriori informazioni, vedere la tabella Application.</span><span class="sxs-lookup"><span data-stu-id="247fd-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="247fd-147"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="247fd-147"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="247fd-148">immagine</span><span class="sxs-lookup"><span data-stu-id="247fd-148">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="247fd-149">Dettagli del rapporto sullo stato archiviati in formato binario per non occupare troppo spazio. I dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="247fd-149">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="247fd-150">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="247fd-150">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="247fd-151"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="247fd-151"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="247fd-152">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="247fd-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="247fd-153">Identificatore univoco che correla informazioni relative al tempo di partecipazione per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="247fd-153">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="247fd-154">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="247fd-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="247fd-155"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="247fd-155"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="247fd-156">int</span><span class="sxs-lookup"><span data-stu-id="247fd-156">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="247fd-157">Tempo (in millisecondi) necessario per un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="247fd-157">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="247fd-158">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="247fd-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

