---
title: 'Lync Server 2013: Riepilogo di DNS - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f748f8107e4d1c0da41a07285eb61e4a3149551
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>Riepilogo di DNS - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2017-03-09_

I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono abbastanza semplici rispetto a quelli per i certificati e le porte. Inoltre, molti record sono facoltativi, a seconda di come si configurano i client che usano Lync 2013 e se si Abilita la Federazione.

Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Per informazioni dettagliate sulla configurazione della configurazione automatica dei client di Lync 2013 se non è configurato il DNS split-brain, vedere la sezione "configurazione automatica senza DNS divisa" in [determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

La tabella seguente contiene un riepilogo dei record DNS necessari per supportare la singola topologia perimetrale consolidata visualizzata nella figura singola topologia perimetrale consolidata. Tieni presente che alcuni record DNS sono necessari solo per la configurazione automatica dei client di Lync 2013. Se si prevede di usare gli oggetti Criteri di gruppo per configurare i client Lync, i record associati non sono necessari.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisiti della scheda di rete Edge Server

Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete negli Edge Server e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna. Ad esempio, come illustrato nella figura scenario di Edge consolidato in scala [consolidata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , il gateway predefinito punta al firewall esterno.

È possibile configurare due schede di rete in ogni server perimetrale nel modo seguente:

  - **Scheda di rete 1-nodo 1 (interfaccia interna)**
    
    Interfaccia interna con 172.25.33.10 assegnati.
    
    Nessun gateway predefinito è definito.
    
    Verificare che esista una route dalla rete che contiene l'interfaccia interna di Edge a tutte le reti che contengono server che includono client Lync Server 2013 o Lync Server 2013, ad esempio da 172.25.33.0 a 192.168.10.0.

  - **Scheda di rete 1-nodo 2 (interfaccia interna)**
    
    Interfaccia interna con 172.25.33.11 assegnati.
    
    Nessun gateway predefinito è definito.
    
    Verificare che esista una route dalla rete che contiene l'interfaccia interna di Edge a tutte le reti che contengono server che includono client Lync Server 2013 o Lync Server 2013, ad esempio da 172.25.33.0 a 192.168.10.0.

  - **Scheda di rete 2 node 1 (interfaccia esterna)**
    
    Alla scheda di rete sono assegnati tre indirizzi IP privati, ad esempio 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge Services.
    
    L'indirizzo IP pubblico del servizio Edge di Access è primario con il set di gateway predefinito per il router pubblico (131.107.155.1).
    
    I servizi di Web Conferencing Edge e gli indirizzi IP privati del servizio Edge A/V sono indirizzi IP aggiuntivi nella sezione **Avanzate** delle proprietà di **Internet Protocol versione 4 (TCP/IPv4)** e **protocollo Internet versione 6 (TCP/IPv6)** delle **proprietà di connessione dell'area locale** in Windows Server.
    
    <div>
    

    > [!NOTE]  
    > È comunque possibile usare un singolo indirizzo IP per tutte le tre interfacce del servizio Edge. Anche se questo Salva gli indirizzi IP, richiede numeri di porta diversi per ogni servizio. Il numero di porta predefinito è 443/TCP, che garantisce che la maggior parte dei firewall remoti consentirà il traffico. La modifica dei valori della porta in (ad esempio) 5061/TCP per il servizio Access Edge, 444/TCP per il servizio Web Conferencing Edge e 443/TCP per il servizio A/V Edge può causare problemi per gli utenti remoti in cui un firewall che sta dietro non consente il traffico su 5061/TCP e 444/TCP. Inoltre, tre indirizzi IP distinti semplificano la risoluzione dei problemi grazie alla possibilità di filtrare in base all'indirizzo IP.

    
    </div>

  - **Scheda di rete 2 node 2 (interfaccia esterna)**
    
    Alla scheda di rete sono assegnati tre indirizzi IP privati, ad esempio 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge Services.
    
    L'indirizzo IP pubblico del servizio Edge di Access è primario con il set di gateway predefinito per il router pubblico (131.107.155.1).
    
    I servizi di Web Conferencing Edge e gli indirizzi IP privati del servizio Edge A/V sono indirizzi IP aggiuntivi nella sezione **Avanzate** delle proprietà di **Internet Protocol versione 4 (TCP/IPv4)** e **protocollo Internet versione 6 (TCP/IPv6)** delle **proprietà di connessione dell'area locale** in Windows Server.

<div>


> [!TIP]  
> La configurazione di Edge Server con due schede di rete è una delle due opzioni. L'altra opzione consiste nell'usare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale. Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio Edge Server e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a>Record DNS necessari per i bordi consolidati in scala, bilanciamento del carico DNS con indirizzi IP pubblici (esempio)

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
<td><p>131.107.155.10 e 131.107.155.11</p></td>
<td><p>Ripetizione dell'interfaccia esterna di Access Edge Services (contoso), se necessario per tutti i domini SIP con gli utenti abilitati a Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 e 131.107.155.21</p></td>
<td><p>Interfaccia esterna di Web Conferencing Edge service</p></td>
</tr>
<tr class="odd">
<td><p>DNS esterno/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 e 131.107.155.31</p></td>
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
<td><p>Interfaccia esterna di Access Edge service necessaria per l'individuazione automatica di DNS dei partner federati noti come "dominio SIP consentito" (chiamata federazione avanzata nelle versioni precedenti). Ripetere la procedura necessaria per tutti i domini SIP con gli utenti abilitati a Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 e 172.25.33.11</p></td>
<td><p>Interfaccia interna del bordo consolidato</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a>Record necessari per la Federazione


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
<th>FQDN</th>
<th>Indirizzo IP/record host FQDN</th>
<th>Mapping a/commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaccia esterna per SIP Access Edge service necessaria per l'individuazione automatica del DNS della Federazione ad altri potenziali partner federativi ed è nota come "domini SIP consentiti" (chiamata federazione avanzata nelle versioni precedenti).</p>
<div>

> [!IMPORTANT]  
> Ripetere le operazioni necessarie per tutti i domini SIP con gli utenti abilitati a Lync e i client di Microsoft Lync mobile che usano il servizio di notifica push o il servizio di notifica push Apple


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>Riepilogo DNS per il protocollo di messaggistica e presenza estensibile


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
<th>FQDN</th>
<th>Indirizzo IP/record host FQDN</th>
<th>Mapping a/commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/SRV/5269</p></td>
<td><p>_xmpp-server. _tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interfaccia esterna proxy XMPP nel pool di servizi o Edge di Access. Ripetere l'impostazione necessaria per tutti i domini SIP interni con gli utenti abilitati a Lync in cui è consentito il contatto con i contatti XMPP tramite la configurazione dei criteri di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o i criteri degli utenti applicati alla Utenti abilitati per Lync. Un dominio XMPP consentito deve essere configurato anche nei criteri dei partner federati XMPP. Vedere gli argomenti in <strong>vedere anche</strong> per ulteriori dettagli</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/A</p></td>
<td><p>xmpp.contoso.com (ad esempio)</p></td>
<td><p>Indirizzo IP del servizio Access Edge nell'Edge Server o nel pool di Edge che ospita il proxy XMPP</p></td>
<td><p>Punta al servizio di Access Edge o al pool di Edge che ospita il servizio proxy XMPP. In genere, il record SRV creato punterà al record host (A o AAAA)</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

