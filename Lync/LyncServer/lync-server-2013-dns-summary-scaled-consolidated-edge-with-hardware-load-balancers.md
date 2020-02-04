---
title: Riepilogo di DNS - topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6be703e13ec50eb66ba52c981196df06adc6e5b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Riepilogo di DNS - topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-27_

I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono abbastanza semplici rispetto a quelli per i certificati e le porte. Inoltre, molti record sono facoltativi, a seconda di come si configurano i client che usano Lync 2013 e se si Abilita la Federazione.

Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Per informazioni dettagliate sulla configurazione della configurazione automatica dei client di Lync 2013 se non è configurato il DNS split-brain, vedere la sezione "configurazione automatica senza DNS divisa" in [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

La tabella seguente contiene un riepilogo dei record DNS necessari per supportare la topologia di Edge consolidato in scala (bilanciamento del carico hardware). Tieni presente che alcuni record DNS sono necessari solo per la configurazione automatica per i client Lync. Se si prevede di usare gli oggetti Criteri di gruppo per configurare i client Lync, i record associati non sono necessari.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisiti della scheda di rete Edge Server

Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete negli Edge Server e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna. Ad esempio, come illustrato nella figura scenario Consolidated Edge in scala [consolidata con il bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), il gateway predefinito punta al firewall esterno.

È possibile configurare due schede di rete in ogni server perimetrale come indicato di seguito:

  - **Scheda di rete 1 (interfaccia interna)**
    
    Interfaccia interna con 172.25.33.10 assegnati.
    
    Nessun gateway predefinito.
    
    Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a tutte le reti che contengono client o server Lync Server che utilizzano Lync Server, ad esempio da 172.25.33.0 a 192.168.10.0.

  - **Scheda di rete 2 (interfaccia esterna)**
    
    Alla scheda di rete vengono assegnati tre indirizzi IP pubblici, ad esempio 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge Services.
    
    <div>
    

    > [!NOTE]
    > Gli indirizzi IP assegnati alle interfacce di rete esterne effettive dell'Edge Server possono dipendere dal bilanciamento del carico hardware scelto. Fare riferimento alla documentazione relativa al dispositivo di bilanciamento del carico hardware per comprendere i requisiti di indirizzo IP effettivi.<BR>È comunque possibile usare un singolo indirizzo IP per tutte le tre interfacce del servizio Edge. Anche se questo Salva gli indirizzi IP, richiede numeri di porta diversi per ogni servizio. Il numero di porta predefinito è 443/TCP, che garantisce che la maggior parte dei firewall remoti consentirà il traffico. La modifica dei valori della porta in (ad esempio) 5061/TCP per il servizio Access Edge, 444/TCP per il servizio Web Conferencing Edge e 443/TCP per il servizio A/V Edge può causare problemi per gli utenti remoti in cui un firewall che sta dietro non consente il traffico su 5061/TCP e 444/TCP. Inoltre, tre indirizzi IP distinti semplificano la risoluzione dei problemi grazie alla possibilità di filtrare in base all'indirizzo IP.

    
    </div>
    
    L'indirizzo IP del servizio Edge di Access è primario con il gateway predefinito impostato su router con accesso a Internet (131.107.155.1).
    
    Web Conferencing Edge service e gli indirizzi IP di un/V Edge service secondari.

<div>


> [!TIP]
> La configurazione di Edge Server con due schede di rete è una delle due opzioni. L'altra opzione consiste nell'usare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale. Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio Edge Server e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>Record DNS necessari per il bordo consolidato in scala, bilanciamento del carico hardware (esempio)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Posizione/tipo/porta</th>
<th>Record FQDN/DNS</th>
<th>Indirizzo IP/FQDN</th>
<th>Mapping a/commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Interfaccia esterna di Access Edge Services (contoso). Ripetere la procedura necessaria per tutti i domini SIP con gli utenti abilitati a Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interfaccia esterna di Web Conferencing Edge service</p></td>
</tr>
<tr class="odd">
<td><p>DNS esterno/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Interfaccia esterna di un/V Edge service</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/SRV/443</p></td>
<td><p>_sip. _tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaccia esterna di Access Edge Services. Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per l'utilizzo esterno. Ripetere le esigenze per tutti i domini SIP con gli utenti abilitati a Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS esterno/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaccia esterna SIP Access Edge service necessaria per l'individuazione automatica di DNS dei partner federati noti come "dominio SIP consentito" (chiamata federazione avanzata nelle versioni precedenti). Ripetere le operazioni necessarie per tutti i domini SIP con gli utenti abilitati a Lync e i client di Microsoft Lync mobile che usano il servizio di notifica push o il servizio di notifica push Apple</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interfaccia interna del bordo consolidato</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

