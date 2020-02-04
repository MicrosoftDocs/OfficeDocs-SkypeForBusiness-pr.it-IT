---
title: 'Lync Server 2013: tabella SIPResponseMetaData'
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
ms.openlocfilehash: 1fcd6cb462bd64f6fdcdbae93cfb733de0639898
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Tabella SIPResponseMetaData in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

SIPResponseMetaDataTable contiene un elenco di codici di risposta SIP e la classificazione e la definizione di ognuno di questi codici. Questi codici vengono generati in risposta agli eventi che interessano i dispositivi SIP e le sessioni di comunicazione SIP; ad esempio, il codice di risposta 403 viene generato quando un dispositivo SIP effettua una richiesta, ma il server rifiuta di onorare la richiesta.

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
<td><p>Classificazione generale per il codice di risposta. Le classificazioni includono:</p>
<ul>
<li><p>1-risposte informative</p></li>
<li><p>2-risposte di successo</p></li>
<li><p>3-risposte di Reindirizzamento</p></li>
<li><p>4-risposte di errore client</p></li>
<li><p>5--risposte di errore del server</p></li>
<li><p>6-risposta di errore globale</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Descrizione</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Descrizione del codice di risposta SIP. Ad esempio, il codice di risposta 181 ha la seguente descrizione:</p>
<p>Chiamata inoltrata</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

