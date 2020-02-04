---
title: 'Lync Server 2013: Requisiti relativi al servizio di bilanciamento del carico hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ed4195d80ecc755faea74ddedb790c9f41ebfb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Requisiti relativi al servizio di bilanciamento del carico hardware per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-05-11_

La topologia di Edge consolidato di Lync Server 2013 è ottimizzata per il bilanciamento del carico DNS per le nuove distribuzioni federative principalmente con altre organizzazioni che usano Lync Server. Se è necessaria una disponibilità elevata per uno degli scenari seguenti, è necessario usare un bilanciamento del carico hardware nei pool di Edge Server per gli elementi seguenti:

  - Federazione con organizzazioni che usano Office Communications Server 2007 R2 o Office Communications Server 2007

  - Messaggistica unificata di Exchange per utenti remoti con messaggistica unificata di Exchange prima di Exchange 2010 con SP1

  - Connettività agli utenti di messaggistica istantanea pubblica

<div>


> [!IMPORTANT]  
> L'uso del bilanciamento del carico DNS su un'interfaccia e il bilanciamento del carico hardware dall'altro non è supportato. È necessario usare il bilanciamento del carico hardware per entrambe le interfacce o il bilanciamento del carico DNS per entrambi.



</div>

<div>


> [!NOTE]  
> Se si usa un sistema di bilanciamento del carico hardware, il servizio di bilanciamento del carico distribuito per le connessioni con la rete interna deve essere configurato per il bilanciamento del carico solo del traffico verso i server che esegue Access Edge e il servizio A/V Edge. Non può caricare il bilanciamento del traffico verso il servizio Web Conferencing Edge interno o il servizio proxy XMPP interno.



</div>

<div>


> [!NOTE]  
> La NAT DSR (Direct Server Return) non è supportata con Lync Server 2013.



</div>

Per determinare se il dispositivo di bilanciamento del carico hardware supporta le funzionalità necessarie per Lync Server 2013, vedere "partner di bilanciamento del carico di Lync Server [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)2010".

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisiti di bilanciamento del carico hardware per i server perimetrali che utilizzano il servizio A/V Edge

Di seguito sono riportati i requisiti di bilanciamento del carico hardware per Edge Server che esegue il servizio A/V Edge:

  - Disattivare TCP nagling per le porte interne ed esterne 443. Nagling è il processo di combinazione di diversi piccoli pacchetti in un singolo pacchetto più grande per una trasmissione più efficiente.

  - Disattivare TCP nagling per l'intervallo di porte esterne 50.000-59.999.

  - Non usare NAT sul firewall interno o esterno.

  - L'interfaccia interna del bordo deve essere in una rete diversa rispetto all'interfaccia esterna del server perimetrale e il routing tra di essi deve essere disabilitato.

  - L'interfaccia esterna dell'Edge Server che usa il servizio A/V Edge deve usare indirizzi IP instradabili pubblicamente e nessuna traduzione NAT o Port in uno degli indirizzi IP esterni di Edge.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Requisiti di bilanciamento del carico hardware

I requisiti di affinità basati su cookie sono notevolmente ridotti in Lync Server 2013 per i servizi Web. Se si distribuisce Lync Server 2013 e non vengono mantenuti i server front end o i pool Front-End di Lync Server 2010, non è necessaria la persistenza basata su cookie. Se tuttavia si mantengono temporaneamente o definitivamente tutti i server front-end di Lync Server 2010 o i pool Front-End, è comunque possibile usare la persistenza basata su cookie mentre viene distribuita e configurata per Lync Server 2010.

<div>


> [!NOTE]  
> <STRONG>Se si decide di usare l'affinità basata su cookie anche se la distribuzione non lo richiede</STRONG>, non c'è alcun impatto negativo.



</div>

Per le distribuzioni che **non useranno** l'affinità basata su cookie:

  - Nella regola di pubblicazione del proxy inverso per la porta 4443 impostare **Inoltra intestazione host** su true. In questo modo verrà inoltrato l'URL originale.

Per le distribuzioni **che** utilizzeranno l'affinità basata su cookie:

  - Nella regola di pubblicazione del proxy inverso per la porta 4443 impostare **Inoltra intestazione host** su true. In questo modo verrà inoltrato l'URL originale.

  - Il cookie di bilanciamento del carico hardware non deve essere contrassegnato httpOnly

  - Il cookie di bilanciamento del carico hardware non deve avere una data di scadenza

  - Il cookie di bilanciamento del carico hardware deve essere denominato **MS-WSMan** (questo è il valore previsto per i servizi Web e non può essere modificato)

  - Il cookie di bilanciamento del carico hardware deve essere impostato in tutte le risposte HTTP per cui la richiesta HTTP in arrivo non ha un cookie, indipendentemente dal fatto che una risposta HTTP precedente alla stessa connessione TCP abbia già ottenuto un cookie. Se il bilanciamento del carico ottimizza l'inserimento del cookie per eseguire una sola volta per ogni connessione TCP, non deve essere usata l'ottimizzazione.

<div>


> [!NOTE]  
> Le tipiche configurazioni di bilanciamento del carico hardware usano l'affinità degli indirizzi di origine e la durata di una sessione TCP di 20 minuti, che va bene per i client Lync Server e Lync 2013, perché lo stato della sessione viene gestito tramite l'utilizzo del client e/o l'interazione tra applicazioni.



</div>

Se si distribuiscono dispositivi mobili, il dispositivo di bilanciamento del carico hardware deve essere in grado di bilanciare il carico delle singole richieste all'interno di una sessione TCP (in effetti, è necessario essere in grado di bilanciare il carico di una singola richiesta in base all'indirizzo IP di destinazione).

<div>


> [!WARNING]  
> I servizi di bilanciamento del carico hardware F5 hanno una caratteristica denominata OneConnect che garantisce che ogni richiesta all'interno di una connessione TCP sia bilanciata individualmente. Se si distribuiscono dispositivi mobili, verificare che il fornitore del dispositivo di bilanciamento del carico hardware supporti le stesse funzionalità. Le più recenti app per dispositivi mobili Apple iOS richiedono Transport Layer Security (TLS) versione 1,2. F5 offre impostazioni specifiche per questo.<BR>Per informazioni dettagliate sui dispositivi di bilanciamento del carico hardware di terze parti, vedere<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

Di seguito sono riportati i requisiti di bilanciamento del carico hardware per i servizi Web Director e front end pool:

  - Per i VIP dei servizi Web interni,\_imposta la persistenza degli indirizzi di origine (porta interna 80, 443) nel servizio di bilanciamento del carico hardware. Per Lync Server 2013, la\_persistenza degli indirizzi di origine indica che più connessioni provenienti da un singolo indirizzo IP vengono sempre inviate a un server per mantenere lo stato della sessione.

  - Usare il timeout di inattività TCP di 1800 secondi.

  - Nel firewall tra il proxy inverso e il bilanciamento del carico hardware del pool hop successivo creare una regola per consentire HTTPS: traffico sulla porta 4443, dal proxy inverso al bilanciamento del carico hardware. Il bilanciamento del carico hardware deve essere configurato per l'ascolto sulle porte 80, 443 e 4443.

<div>


> [!IMPORTANT]  
> Per ulteriori informazioni sulla configurazione dell'utilità di bilanciamento del carico hardware, vedere la pagina relativa a <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Edge consolidato con bilanciamento del carico hardware in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Riepilogo dei requisiti di affinità di bilanciamento del carico hardware


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Posizione client/utente</th>
<th>Requisiti di affinità FQDN servizi Web esterni</th>
<th>Requisiti di affinità FQDN servizi Web interni</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Web App (utenti interni ed esterni)</p>
<p>Dispositivo mobile (utenti interni ed esterni)</p></td>
<td><p>Nessuna affinità</p></td>
<td><p>Affinità indirizzo di origine</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App (solo utenti esterni)</p>
<p>Dispositivo mobile (utenti interni ed esterni)</p></td>
<td><p>Nessuna affinità</p></td>
<td><p>Affinità indirizzo di origine</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App (solo utenti interni)</p>
<p>Dispositivo mobile (non distribuito)</p></td>
<td><p>Nessuna affinità</p></td>
<td><p>Affinità indirizzo di origine</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>Monitoraggio della porta per i dispositivi di bilanciamento del carico hardware

Puoi definire il monitoraggio della porta sui dispositivi di bilanciamento del carico hardware per determinare quando i servizi specifici non sono più disponibili a causa di problemi hardware o comunicazioni. Ad esempio, se il servizio server front-end (RTCSRV) si arresta perché il server front-end o il pool Front-end non riesce, il monitoraggio di HLB dovrebbe interrompere anche la ricezione del traffico sui servizi Web. Puoi implementare il monitoraggio della porta in HLB per monitorare le operazioni seguenti:

### <a name="front-end-server-user-pool--hlb-internal-interface"></a>Pool di utenti del server front-end-interfaccia interna di HLB

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
<th>IP virtuale/porta</th>
<th>Porta nodi</th>
<th>Nodo macchina/monitor</th>
<th>Profilo di persistenza</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;Web&gt;pool-int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Fonte</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;Web&gt;pool-int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Fonte</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>Pool di utenti del server front-end-interfaccia esterna di HLB

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
<th>IP virtuale/porta</th>
<th>Porta nodi</th>
<th>Nodo macchina/monitor</th>
<th>Profilo di persistenza</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;web_mco_443_vs&gt;del pool</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Nessuno</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;web_mco_80_vs&gt;del pool</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Nessuno</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

