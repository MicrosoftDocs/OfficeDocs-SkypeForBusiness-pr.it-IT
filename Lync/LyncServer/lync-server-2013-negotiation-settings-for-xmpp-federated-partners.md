---
title: 'Lync Server 2013: impostazioni di negoziazione per i partner federati XMPP'
description: 'Lync Server 2013: impostazioni di negoziazione per i partner federati XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578642"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Impostazioni di negoziazione per i partner federati XMPP in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-21_

Le impostazioni per i tipi di negoziazione nella configurazione di un Partner XMPP offrono un'ampia gamma di possibili combinazioni. Non tutte le combinazioni sono valide. Nella tabella illustrata in questo argomento vengono elencate le impostazioni valide e quelle non valide. Le configurazioni più comuni sono presentate nella prima tabella, mentre la seconda tabella contiene tutte le possibili combinazioni. Si noti che non è possibile disporre *di Simple Authentication and Security Layer* (SASL), **a meno che non** sia disponibile anche TLS ( *Transport Layer Security* ). SASL viene inviato in un formato non crittografato (leggibile) e non dovrebbe mai essere trasmesso se non viene protetto in altro modo, ad esempio con TLS.

### <a name="common-xmpp-federation-negotiation-methods"></a>Metodi comuni di negoziazione per la federazione XMPP

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>TLS (Transport Layer Security)</th>
<th>SASL (Simple Authentication and Security Layer)</th>
<th>Autenticazione dialback</th>
<th>Metodi di autenticazione previsti</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obbligatorio</p></td>
<td><p>Obbligatorio</p></td>
<td><p>False</p></td>
<td><p>SASL su TLS</p></td>
<td><p>L'obbligatorietà di TLS e SASL aiuta ad assicurare la protezione del flusso di messaggi SASL. Il dialback non è disponibile e non può essere utilizzato come metodo di fallback se il partner federato XMPP non ha impostato TLS su obbligatorio o facoltativo.</p></td>
</tr>
<tr class="even">
<td><p>Obbligatorio</p></td>
<td><p>Facoltativo</p></td>
<td><p>Vero</p></td>
<td><p>SASL su TLS, dialback TLS, dialback TCP</p></td>
<td><p>Impostando TLS come obbligatorio, se il partner federato XMPP ha impostato SASL su facoltativo o su obbligatorio, viene utilizzato SASL. Se SASL non è disponibile, verrà utilizzato il dialback su TLS.</p></td>
</tr>
<tr class="odd">
<td><p>Facoltativo</p></td>
<td><p>Facoltativo</p></td>
<td><p>Vero</p></td>
<td><p>SASL su TLS, dialback TLS, dialback TCP</p></td>
<td><p>Molto flessibili nel metodo di negoziazione offerto, queste impostazioni si avvalgono delle impostazioni dei partner della federazione XMPP. Se TLS è facoltativo o obbligatorio per il partner ma SASL non è supportato, sarà disponibile il dialback TLS. Se TLS e SASL sono impostati su facoltativo o obbligatorio per il partner, viene utilizzata la selezione ottimale di TLS su SASL.</p></td>
</tr>
<tr class="even">
<td><p>Non supportato</p></td>
<td><p>Non supportato</p></td>
<td><p>Vero</p></td>
<td><p>Dialback TCP</p></td>
<td><p>In molti casi il dialback TCP è l'unica soluzione possibile. Meno desiderabile di altre opzioni, offre comunque un buon grado di attendibilità.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>Matrice dei metodi di negoziazione per la federazione XMPP - Completa

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>TLS (Transport Layer Security)</th>
<th>SASL (Simple Authentication and Security Layer)</th>
<th>Autenticazione dialback</th>
<th>Metodo di autenticazione previsto</th>
<th>Note, avvisi o errori di configurazione non valida</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obbligatorio</p></td>
<td><p>Obbligatorio</p></td>
<td><p>Vero</p></td>
<td><p>SASL su TLS</p></td>
<td><div>

> [!WARNING]  
> Se SASL e TSL sono entrambi obbligatori, il dialback non verrà utilizzato.


</div></td>
</tr>
<tr class="even">
<td><p>Obbligatorio</p></td>
<td><p>Obbligatorio</p></td>
<td><p>False</p></td>
<td><p>SASL su TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Facoltativo</p></td>
<td><p>Obbligatorio</p></td>
<td><p>Vero</p></td>
<td><p>SASL su TLS, dialback TLS, dialback TCP</p></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.


</div></td>
</tr>
<tr class="even">
<td><p>Facoltativo</p></td>
<td><p>Obbligatorio</p></td>
<td><p>False</p></td>
<td><p>SASL su TLS</p></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.


</div></td>
</tr>
<tr class="odd">
<td><p>Non supportato</p></td>
<td><p>Obbligatorio</p></td>
<td><p>Vero</p></td>
<td><p>Dialback TCP</p></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.


</div></td>
</tr>
<tr class="even">
<td><p>Non supportato</p></td>
<td><p>Obbligatorio</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> Configurazione non valida.


</div></td>
<td><div>

> [!WARNING]  
> Poiché SASL richiede TLS, ma TLS non è disponibile, SASL/TLS ha esito negativo. Il dialback TCP è impostato su false e non può essere utilizzato.


</div></td>
</tr>
<tr class="odd">
<td><p>Obbligatorio</p></td>
<td><p>Facoltativo</p></td>
<td><p>Vero</p></td>
<td><p>SASL su TLS, dialback TLS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Obbligatorio</p></td>
<td><p>Facoltativo</p></td>
<td><p>False</p></td>
<td><p>SASL su TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Facoltativo</p></td>
<td><p>Facoltativo</p></td>
<td><p>Vero</p></td>
<td><p>SASL su TLS, dialback TLS, dialback TCP</p></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.


</div></td>
</tr>
<tr class="even">
<td><p>Facoltativo</p></td>
<td><p>Facoltativo</p></td>
<td><p>False</p></td>
<td><p>SASL su TLS</p></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.


</div></td>
</tr>
<tr class="odd">
<td><p>Non supportato</p></td>
<td><p>Facoltativo</p></td>
<td><p>Vero</p></td>
<td><p>Dialback TCP</p></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.


</div></td>
</tr>
<tr class="even">
<td><p>Non supportato</p></td>
<td><p>Facoltativo</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> Configurazione non valida.


</div></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. Impostando TLS come facoltativo, potrebbero verificarsi errori di negoziazione delle sessioni.


</div></td>
</tr>
<tr class="odd">
<td><p>Obbligatorio</p></td>
<td><p>Non supportato</p></td>
<td><p>Vero</p></td>
<td><p>Dialback TLS</p></td>
<td><p>La configurazione consente il dialback TLS.</p></td>
</tr>
<tr class="even">
<td><p>Obbligatorio</p></td>
<td><p>Non supportato</p></td>
<td><p>False</p></td>
<td><p>Configurazione non valida.</p></td>
<td><div>

> [!WARNING]  
> È necessario abilitare SASL o Dialback.


</div></td>
</tr>
<tr class="odd">
<td><p>Facoltativo</p></td>
<td><p>Non supportato</p></td>
<td><p>Vero</p></td>
<td><p>Dialback TLS, dialback TCP</p></td>
<td><p>Basato sulle scelte di negoziazione dell'altro endpoint, il dialback TCP o TLS verrà accettato.</p></td>
</tr>
<tr class="even">
<td><p>Facoltativo</p></td>
<td><p>Non supportato</p></td>
<td><p>False</p></td>
<td><p>Configurazione non valida.</p></td>
<td><div>

> [!WARNING]  
> È necessario abilitare SASL o Dialback.


</div></td>
</tr>
<tr class="odd">
<td><p>Non supportato</p></td>
<td><p>Non supportato</p></td>
<td><p>Vero</p></td>
<td><p>Dialback TCP</p></td>
<td><p>Il dialback TCP è l'unico metodo di negoziazione disponibile</p></td>
</tr>
<tr class="even">
<td><p>Non supportato</p></td>
<td><p>Non supportato</p></td>
<td><p>False</p></td>
<td><p>Configurazione non valida.</p></td>
<td><div>

> [!WARNING]  
> È necessario abilitare SASL o Dialback.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

