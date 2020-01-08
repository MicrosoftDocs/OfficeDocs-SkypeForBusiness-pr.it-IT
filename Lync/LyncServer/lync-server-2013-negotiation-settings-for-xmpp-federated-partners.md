---
title: 'Lync Server 2013: Impostazioni di negoziazione per i partner federati XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d72870e4060be6aa4ec428159af7ab19cb68b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Impostazioni di negoziazione per i partner federati XMPP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-21_

Le impostazioni per i tipi di negoziazione nella configurazione di un partner XMPP hanno un'ampia varietà di combinazioni possibili. Non tutte le combinazioni sono valide. La tabella dettagliata in questo argomento definirà le impostazioni valide e non valide. Le configurazioni comuni sono presentate nella prima tabella, la seconda tabella che descrive tutte le combinazioni possibili. Tieni presente che non puoi avere un protocollo SASL ( *Simple Authentication and Security Layer* ) **a meno che non** sia disponibile anche *Transport Layer Security* (TLS). SASL viene inviato in formato non crittografato e non deve mai essere trasmesso a meno che non sia protetto da un altro mezzo, ad esempio TLS.

### <a name="common-xmpp-federation-negotiation-methods"></a>Metodi di negoziazione federativi comuni XMPP

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
<th>Autenticazione richiamata</th>
<th>Metodo di autenticazione previsto (s)</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obbligatorio</p></td>
<td><p>Obbligatorio</p></td>
<td><p>False</p></td>
<td><p>SASL su TLS</p></td>
<td><p>TLS e SASL necessari aiutano a garantire che il flusso di messaggi SASL sia sicuro. Richiamata non è disponibile e non può essere usato per un metodo di fallback se il partner federato XMPP non ha impostato TLS su obbligatorio o facoltativo.</p></td>
</tr>
<tr class="even">
<td><p>Obbligatorio</p></td>
<td><p>Facoltativo</p></td>
<td><p>True</p></td>
<td><p>SASL su TLS, TLS richiamata, TCP richiamata</p></td>
<td><p>Richiedendo TLS, se è usato il partner federato XMPP che ha impostato SASL su SASL facoltativo o richiesto. Se SASL non è disponibile, verrà usato richiamata su TLS.</p></td>
</tr>
<tr class="odd">
<td><p>Facoltativo</p></td>
<td><p>Facoltativo</p></td>
<td><p>True</p></td>
<td><p>SASL su TLS, TLS richiamata, TCP richiamata</p></td>
<td><p>Sebbene sia molto flessibile nei metodi di negoziazione offerti, queste impostazioni si basano sulle impostazioni del partner federativo XMPP. Se il partner ha TLS facoltativo o obbligatorio, ma SASL non è supportato, TLS richiamata sarà disponibile. Se il partner ha impostato TLS e SASL su facoltativo o obbligatorio, viene usata la selezione ottimale di TLS su SASL.</p></td>
</tr>
<tr class="even">
<td><p>Non supportato</p></td>
<td><p>Non supportato</p></td>
<td><p>True</p></td>
<td><p>TCP richiamata</p></td>
<td><p>In molti casi, TCP richiamata è l'unica soluzione possibile. Meno auspicabile rispetto ad altre opzioni, offre un certo livello di attendibilità.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>Matrice del metodo di negoziazione della Federazione XMPP-completamento

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
<th>Autenticazione richiamata</th>
<th>Metodo di autenticazione previsto</th>
<th>Note, avvisi o errori per la configurazione non valida</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Obbligatorio</p></td>
<td><p>Obbligatorio</p></td>
<td><p>True</p></td>
<td><p>SASL su TLS</p></td>
<td><div>

> [!WARNING]  
> Richiamata non funzionerà se sono necessari sia SASL che TLS.


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
<td><p>True</p></td>
<td><p>SASL su TLS, TLS richiamata, TCP richiamata</p></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.


</div></td>
</tr>
<tr class="even">
<td><p>Facoltativo</p></td>
<td><p>Obbligatorio</p></td>
<td><p>False</p></td>
<td><p>SASL su TLS</p></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.


</div></td>
</tr>
<tr class="odd">
<td><p>Non supportato</p></td>
<td><p>Obbligatorio</p></td>
<td><p>True</p></td>
<td><p>TCP richiamata</p></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.


</div></td>
</tr>
<tr class="even">
<td><p>Non supportato</p></td>
<td><p>Obbligatorio</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> Configurazione non valida


</div></td>
<td><div>

> [!WARNING]  
> Poiché SASL richiede TLS e TLS non è disponibile, SASL/TLS non riesce. TCP richiamata è impostato su false e non può essere usato.


</div></td>
</tr>
<tr class="odd">
<td><p>Obbligatorio</p></td>
<td><p>Facoltativo</p></td>
<td><p>True</p></td>
<td><p>SASL su TLS, TLS richiamata</p></td>
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
<td><p>True</p></td>
<td><p>SASL su TLS, TLS richiamata, TCP richiamata</p></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.


</div></td>
</tr>
<tr class="even">
<td><p>Facoltativo</p></td>
<td><p>Facoltativo</p></td>
<td><p>False</p></td>
<td><p>SASL su TLS</p></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.


</div></td>
</tr>
<tr class="odd">
<td><p>Non supportato</p></td>
<td><p>Facoltativo</p></td>
<td><p>True</p></td>
<td><p>TCP richiamata</p></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.


</div></td>
</tr>
<tr class="even">
<td><p>Non supportato</p></td>
<td><p>Facoltativo</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> Configurazione non valida


</div></td>
<td><div>

> [!WARNING]  
> SASL richiede TLS. La possibilità di consentire a TLS di essere facoltativa può comportare una negoziazione non riuscita.


</div></td>
</tr>
<tr class="odd">
<td><p>Obbligatorio</p></td>
<td><p>Non supportato</p></td>
<td><p>True</p></td>
<td><p>TLS richiamata</p></td>
<td><p>La configurazione consente la richiamata TLS.</p></td>
</tr>
<tr class="even">
<td><p>Obbligatorio</p></td>
<td><p>Non supportato</p></td>
<td><p>False</p></td>
<td><p>Configurazione non valida</p></td>
<td><div>

> [!WARNING]  
> La funzionalità SASL o richiamata deve essere abilitata.


</div></td>
</tr>
<tr class="odd">
<td><p>Facoltativo</p></td>
<td><p>Non supportato</p></td>
<td><p>True</p></td>
<td><p>TLS richiamata, TCP richiamata</p></td>
<td><p>In base alle scelte di negoziazione dell'altro punto finale, verranno accettate le richiamata TCP o TLS.</p></td>
</tr>
<tr class="even">
<td><p>Facoltativo</p></td>
<td><p>Non supportato</p></td>
<td><p>False</p></td>
<td><p>Configurazione non valida</p></td>
<td><div>

> [!WARNING]  
> La funzionalità SASL o richiamata deve essere abilitata.


</div></td>
</tr>
<tr class="odd">
<td><p>Non supportato</p></td>
<td><p>Non supportato</p></td>
<td><p>True</p></td>
<td><p>TCP richiamata</p></td>
<td><p>TCP richiamata è l'unico metodo di negoziazione disponibile</p></td>
</tr>
<tr class="even">
<td><p>Non supportato</p></td>
<td><p>Non supportato</p></td>
<td><p>False</p></td>
<td><p>Configurazione non valida</p></td>
<td><div>

> [!WARNING]  
> La funzionalità SASL o richiamata deve essere abilitata.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

