---
title: 'Lync Server 2013: Tabella ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0fc30d4686ffcc1d1cda0474b3b01a645c94be5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a>Tabella ErrorReport in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

La Tabella ErrorReport archivia le informazioni sugli errori che si sono verificati. Ogni record è un'occorrenza di errore. Gli errori vengono acquisiti dall'agente CDR in uso nel server front-end o inviati dal client.


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
<td><p>Principale</p></td>
<td><p>Data e ora in cui si è verificato l'errore.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Numero ID per identificare il report degli errori. Usato in combinazione con <strong>ErrorTime</strong> per identificare in modo univoco una segnalazione di errori.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>ID univoco del tipo di errore. Per altre informazioni, vedere la <a href="lync-server-2013-errordef-table.md">tabella ErrorDef in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Utente che ha originato la richiesta che ha causato l'errore. Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Touserid</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Utente di destinazione per la richiesta che ha causato l'errore. Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>URI della conferenza correlato all'errore. Per altre informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> . In genere, se ConferenceUriId non è null, FromUserId o touserid sarà null.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Esterna</p></td>
<td><p>Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione. Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Numero ID per identificare la sessione. Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione. Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Server che ha inviato il report degli errori (se il report viene inviato da un componente server). Per altre informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella server in Lync server 2013</a> .</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Server che ha inviato il report degli errori (se il report viene inviato da un componente server). Per altre informazioni, vedere la <a href="lync-server-2013-application-table.md">tabella delle applicazioni in Lync Server 2013</a> .</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>image</p></td>
<td><p> </p></td>
<td><p>Altre informazioni sull'errore.</p>
<p>Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Versione client di endpoint che invia il report di errore. Per altre informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>È il rapporto di errore acquisito dall'agente CDR in uso nel server front-end o inviato dal client.</p></td>
</tr>
<tr class="even">
<td><p><strong>Contrassegno</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Riservato per un uso futuro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>Identificatore univoco che correla le informazioni sul tempo di join per i diversi componenti coinvolti in una conferenza.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ora (in millisecondi) necessaria per un componente specifico per partecipare a una conferenza.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Rappresenta il nome di dominio completo del server che ha generato il report degli errori.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Rappresenta il nome di dominio completo del pool in cui è stato generato il report di errore.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

