---
title: 'Lync Server 2013: Tabella ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f9377b70923c1dc2c7213e9ac72486daffcda99
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a>Tabella ErrorReport in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

Nella Tabella ErrorReport vengono archiviate informazioni sugli errori che si sono verificati. Ogni record corrisponde a un'occorrenza di un errore. Gli errori vengono acquisiti dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o inviati dal client.


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
<td><p>datetime</p></td>
<td><p>Principale</p></td>
<td><p>Data e ora in cui si è verificato l'errore.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Numero ID per identificare la segnalazione errori. Utilizzato insieme a <strong>ErrorTime</strong> per identificare in modo univoco un report di errore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>ID univoco del tipo di errore. Per ulteriori informazioni, vedere la <a href="lync-server-2013-errordef-table.md">tabella ErrorDef in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Utente che ha originato la richiesta che ha causato l'errore. Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Touserid</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Utente di destinazione per la richiesta che ha causato l'errore. Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>URI della conferenza relativo all'errore. Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> . In genere, se ConferenceUriId non è null, FromUserId o touserid sarà null.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Stranieri</p></td>
<td><p>Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Numero ID per identificare la sessione. Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Server che ha inviato la segnalazione errori (se il rapporto è stato inviato da un componente server). Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> .</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Server che ha inviato la segnalazione errori (se il rapporto è stato inviato da un componente server). Per ulteriori informazioni, vedere la <a href="lync-server-2013-application-table.md">tabella applicazioni in Lync Server 2013</a> .</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>immagine</p></td>
<td><p> </p></td>
<td><p>Ulteriori informazioni sull'errore.</p>
<p>Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>La versione client di endpoint che invia la segnalazione errori. Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>È la segnalazione errori acquisita dall'agente di registrazione dettagli chiamata in esecuzione nel server front-end o inviata dal client.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bandiera</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Riservato per utilizzi futuri.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>Identificatore univoco di correlazione delle informazioni sul tempo di partecipazione per i diversi componenti coinvolti in una conferenza.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Tempo (in millisecondi) richiesto da un componente specifico per partecipare a una conferenza.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Rappresenta il nome di dominio completo del server che ha generato la segnalazione errori.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Rappresenta il nome di dominio completo del pool in cui è stato generato il report di errore.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

