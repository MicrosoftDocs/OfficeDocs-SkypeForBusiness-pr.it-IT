---
title: 'Lync Server 2013: tabella SIPResponseMetaData'
description: 'Lync Server 2013: tabella SIPResponseMetaData.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 402cff331f81a9b46028d76de69deeaace8d5ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558982"
---
# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Tabella SIPResponseMetaData in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

Nella tabella SIPResponseMetaDataTable è contenuto un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice. Questi codici vengono generati in risposta a eventi che influiscono sui dispositivi SIP e sulle sessioni di comunicazioni SIP. Il codice di risposta 403 ad esempio viene generato quando un dispositivo SIP invia una richiesta, che però non viene soddisfatta dal server.

Questa tabella è stata introdotta in Microsoft Lync Server 2013.


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
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Valore numerico che rappresenta il codice di risposta SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Classe</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Classifica generale del codice di risposta. Sono incluse le classifiche seguenti:</p>
<ul>
<li><p>1: risposte informali</p></li>
<li><p>2: risposte con esito positivo</p></li>
<li><p>3: risposte di reindirizzamento</p></li>
<li><p>4: risposte di errore client</p></li>
<li><p>5-risposte di errore del server</p></li>
<li><p>6: risposta di errore globale</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Descrizione</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Descrizione del codice di risposta SIP. Il codice di risposta 181 ad esempio è associato alla descrizione seguente:</p>
<p>Call Is Being Forwarded</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

