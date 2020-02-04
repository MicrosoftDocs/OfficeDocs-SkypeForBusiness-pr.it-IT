---
title: 'Lync Server 2013: visualizzazione ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46356099c3eee20794a4198720597dc4395b563f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a>Visualizzazione ConferenceSessionDetails in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-12_

La visualizzazione ConferenceSessionDetails archivia le informazioni sulle sessioni multiparte. Ogni record rappresenta una sessione di conferenza, che può essere la sessione con lo stato attiva o la sessione con uno specifico server di conferenza. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo di dati</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Ora della richiesta della sessione. Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numero ID per identificare la sessione. Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Ora della prima richiesta di invito. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI della conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URI del tipo di conferenza. Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificatore che distingue tra le istanze delle conferenze periodiche. Ogni istanza di conferenza ricorrente ha lo stesso ConferenceURI, ma un valore ConfInstance diverso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del server dei servizi di conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo di URI di conferenza server. Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI dell'utente coinvolto nella sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo di URI dell'utente di cui è stata parte della sessione. Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tenant dell'utente di cui è stata parte della sessione. Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificatore univoco dell'utente di cui faceva parte della sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Ora di fine della sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Versione di Conference Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Tipo di server conferenza. Per altre informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoria Server conferenze.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Versione del client usata dall'utente che ha partecipato alla sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Client usato dall'utente che ha partecipato alla sessione. Per altri dettagli, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nome della categoria del client usata dall'utente che faceva parte della sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI dell'utente per conto della quale è stata avviata la sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo di URI dell'utente per conto della quale è stata avviata la sessione. Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tenant dell'utente per cui è stata avviata la sessione. Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI dell'utente che ha fatto riferimento alla sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo di URI dell'utente che ha fatto riferimento alla sessione. Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tenant dell'utente che ha fatto riferimento alla sessione. Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>ID finestra di dialogo SIP. Il formato è</p>
<p>:d ialog; from-tag; to-Tag</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Numero ID per identificare la finestra di dialogo che è stata sostituita dalla sessione corrente. Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numero ID per identificare la sessione. Usato in combinazione con ReplaceDialogIdTime per identificare in modo univoco una sessione sostituita da questa sessione. Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>ID finestra di dialogo SIP che sostituisce la sessione. Il formato dell'is:</p>
<p>finestra di dialogo; da-tag; to-Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>po'</p></td>
<td><p>Indica se la sessione è stata avviata dal server dei servizi di conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>po'</p></td>
<td><p>Indica se la sessione è stata terminata dal server dei servizi di conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>po'</p></td>
<td><p>Indica se l'utente ha effettuato l'accesso dalla rete interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Ora della risposta al primo messaggio di invito. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Codice di risposta SIP per l'invito alla sessione. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>ID di diagnostica acquisito dalle intestazioni SIP della sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo di contenuto per la sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome di dominio completo del server front-end che ha acquisito i dati per la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome di dominio completo del pool che ha acquisito i dati per la sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mediation Server usato dall'utente che ha partecipato alla sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Gateway usato dall'utente che ha partecipato alla sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN dell'Edge Server usato dall'utente che ha partecipato alla sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Indica gli attributi dell'utente che ha partecipato alla sessione. Le definizioni di attributo seguenti sono consentite:</p>
<p>0x01-integrato con il telefono desktop</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Indica gli attributi di chiamata. Sono consentite le definizioni di attributo seguenti:</p>
<p>0x01-riprovato Session0</p>
<p>X02-chiamata effettuata dall'agente per conto di un gruppo di risposte</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

