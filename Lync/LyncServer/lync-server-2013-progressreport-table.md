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
ms.openlocfilehash: 2e1cb7c8e764097af96981220ee74d481b379341
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>Tabella ProgressReport in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

I report sullo stato di avanzamento si basano sui dati caricati dal client nel database dopo il completamento di una chiamata o di una sessione. I report sullo stato di avanzamento verranno scritti solo per le chiamate e le sessioni che Lync Server 2013 determina può essere utile per scopi diagnostici.

I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non si riferiscono necessariamente agli errori, ma ai messaggi che indicano lo stato delle chiamate o dei messaggi.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo di dati</th>
<th>Chiave/indice</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Primaria, straniera</p></td>
<td><p>Data e ora del report sugli errori di stato che contiene il report sullo stato di avanzamento. Per altre informazioni, vedere la <a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Primaria, straniera</p></td>
<td><p>Numero ID usato in combinazione con ErrorTime, ProgressReportSeq per identificare in modo univoco un report di stato. Per altre informazioni, vedere la <a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaria, straniera</p></td>
<td><p>Numero ID che identifica il report degli errori. ErrorReporSeq viene usato in combinazione con ErrorTime per identificare in modo univoco una segnalazione di errori. Per altre informazioni, vedere la <a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a> .</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Numero ID per identificare il rapporto di stato. Usato in combinazione con ErrorTime e ErrorReportSeq per identificare in modo univoco un report di stato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID di diagnostica del report sullo stato di avanzamento.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Server che ha inviato il report degli errori (se il report è stato inviato da un componente server). Per altre informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella server in Lync server 2013</a> . Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Processo del server Lync in cui si trova il report. Per altre informazioni, vedere la tabella delle applicazioni.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dettaglio</strong></p></td>
<td><p>image</p></td>
<td></td>
<td><p>Dettagli del report sullo stato di avanzamento, archiviati in formato binario per risparmiare spazio. Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</p>
<p>Cast (cast (dettaglio come varbinary (max)) come varchar (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>Identificatore univoco che correla le informazioni sull'ora di join per i diversi componenti coinvolti in una conferenza.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ora (in millisecondi) per un componente specifico per partecipare a una conferenza.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

