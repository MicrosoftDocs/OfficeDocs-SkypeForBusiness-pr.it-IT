---
title: "Lync Server 2013: avvio di Lync da un'altra applicazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dafb8295d3070cd9f38e8691e654146978156d45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>Avvio di Lync da un'altra applicazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-20_

È possibile usare i parametri della riga di comando per avviare rapidamente Lync 2013. Ad esempio, se un utente fa clic su un numero di telefono in un'altra applicazione, l'applicazione può avviare un'istanza di Lync 2013 e avviare una chiamata a tale numero.

Lync 2013 può anche riconoscere un elenco delimitato da punti e virgola di nomi di contatti per i servizi di conferenza multiparte.

Se Lync 2013 è configurato per l'accesso automatico all'avvio, l'avvio di Lync 2013 con i parametri della riga di comando consente di aprire la finestra principale di Lync. Se Lync non è configurato per l'accesso automatico all'avvio, viene visualizzata la finestra di accesso.

La tabella seguente mostra i parametri disponibili.

### <a name="lync-2013-command-line-parameters"></a>Parametri della riga di comando di Lync 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Estensione</th>
<th>Formato dei dati</th>
<th>Azione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel</p></td>
<td><p>URI tel</p></td>
<td><p>Apre la finestra di conversazione per una chiamata audio ma non compone il numero specificato.</p></td>
</tr>
<tr class="even">
<td><p>CALLTO</p></td>
<td><p>Tel:, SIP: o URI di tipo Tel</p></td>
<td><p>Apre la finestra di conversazione per una chiamata audio ma non compone il numero specificato.</p></td>
</tr>
<tr class="odd">
<td><p>SIP</p></td>
<td><p>URI SIP</p></td>
<td><p>Apre la finestra di conversazione con l'URI (Uniform Resource Identifier) SIP specificato nell'elenco dei partecipanti.</p></td>
</tr>
<tr class="even">
<td><p>Sorsi</p></td>
<td><p>URI SIP</p></td>
<td><p>Se Lync 2013 è configurato per l'uso del protocollo Transport Layer Security (TLS), funziona esattamente come SIP:. Se TLS non viene usato, Visualizza una finestra di dialogo che informa l'utente che è necessario un livello di sicurezza più elevato.</p></td>
</tr>
<tr class="odd">
<td><p>conf</p></td>
<td><p>URI SIP della conferenza a cui partecipare</p></td>
<td><p>Se URI è autonomo, crea un'istanza dello stato attiva e visualizza la visualizzazione solo elenco. In caso contrario, porta in alto la visualizzazione roster ma non invia INVITE.</p></td>
</tr>
<tr class="even">
<td><p>messaggistica istantanea</p></td>
<td><p>URI SIP</p></td>
<td><p>Consente di visualizzare una finestra di conversazione solo messaggistica istantanea con l'URI SIP. Accetta più URI SIP specificati all'interno di parentesi angolari (&lt;&gt;) senza alcun separatore.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


La tabella seguente contiene alcuni esempi di questi parametri della riga di comando.

### <a name="command-line-parameter-examples"></a>Esempi di parametri della riga di comando

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Istanza</th>
<th>Risultati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel: + 14255550101</p></td>
<td><p>Apre una visualizzazione solo telefono con + 14255550101.</p></td>
</tr>
<tr class="even">
<td><p>Callto: Tel: + 14255550101</p></td>
<td><p>Apre una visualizzazione solo telefono con + 14255550101.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Apre una visualizzazione solo telefono con kazuto@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Apre una finestra di conversazione con kazuto@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p>conf: SIP:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Apre una finestra di conversazione e visualizza le opzioni di partecipazione audio della riunione.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

