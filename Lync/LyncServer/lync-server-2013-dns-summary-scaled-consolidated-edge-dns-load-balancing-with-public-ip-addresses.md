---
title: 'Lync Server 2013: Consolidated Edge in scala di riepilogo DNS, bilanciamento del carico DNS con indirizzi IP pubblici'
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
ms.openlocfilehash: 48dab867ac7ae408f544e4dbc6bc55ff555e20a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>Server perimetrale consolidato in scala di riepilogo DNS, bilanciamento del carico DNS con indirizzi IP pubblici in Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-03-09_

I requisiti dei record DNS per l'accesso remoto a Lync Server 2013 sono relativamente semplici rispetto a quelli relativi ai certificati e alle porte. Inoltre, molti record sono facoltativi, a seconda del modo in cui vengono configurati i client che eseguono Lync 2013 e se si Abilita la Federazione.

Per informazioni dettagliate sui requisiti DNS di Lync 2013, vedere [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Per informazioni dettagliate sulla configurazione automatica dei client Lync 2013 se il DNS split-brain non è configurato, vedere la sezione "configurazione automatica senza DNS split brain" in [determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Nella tabella seguente viene fornito un riepilogo dei record DNS necessari per supportare la topologia perimetrale consolidata singola illustrata nella relativa figura. Si noti che alcuni record DNS sono necessari solo per la configurazione automatica dei client Lync 2013. Se si prevede di utilizzare gli oggetti Criteri di gruppo per configurare i client Lync, i record associati non sono necessari.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisiti della scheda di rete per i server perimetrali

Per evitare problemi di routing, verificare che siano presenti almeno due schede di rete nei server perimetrali e che il gateway predefinito sia impostato solo sulla scheda di rete associata all'interfaccia esterna. Ad esempio, come illustrato nella figura dello scenario dei server perimetrali in scala consolidato in [scala consolidata perimetrale, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , il gateway predefinito dovrebbe puntare al firewall esterno.

È possibile configurare due schede di rete in ogni server perimetrale, come illustrato di seguito:

  - **Scheda di rete 1 - Nodo 1 (interfaccia interna)**
    
    Interfaccia interna con indirizzo 172.25.33.10 assegnato.
    
    Nessun gateway predefinito definito.
    
    Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a qualsiasi rete che contiene server che eseguono i client Lync 2013 o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0).

  - **Scheda di rete 1 - Nodo 2 (interfaccia interna)**
    
    Interfaccia interna con indirizzo 172.25.33.11 assegnato.
    
    Non è specificato alcun gateway predefinito.
    
    Verificare che esista una route dalla rete che contiene l'interfaccia interna del server perimetrale a qualsiasi rete che contiene server che eseguono i client Lync 2013 o Lync Server 2013 (ad esempio, da 172.25.33.0 a 192.168.10.0).

  - **Scheda di rete 2 - Nodo 1 (interfaccia esterna)**
    
    A questa scheda di rete sono assegnati tre indirizzi IP privati, ad esempio 131.107.155.10 per il servizio Access Edge, 131.107.155.20 per il servizio Web Conferencing Edge, 131.107.155.30 per il servizio A/V Edge.
    
    L'indirizzo IP pubblico del servizio Access Edge è primario, con gateway predefinito impostato sul router pubblico (131.107.155.1).
    
    I servizi Web Conferencing Edge e gli indirizzi IP privati del servizio A/V Edge sono indirizzi IP aggiuntivi nella sezione **Advanced** delle proprietà del **protocollo Internet versione 4 (TCP/IPv4)** e del **protocollo Internet versione 6 (TCP/IPv6)** delle **proprietà della connessione all'area locale** in Windows Server.
    
    <div>
    

    > [!NOTE]  
    > È possibile, anche se non consigliabile, utilizzare un singolo indirizzo IP per tutte e tre le interfacce dei servizi perimetrali. Benché in questo modo sia possibile utilizzare meno indirizzi IP, vengono richiesti numeri di porte diversi per ogni servizio. Il numero di porta predefinito è 443/TCP, che garantisce il passaggio del traffico attraverso i firewall più remoti. Se si modificano i valori delle porte su (ad esempio) 5061/TCP per il servizio Access Edge, 444/TCP per il servizio Web Conferencing Edge e 443/TCP per il servizio A/V Edge potrebbe causare problemi per gli utenti remoti in cui un firewall che sono dietro non consente il traffico su 5061/TCP e 444/TCP. L'utilizzo di tre indirizzi IP distinti inoltre semplifica la risoluzione dei problemi poiché consente di applicare un filtro in base all'indirizzo IP.

    
    </div>

  - **Scheda di rete 2 - Nodo 2 (interfaccia esterna)**
    
    A questa scheda di rete sono assegnati tre indirizzi IP privati, ad esempio 131.107.155.11 per il servizio Access Edge, 131.107.155.21 per il servizio Web Conferencing Edge, 131.107.155.31 per il servizio A/V Edge.
    
    L'indirizzo IP pubblico del servizio Access Edge è primario, con gateway predefinito impostato sul router pubblico (131.107.155.1).
    
    I servizi Web Conferencing Edge e gli indirizzi IP privati del servizio A/V Edge sono indirizzi IP aggiuntivi nella sezione **Advanced** delle proprietà del **protocollo Internet versione 4 (TCP/IPv4)** e del **protocollo Internet versione 6 (TCP/IPv6)** delle **proprietà della connessione all'area locale** in Windows Server.

<div>


> [!TIP]  
> La configurazione del server perimetrale con due schede di rete è una delle due opzioni. L'altra opzione consiste nell'utilizzare una scheda di rete per il lato interno e tre schede di rete per il lato esterno del server perimetrale. Il vantaggio principale di questa opzione è una scheda di rete distinta per ogni servizio server perimetrale e una raccolta di dati potenzialmente più concisa quando è necessaria la risoluzione dei problemi



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a>Record DNS necessari per topologia perimetrale consolidata con scalabilità implementata e bilanciamento del carico DNS con indirizzi IP pubblici (esempio)

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
<td><p>131.107.155.10 e 131.107.155.11</p></td>
<td><p>Ripetizione dell'interfaccia esterna del servizio Access Edge (contoso) come necessario per tutti i domini SIP con gli utenti abilitati per Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 e 131.107.155.21</p></td>
<td><p>Interfaccia esterna del servizio Web Conferencing Edge</p></td>
</tr>
<tr class="odd">
<td><p>DNS esterno/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 e 131.107.155.31</p></td>
<td><p>Interfaccia esterna del servizio A/V Edge</p></td>
</tr>
<tr class="even">
<td><p>DNS esterno/SRV/443</p></td>
<td><p>_sip. _tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaccia esterna del servizio Access Edge. Necessario per la configurazione automatica dei client Lync 2013 e Lync 2010 per funzionare esternamente. Ripetere secondo necessità per tutti i domini SIP con utenti abilitati per Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS esterno/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaccia esterna del servizio Access Edge necessario per l'individuazione automatica del DNS dei partner federati noti come "dominio SIP consentito" (denominato Federazione avanzata nelle versioni precedenti). Ripetere per tutti i domini SIP con utenti abilitati per Lync, se necessario.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 e 172.25.33.11</p></td>
<td><p>Interfaccia interna del server perimetrale consolidato.</p></td>
</tr>
</tbody>
</table>


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
<td><p>Interfaccia esterna del servizio Access Edge SIP necessaria per l'individuazione automatica dei DNS della Federazione verso altri potenziali partner di federazione ed è nota come "domini SIP consentiti" (denominata Federazione avanzata nelle versioni precedenti).</p>
<div>

> [!IMPORTANT]  
> Ripetere quanto necessario per tutti i domini SIP con gli utenti abilitati per Lync e i client Microsoft Lync mobile che utilizzano il servizio di notifica push o il servizio di notifica push di Apple


</div></td>
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

