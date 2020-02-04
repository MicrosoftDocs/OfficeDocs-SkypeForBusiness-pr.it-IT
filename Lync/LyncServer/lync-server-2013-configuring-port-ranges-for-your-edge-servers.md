---
title: 'Lync Server 2013: configurazione degli intervalli di porte per gli Edge Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6eddf59f6fe4b2575e0e7d70adddb2e94c90e05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Configurazione degli intervalli di porte per gli Edge Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-07-24_

Con Edge Server non è necessario configurare intervalli di porte distinti per l'audio, il video e la condivisione di applicazioni; allo stesso modo, gli intervalli di porte usati per i server perimetrali non devono corrispondere agli intervalli di porte usati con i server di conferenza, applicazione e mediazione. Prima di procedere con il nostro esempio, è importante sottolineare che, mentre questa opzione esiste, ti consigliamo di non modificare gli intervalli di porte, perché questo potrebbe influire negativamente su alcuni scenari, se ci si sposta fuori dall'intervallo di porte di 50000.

Si supponga ad esempio di avere configurato i servizi di conferenza, applicazione e mediazione per l'uso di questi intervalli di porte:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di pacchetto</th>
<th>Porta di avvio</th>
<th>Numero di porte riservate</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Condivisione applicazioni</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>Video</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>Totali</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Come si può vedere, gli intervalli di porte per la condivisione di audio, video e applicazioni iniziano alla porta 40803 e includono un totale di 24732 porte. Se si preferisce, è possibile configurare un server perimetrale specifico per l'uso di questi valori di porta complessivi eseguendo un comando simile a quello di Lync Server Management Shell:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

In alternativa, usare il comando seguente per configurare contemporaneamente tutti i server perimetrali dell'organizzazione:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Puoi verificare le impostazioni della porta corrente per gli Edge Server usando il comando Lync Server Management Shell:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Anche in questo caso, quando forniamo queste opzioni, ti consigliamo vivamente di abbandonare gli elementi per la configurazione della porta.

</div>

<span> </span>

</div>

</div>

</div>

