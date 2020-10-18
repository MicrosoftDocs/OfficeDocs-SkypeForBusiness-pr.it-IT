---
title: Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP pubblici
description: Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP pubblici.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f0787d894e741951fd220ef3b2a9fada8183b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572792"
---
# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP pubblici in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-03-09_

I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono relativamente semplici rispetto a quelli relativi ai certificati e alle porte. Inoltre, molti record sono facoltativi, a seconda del modo in cui vengono configurati i client che eseguono Lync 2013 e se si Abilita la Federazione.

Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Per informazioni dettagliate sulla configurazione automatica dei client che eseguono Lync 2013 se il DNS split-brain non è configurato, vedere la sezione relativa alla configurazione automatica senza Split-Brain DNS in [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Nella tabella seguente viene fornito un riepilogo dei record DNS necessari per supportare la topologia perimetrale consolidata singola illustrata nella relativa figura. Si noti che alcuni record DNS sono necessari solo per la configurazione automatica dei client Lync 2013 e Lync 2010. Se si prevede di utilizzare gli oggetti Criteri di gruppo per configurare i client Lync, i record di configurazione automatica associati non sono necessari.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisiti della scheda di rete per i server perimetrali

Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete nei server perimetrali e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna. Ad esempio, come illustrato nella singola topologia perimetrale consolidata con indirizzi IP pubblici in un [unico perimetro consolidato con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), il gateway predefinito potrebbe puntare al router esterno nel perimetro o nel firewall Internet che può fornire un indirizzo IP pubblico. La relazione di rete per le interfacce del server perimetrale è una relazione di route anziché una relazione NAT.

È possibile configurare due schede di rete all'interno del server perimetrale come segue:

  - **Scheda di rete 1 (interfaccia interna)**
    
    Interfaccia interna con indirizzo 172.25.33.10 assegnato.
    
    Non è specificato alcun gateway predefinito.
    
    Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a qualsiasi rete che contiene server che eseguono i client Lync 2013 o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0).

  - **Scheda di rete 2 (interfaccia esterna)**
    
    A questa scheda di rete sono assegnati tre indirizzi IP pubblici, ad esempio 131.107.155.10 per Access Edge, 131.107.155.20 per Web Conferencing Edge, 131.107.155.30 per AV Edge.
    
    <div>
    

    > [!NOTE]
    > È possibile, sebbene non consigliabile, utilizzare un unico indirizzo IP per le tre interfacce del servizio Edge. Sebbene in questo modo sia possibile risparmiare indirizzi IP, è necessario un numero di porta separato per ciascun servizio. Il numero di porta predefinito è 443/TCP, porta questa che permette anche ai firewall più remoti di consentire il traffico. Se si cambia il valore delle porte, come ad esempio 5061/TCP per l'Access Edge, 444/TCP per il Web Conferencing Edge e 443/TCP A/V Edge, si potrebbero causare problemi agli utenti remoti qualora il firewall dietro il quale essi si trovano non consentisse il traffico su 5061/TCP e 444/TCP. Inoltre, la presenza di tre indirizzi IP differenti semplifica la risoluzione dei problemi, poiché questa è in grado di filtrare a seconda dell'indirizzo IP.

    
    </div>
    
    L'indirizzo IP pubblico di Access Edge è quello primario, con il gateway predefinito impostato sul router pubblico (131.107.155.1).
    
    Gli indirizzi IP pubblici di Web conferencing e A/V Edge sono indirizzi IP aggiuntivi nella sezione **Avanzate** delle proprietà di **Internet Protocol Version 4 (TCP/IPv4)** e **Internet Protocol Version 6 (TCP/IPv6)** delle **Proprietà LAN** in Windows Server.

<div>


> [!TIP]
> La configurazione del server perimetrale con due schede di rete è una delle due opzioni. L'altra opzione consiste nell'utilizzare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale. Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio server perimetrale e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a>Record DNS necessari per la topologia perimetrale singola con indirizzi IP pubblici (esempio)

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
<th>FQDN/Record DNS</th>
<th>Indirizzo IP/FQDN</th>
<th>Mapping a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Interfaccia esterna di Access Edge (Contoso). Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interfaccia esterna Web Conferencing Edge Server</p></td>
</tr>
<tr class="odd">
<td><p>DNS esterno/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Interfaccia esterna A/V Edge Server</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/SRV/443</p></td>
<td><p>_sip _sip._tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaccia esterna di Access Edge. Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per funzionare esternamente. Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS esterno/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaccia esterna SIP di Access Edge. Necessaria per l'individuazione DNS automatica di partner federati, nota come dominio SIP consentito, nonché come federazione avanzata nelle versioni precedenti. Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interfaccia interna perimetrale consolidata</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> I record elencati nella tabella precedente sono visualizzati con estensione <EM>net</EM> o <EM>com</EM>, per evidenziare la zona in cui devono trovarsi se non si utilizza il DNS di tipo split brain. Se si utilizza il DNS di tipo split brain, tutti i record devono trovarsi nella stessa zona, con l'unica distinzione tra versione interna ed esterna. Per informazioni dettagliate, vedere "DNS split-brain" in <A href="lync-server-2013-determine-dns-requirements.md">determine DNS requirements for Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="records-required-for-federation"></a>Record necessari per la federazione


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
<th>Indirizzo IP/FQDN record host</th>
<th>Mapping a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaccia esterna SIP di Access Edge. Necessaria per l'individuazione DNS automatica di partner federati, nota come dominio SIP consentito, nonché come federazione avanzata nelle versioni precedenti. Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</p>



> [!IMPORTANT]
> Questo record SRV è necessario per la mobilità e il fornitore di servizi di accesso a terze parti delle notifiche push

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>Riepilogo DNS per il protocollo XMPP


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
<th>Indirizzo IP/FQDN record host</th>
<th>Mapping a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/SRV/5269</p></td>
<td><p>_xmpp-server._tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interfaccia esterna del proxy XMPP nel servizio Access Edge o nel pool di server perimetrali. Ripetere quanto necessario per tutti i domini SIP interni con gli utenti abilitati per Lync, in cui è consentito il contatto con i contatti XMPP tramite la configurazione del criterio di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o il criterio utente applicato all'utente abilitato per Lync. Un dominio XMPP consentito deve inoltre essere configurato nel criterio dei partner XMPP federati. Per informazioni dettagliate, vedere gli argomenti in <strong>Vedere anche</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/A</p></td>
<td><p>xmpp.contoso.com (esempio)</p></td>
<td><p>Indirizzo IP del servizio Access Edge nel server perimetrale o nel pool perimetrale che ospita il proxy XMPP</p></td>
<td><p>Punta al servizio Access Edge o al pool di server perimetrali che ospita il servizio proxy XMPP. Il record SRV creato punterà a questo record host (A o AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

