---
title: 'Lync Server 2013: configurazione degli intervalli di porte per i server perimetrali'
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
ms.openlocfilehash: 0ce17300c6504989d132cb27301128bfbc568870
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Configurazione degli intervalli di porte per i server perimetrali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-07-24_

Con i server perimetrali non è necessario configurare intervalli di porte separati per la condivisione di audio, video e applicazioni. Analogamente, gli intervalli di porte utilizzati per i server perimetrali non devono corrispondere agli intervalli di porte utilizzati con le conferenze, l'applicazione e i Mediation Server. Prima di procedere con l'esempio, è importante sottolineare che, sebbene esista questa opzione, si consiglia di non modificare gli intervalli di porte, in quanto ciò potrebbe influire negativamente su alcuni scenari se si esce dall'intervallo di porte 50000.

Si supponga, ad esempio, che siano stati configurati i servizi di conferenza, applicazione e Mediation Server per l'utilizzo di questi intervalli di porte:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di pacchetto</th>
<th>Numero di porta iniziale</th>
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


Come si può notare, gli intervalli di porte per la condivisione di audio, video e applicazioni partono dalla porta 40803 e comprendono un totale di 24732 porte. Se lo si desidera, è possibile configurare un server perimetrale specifico affinché utilizzi questi valori generali, eseguendo un comando simile al seguente da Lync Server Management Shell:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Alternativamente, è possibile utilizzare il comando seguente per configurare simultaneamente tutti i server perimetrali all'interno dell'organizzazione:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

È possibile verificare le impostazioni correnti delle porte per i server perimetrali utilizzando il comando Lync Server Management Shell:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Anche in questo caso, se si forniscono queste opzioni, si consiglia vivamente di lasciare le cose così come sono per la configurazione della porta.

</div>

<span> </span>

</div>

</div>

</div>

