---
title: 'Lync Server 2013: Tabella ProgressReport'
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
ms.openlocfilehash: c92adf48a09f83c3c3dec18f91e4aadc3a3cbd39
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513233"
---
# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="ad2ad-102">Tabella ProgressReport in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad2ad-102">ProgressReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad2ad-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ad2ad-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ad2ad-104">I rapporti sullo stato sono basati sui dati caricati dal client nel database al termine di una chiamata o di una sessione.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="ad2ad-105">Tali rapporti sullo stato verranno scritti solo per le chiamate e le sessioni ritenute utili da Lync Server 2013 a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="ad2ad-106">I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non fanno riferimento necessariamente a errori, bensì a messaggi in cui viene indicato lo stato delle chiamate o dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad2ad-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="ad2ad-107">Column</span></span></th>
<th><span data-ttu-id="ad2ad-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ad2ad-108">Data Type</span></span></th>
<th><span data-ttu-id="ad2ad-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="ad2ad-109">Key/Index</span></span></th>
<th><span data-ttu-id="ad2ad-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ad2ad-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad2ad-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="ad2ad-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ad2ad-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ad2ad-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ad2ad-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="ad2ad-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ad2ad-114">Data e ora della segnalazione degli errori di stato inclusa nel rapporto sullo stato.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="ad2ad-115">Per ulteriori informazioni, vedere la <a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ad2ad-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad2ad-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="ad2ad-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="ad2ad-117">int</span><span class="sxs-lookup"><span data-stu-id="ad2ad-117">int</span></span></p></td>
<td><p><span data-ttu-id="ad2ad-118">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="ad2ad-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ad2ad-119">Numero ID utilizzato insieme a ErrorTime e ProgressReportSeq per identificare in modo univoco un rapporto sullo stato.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="ad2ad-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ad2ad-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad2ad-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ad2ad-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ad2ad-122">int</span><span class="sxs-lookup"><span data-stu-id="ad2ad-122">int</span></span></p></td>
<td><p><span data-ttu-id="ad2ad-123">Primaria/o, esterna/o</span><span class="sxs-lookup"><span data-stu-id="ad2ad-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ad2ad-124">Numero ID che identifica la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-124">ID number that identifies the error report.</span></span> <span data-ttu-id="ad2ad-125">ErrorReporSeq viene utilizzato insieme a ErrorTime per identificare in modo univoco un rapporto di errore.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="ad2ad-126">Per ulteriori informazioni, vedere la <a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ad2ad-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="ad2ad-127">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad2ad-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ad2ad-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ad2ad-129">int</span><span class="sxs-lookup"><span data-stu-id="ad2ad-129">int</span></span></p></td>
<td><p><span data-ttu-id="ad2ad-130">Principale</span><span class="sxs-lookup"><span data-stu-id="ad2ad-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="ad2ad-p105">Numero ID per identificare il rapporto sullo stato. Utilizzato insieme a ErrorTime ed ErrorReportSeq per identificare in modo univoco un rapporto sullo stato.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad2ad-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="ad2ad-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="ad2ad-134">int</span><span class="sxs-lookup"><span data-stu-id="ad2ad-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ad2ad-135">ID diagnostica del rapporto sullo stato.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="ad2ad-136">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad2ad-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="ad2ad-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="ad2ad-138">int</span><span class="sxs-lookup"><span data-stu-id="ad2ad-138">int</span></span></p></td>
<td><p><span data-ttu-id="ad2ad-139">Stranieri</span><span class="sxs-lookup"><span data-stu-id="ad2ad-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ad2ad-140">Server che ha inviato la segnalazione errori (se il rapporto è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="ad2ad-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="ad2ad-141">Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> . Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad2ad-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="ad2ad-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="ad2ad-143">int</span><span class="sxs-lookup"><span data-stu-id="ad2ad-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ad2ad-p107">Processo di Lync Server a cui fa riferimento il rapporto. Per ulteriori informazioni, vedere la tabella Application.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad2ad-146"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="ad2ad-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="ad2ad-147">immagine</span><span class="sxs-lookup"><span data-stu-id="ad2ad-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ad2ad-148">Dettagli del rapporto sullo stato archiviati in formato binario per non occupare troppo spazio. I dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="ad2ad-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="ad2ad-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="ad2ad-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad2ad-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="ad2ad-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="ad2ad-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="ad2ad-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ad2ad-152">Identificatore univoco che correla informazioni relative al tempo di partecipazione per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="ad2ad-153">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad2ad-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="ad2ad-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ad2ad-155">int</span><span class="sxs-lookup"><span data-stu-id="ad2ad-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ad2ad-156">Tempo (in millisecondi) necessario per un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="ad2ad-157">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad2ad-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

