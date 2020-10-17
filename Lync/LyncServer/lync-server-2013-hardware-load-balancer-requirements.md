---
title: Requisiti per il bilanciamento del carico hardware di Lync Server 2013
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
ms.openlocfilehash: 5c4aac657dd1e472068474a3a70d17f1a2a38c63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530873"
---
# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Requisiti per il bilanciamento del carico hardware per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-05-11_

La topologia perimetrale consolidata di Lync Server 2013 è ottimizzata per il bilanciamento del carico DNS per le nuove distribuzioni che si riferiscono principalmente ad altre organizzazioni che utilizzano Lync Server. Se è richiesta la disponibilità elevata per uno degli scenari seguenti, sarà necessario utilizzare un dispositivo di bilanciamento del carico hardware nei pool di server perimetrali nei casi seguenti:

  - Federazione con organizzazioni che utilizzano Office Communications Server 2007 R2 o Office Communications Server 2007

  - Messaggistica unificata di Exchange per gli utenti remoti tramite messaggistica unificata di Exchange prima di Exchange 2010 con SP1

  - Connettività con utenti di messaggistica istantanea pubblica

<div>


> [!IMPORTANT]  
> Non è possibile usare il bilanciamento del carico DNS in un'interfaccia e il bilanciamento del carico hardware in un'altra. È necessario usare lo stesso tipo di bilanciamento del carico per entrambe le interfacce, in quanto non è supportata una combinazione dei due tipi.



</div>

<div>


> [!NOTE]  
> Se si usa un servizio di bilanciamento del carico hardware, il bilanciamento del carico distribuito per le connessioni con la rete interna deve essere configurato per bilanciare il carico solo del traffico verso i server che eseguono i servizi Access Edge e A/V Edge. Non è possibile bilanciare il carico del traffico verso il servizio Web Conferencing Edge interno o il servizio del proxy XMPP interno.



</div>

<div>


> [!NOTE]  
> Il protocollo DSR (Direct Server Return) NAT non è supportato con Lync Server 2013.



</div>

Per determinare se il dispositivo di bilanciamento del carico hardware supporta le funzionalità necessarie per Lync Server 2013, vedere la sezione relativa ai partner di bilanciamento del carico di Lync Server 2010 all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisiti dei servizi di bilanciamento del carico hardware per i server perimetrali che eseguono il servizio A/V Edge

Di seguito sono riportati i requisiti per il bilanciamento del carico hardware per i server perimetrali che eseguono il servizio A/V Edge:

  - Disattivare il nagling TCP per le porte 443 interne ed esterne. Per nagling si intende il processo di combinazione di più pacchetti di piccole dimensioni in un singolo pacchetto di dimensioni maggiori per una trasmissione più efficiente.

  - Disattivare il nagling TCP per l'intervallo di porte esterne compreso tra 50.000 e 59.999.

  - Non utilizzare NAT nel firewall interno o esterno.

  - L'interfaccia interna perimetrale deve trovarsi in una rete diversa rispetto all'interfaccia esterna del server perimetrale e il routing tra di esse deve essere disabilitato.

  - L'interfaccia esterna del server perimetrale che esegue il servizio A/V Edge deve utilizzare gli indirizzi IP instradabili pubblicamente e non la conversione NAT o la porta su uno degli indirizzi IP esterni perimetrali.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Requisiti relativi al servizio di bilanciamento del carico hardware

I requisiti di affinità basati su cookie sono notevolmente ridotti in Lync Server 2013 per i servizi Web. Se si sta distribuendo Lync Server 2013 e non si conservano i server Lync Server 2010 front end o i pool Front End, non è necessaria la persistenza basata su cookie. Tuttavia, se si conservano temporaneamente o definitivamente i server front end o i pool Front-End di Lync Server 2010, è comunque possibile utilizzare la persistenza basata su cookie come è stata distribuita e configurata per Lync Server 2010.

<div>


> [!NOTE]  
> <STRONG>La decisione di usare l'affinità basata sui cookie anche se la distribuzione non la richiede</STRONG> non determina un impatto negativo.



</div>

Per le distribuzioni in cui l'affinità basata sui cookie **non verrà usata**:

  - Nella regola di pubblicazione del proxy inverso per la porta 4443, impostare **Forward host header** su True in modo da assicurarsi che l'URL originale venga inoltrato.

Per le distribuzioni in cui l'affinità basata sui cookie **verrà usata**:

  - Nella regola di pubblicazione del proxy inverso per la porta 4443, impostare **Forward host header** su True in modo da assicurarsi che l'URL originale venga inoltrato.

  - Il cookie del bilanciamento del carico hardware NON DEVE essere contrassegnato come httpOnly

  - Per il bilanciamento del carico hardware NON DEVE essere impostata una data di scadenza

  - Il cookie del bilanciamento del carico hardware DEVE essere denominato **MS-WSMAN** ovvero il valore, non modificabile, previsto dai servizi Web

  - Il cookie del bilanciamento del carico hardware DEVE essere impostato in ogni risposta HTTP per la quale la richiesta HTTP in arrivo non presentava un cookie, indipendentemente dal fatto che una precedente risposta HTTP nella stessa connessione TCP abbia già ottenuto un cookie. Se il bilanciamento del carico ottimizza l'inserimento del cookie in modo che venga eseguito una sola volta per ogni connessione TCP, tale ottimizzazione NON DEVE essere usata

<div>


> [!NOTE]  
> Le configurazioni tipiche del dispositivo di bilanciamento del carico hardware utilizzano l'affinità degli indirizzi di origine e la durata di una sessione di 20 min. TCP, che va bene per i client Lync Server e Lync 2013 perché lo stato della sessione viene mantenuto tramite l'utilizzo del client e/o l'interazione tra applicazioni.



</div>

Se si distribuiscono dispositivi mobili, il servizio di bilanciamento del carico hardware deve essere in grado di bilanciare il carico delle singole richieste in una sessione TCP (in effetti, è necessario essere in grado di bilanciare il carico di una singola richiesta in base all'indirizzo IP di destinazione).

<div>


> [!WARNING]  
> I servizi di bilanciamento del carico hardware F5 presentano una funzionalità chiamata OneConnect che garantisce che il bilanciamento del carico venga eseguito per ogni singola richiesta all'interno di una connessione TCP. Se si distribuiscono dispositivi mobili, verificare che il fornitore di servizi di bilanciamento del carico hardware supporti la stessa funzionalità. Le applicazioni per dispositivi mobili Apple iOS più recenti richiedono TLS (Transport Layer Security) versione 1.2. F5 offre impostazioni specifiche a questo scopo.<BR>Per informazioni dettagliate sui dispositivi di bilanciamento del carico hardware di terze parti, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

Vengono riportati di seguito i requisiti dei servizi di bilanciamento del carico hardware per i servizi Web dei pool di server Director e Front End:

  - Per i VIP dei servizi Web interni, impostare \_ la persistenza dell'indirizzo di origine (porta interna 80, 443) nel dispositivo di bilanciamento del carico hardware. Per Lync Server 2013, la \_ persistenza dell'addr di origine implica che più connessioni provenienti da un singolo indirizzo IP vengano sempre inviate a un solo server per mantenere lo stato della sessione.

  - Impostare il timeout di inattività TCP su 1800 secondi.

  - Nel firewall tra il proxy inverso e il servizio di bilanciamento del carico hardware del pool di hop successivi, creare una regola per consentire il traffico HTTPS nella porta 4443, dal proxy inverso al servizio di bilanciamento del carico hardware. Il servizio di bilanciamento del carico hardware deve essere configurato per l'ascolto sulle porte 80, 443 e 4443.

<div>


> [!IMPORTANT]  
> Per ulteriori informazioni sulla configurazione del dispositivo di bilanciamento del carico hardware, leggere il <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">perimetro consolidato in scala di riepilogo delle porte con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Riepilogo dei requisiti per l'affinità del servizio di bilanciamento del carico hardware


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Posizione client/utente</th>
<th>Requisiti per l'affinità FQDN dei servizi Web esterni</th>
<th>Requisiti per l'affinità FQDN dei servizi Web interni</th>
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
<td><p>Lync Web App (solo per gli utenti interni)</p>
<p>Dispositivo mobile (non distribuito)</p></td>
<td><p>Nessuna affinità</p></td>
<td><p>Affinità indirizzo di origine</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>Monitoraggio delle porte per i servizi di bilanciamento del carico hardware

Il monitoraggio delle porte viene definito nei servizi di bilanciamento del carico hardware per stabilire quando determinati servizi non sono più disponibili a causa di un errore hardware o delle comunicazioni. Ad esempio, se il servizio front end server (RTCSRV) si interrompe perché il front end server o il pool Front End ha esito negativo, il monitoraggio di HLB dovrebbe anche interrompere la ricezione del traffico sui servizi Web. Il monitoraggio delle porte viene implementato nel servizio HLB per monitorare quanto segue:

### <a name="front-end-server-user-pool--hlb-internal-interface"></a>Pool di utenti front end server – interfaccia interna di HLB

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
<th>IP virtuale/Porta</th>
<th>Porta nodo</th>
<th>Computer/Monitor nodo</th>
<th>Profilo persistenza</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;int_mco_443_vs del pool &gt;</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>Front End</p>
<p>5061</p></td>
<td><p>Origine</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;int_mco_80_vs del pool &gt;</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>Front End</p>
<p>5061</p></td>
<td><p>Origine</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>Pool di utenti front end server – interfaccia esterna di HLB

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
<th>IP virtuale/Porta</th>
<th>Porta nodo</th>
<th>Computer/Monitor nodo</th>
<th>Profilo persistenza</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;web_mco_443_vs del pool &gt;</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>Front End</p>
<p>5061</p></td>
<td><p>Nessuno</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;web_mco_80_vs del pool &gt;</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>Front End</p>
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

