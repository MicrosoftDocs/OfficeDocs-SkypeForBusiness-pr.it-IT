---
title: Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c3c111ef2518d159719426dfadd6c070f246349
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-03-09_

I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono relativamente semplici rispetto a quelli relativi ai certificati e alle porte. Inoltre, molti record sono facoltativi, a seconda del modo in cui vengono configurati i client che eseguono Lync 2013 e se si Abilita la Federazione.

Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Per informazioni dettagliate sulla configurazione automatica dei client che eseguono Lync 2013 se il DNS split-brain non è configurato, vedere la sezione relativa alla configurazione automatica senza DNS split-brain in [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Nella tabella seguente viene fornito un riepilogo dei record DNS necessari per supportare la topologia perimetrale consolidata singola illustrata nella relativa figura. Si noti che alcuni record DNS sono necessari solo per la configurazione automatica dei client Lync 2013 e Lync 2010. Se si prevede di utilizzare gli oggetti Criteri di gruppo per configurare i client Lync, i record di configurazione automatica associati non sono necessari.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisiti della scheda di rete per i server perimetrali

Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete nei server perimetrali e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna. Ad esempio, come illustrato nella singola topologia perimetrale consolidata in un [unico perimetro consolidato con indirizzi IP privati e NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), il gateway predefinito dovrebbe puntare al firewall esterno (10.45.16.1).

È possibile configurare due schede di rete all'interno del server perimetrale come segue:

  - **Scheda di rete 1 (interfaccia interna)**
    
    Interfaccia interna con indirizzo 172.25.33.10 assegnato.
    
    Non è specificato alcun gateway predefinito.
    
    Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a qualsiasi rete che contiene server che eseguono i client Lync 2013 o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0).

  - **Scheda di rete 2 (interfaccia esterna)**
    
    A questa scheda di rete sono assegnati tre indirizzi IP privati, ad esempio 10.45.16.10 per Access Edge, 10.45.16.20 per Web Conferencing Edge e 10.45.16.30 per AV Edge
    
    <div>
    

    > [!NOTE]
    > È possibile, ma non consigliabile, utilizzare un solo indirizzo IP per tutte e tre le interfacce dei servizi Edge. Sebbene questa scelta consenta di risparmiare indirizzi IP, richiede numeri di porta diversi per ogni servizio. Il numero di porta predefinito è 443/TCP e garantisce che la maggior parte dei firewall remoti consenta il traffico. L'impostazione dei valori di porta ad esempio su 5061/TCP per Access Edge, 444/TCP per Web Conferencing Edge e 443/TCP per AV Edge può causare problemi per gli utenti remoti se un firewall da cui sono protetti non consente il traffico su 5061/TCP e 444/TCP. L'utilizzo di tre indirizzi IP distinti inoltre facilita la risoluzione dei problemi perché i dati possono essere filtrati in base all'indirizzo IP.

    
    </div>
    
    L'indirizzo IP di Access Edge è primario, con gateway predefinito impostato sul router integrato (10.45.16.1).
    
    Gli indirizzi di Web Conferencing e A/V Edge sono secondari.

<div>


> [!TIP]
> La configurazione del server perimetrale con due schede di rete è una delle due opzioni. L'altra opzione consiste nell'utilizzare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale. Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio server perimetrale e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a>Record DNS necessari per un server perimetrale consolidato singolo con indirizzi IP privati e NAT (esempio)

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
<td><p>Interfaccia esterna Access Edge (Contoso). Ripetere secondo le necessità per tutti i domini SIP con utenti abilitati per Lync.</p></td>
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
<td><p>_sip. _tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaccia esterna di Access Edge. Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per funzionare esternamente. Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS esterno/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
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
> I record elencati nella tabella precedente sono visualizzati con estensione <EM>net</EM> o <EM>com</EM> per evidenziare la zona in cui devono trovarsi se non si utilizza DNS di tipo split brain. Se si utilizza DNS di tipo split brain, tutti i record devono trovarsi nella stessa zona <EM>com</EM>, con l'unica distinzione tra versione interna ed esterna della zona DNS. Per informazioni dettagliate, vedere "DNS split-brain" in <A href="lync-server-2013-determine-dns-requirements.md">determine DNS requirements for Lync Server 2013</A>.



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
<th>Si mappa a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
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
<th>Si mappa a/Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS esterno/SRV/5269</p></td>
<td><p>_xmpp-server. _tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interfaccia esterna del proxy XMPP nel servizio Access Edge o nel pool di server perimetrali. Ripetere quanto necessario per tutti i domini SIP interni con gli utenti abilitati per Lync, in cui è consentito il contatto con i contatti XMPP tramite la configurazione del criterio di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o il criterio utente applicato all' Utente abilitato per Lync. Un dominio XMPP consentito deve inoltre essere configurato nel criterio dei partner XMPP federati. Per informazioni dettagliate, vedere gli argomenti in <strong>Vedere anche</strong></p></td>
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

