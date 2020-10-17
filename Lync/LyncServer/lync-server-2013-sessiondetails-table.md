---
title: 'Lync Server 2013: tabella SessionDetails'
description: 'Lync Server 2013: tabella SessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd927f784fb0f2a835c896824105fe8bb112c7a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569932"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a>Tabella SessionDetails in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

Ogni record rappresenta una sessione peer-to-peer, ovvero una chiamata telefonica VoIP-VoIP, una sessione di messaggistica istantanea con due partecipanti o un altro tipo di sessione. È possibile eseguire una tabella di join con la [tabella media in Lync Server 2013](lync-server-2013-media-table.md) per trovare i dettagli di ogni supporto coinvolto in questa sessione.

Si noti che i campi IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone sono stati eliminati dalla tabella SessionDetails utilizzata in Microsoft Lync Server 2013.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primaria, esterna</p></td>
<td><p>Data e ora della richiesta di sessione. Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaria, esterna</p></td>
<td><p>Numero ID per identificare la sessione. Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione. * vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> per ulteriori informazioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>GUID per correlare più sessioni.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Stranieri</p></td>
<td><p>Numero ID per l'identificazione della finestra di dialogo sostituita dalla sessione corrente. Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Numero ID per l'identificazione della sessione. Valore utilizzato in combinazione con <strong>ReplacesDialogIdTime</strong> per identificare in modo univoco una sessione sostituita da questa sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1Id</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>ID di un utente nella sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>ID dell'altro utente nella sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>GUID che identifica l'endpoint utilizzato dal primo utente della sessione.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>GUID che identifica l'endpoint utilizzato dal secondo utente della sessione.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>URI utente di destinazione originale nella richiesta SIP. Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionStartedById</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>ID dell'utente che ha avviato la sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Indica l'ID dell'utente per conto del quale il chiamante esegue la chiamata. Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>ID dell'utente da quale proviene la chiamata. Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>ID del Front End Server utilizzato per questa sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-servers-table.md">tabella Servers in Lync server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>ID del pool in cui è stata acquisita la sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Tipo di contenuto utilizzato nella sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-contenttypes-table.md">tabella ContentTypes in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Versione del client utilizzata da User1. Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Versione del client utilizzata da User2. Per ulteriori informazioni, vedere la <a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Server perimetrale utilizzato da User1. Per ulteriori informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Server perimetrale utilizzato da User2. Per ulteriori informazioni, vedere la <a href="lync-server-2013-edgeservers-table.md">tabella EdgeServers in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Indica se User1 è connesso o meno dall'interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Indica se User2 è connesso o meno dall'interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Ora della prima richiesta INVITE. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non esiste un messaggio INVITE, il campo conterrà data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO). I dati contenuti in questo campo sono, tipicamente, quelli generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Ora della risposta al primo messaggio INVITE. I dati contenuti in questo campo sono, tipicamente, quelli generati dal messaggio INVITE iniziale nella sessione. Se non esiste un messaggio INVITE, il campo conterrà data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID diagnostica acquisito dall'intestazione SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallPriority</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Priorità della chiamata. Per ulteriori informazioni, vedere la <a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>User1MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Numero di messaggi inviati da User1 durante la sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Numero di messaggi inviati da User2 durante la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Orario al termine della sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaTypes</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Set di bit che indica il tipo di contenuto multimediale della sessione. Di seguito sono elencate le definizioni dei tipi:</p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>IM</p></td>
<td><p>1 </p></td>
</tr>
<tr class="even">
<td><p>FILE_TRANSFER</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>REMOTE_ASSISTANCE</p></td>
<td><p>4 </p></td>
</tr>
<tr class="even">
<td><p>APP_SHARING</p></td>
<td><p>8 </p></td>
</tr>
<tr class="odd">
<td><p>AUDIO</p></td>
<td><p>16 </p></td>
</tr>
<tr class="even">
<td><p>VIDEO</p></td>
<td><p>32</p></td>
</tr>
<tr class="odd">
<td><p>APP_INVITE</p></td>
<td><p>64</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>User1Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Set di bit che indica gli attributi di User1. Sono elencate le definizioni di attributo seguenti:</p>
<ul>
<li><p>0x01 - Integrato con telefono da tavolo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Set di bit che indica gli attributi di User2. Sono elencate le definizioni di attributo seguenti:</p>
<ul>
<li><p>0x01 - Integrato con telefono da tavolo</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Set di bit che indica gli attributi della chiamata. Sono elencate le definizioni di attributo seguenti:</p>
<ul>
<li><p>0x01 - Nuovi tentativi di sessione</p></li>
<li><p>0x02 - Chiamata effettuata da un agente per conto di un Response Group</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Elaborati</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Per uso interno del servizio di monitoraggio.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\* Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1. Se più sessioni iniziano esattamente alla stessa ora, il valore SessionIdSeq per una sarà 1, per l'altra sarà 2 e così via.

</div>

<span> </span>

</div>

</div>

</div>

