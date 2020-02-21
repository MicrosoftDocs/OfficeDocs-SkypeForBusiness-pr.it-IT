---
title: 'Lync Server 2013: determinare i requisiti DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3f1bc8cd839b986a4830ad32f797835c56e9ebd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a>Determinare i requisiti DNS per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Utilizzare il diagramma di flusso seguente per determinare i requisiti DNS (Domain Name System). Le modifiche per gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 sono note in cui si applicano.

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 supporta l'utilizzo dell'indirizzamento IPv6. Per utilizzare gli indirizzi IPv6, è inoltre necessario fornire il supporto per DNS IPv6 e configurare i record host DNS AAAA (noti come "Quad-A"). Nelle distribuzioni in cui vengono utilizzati sia IPv4 che IPv6, è preferibile configurare e gestire entrambi i record host A per IPv4 e host AAAA per IPv6. Anche se la distribuzione è stata completata completamente in IPv6, è possibile che i record host DNS IPv4 siano ancora necessari quando gli utenti esterni utilizzano ancora IPv4.



</div>

**Determinazione del diagramma di flusso dei requisiti DNS**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> Per impostazione predefinita, il nome del computer di un computer che non è aggiunto a un dominio è un nome host e non un nome di dominio completo (FQDN). Generatore di topologie utilizza FQDN, non nomi host. Pertanto, è necessario configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale non aggiunto a un dominio. Quando si assegnano FQDN dei server Lync, server perimetrali e pool, <STRONG>utilizzare solo caratteri standard</STRONG> (tra cui a – z, a – z, 0 – 9 e segni meno). Non utilizzare caratteri Unicode o di sottolineatura. I caratteri non standard in un FQDN spesso non sono supportati dal DNS esterno e dalle CA pubbliche (ovvero, quando il nome di dominio completo deve essere assegnato a SN nel certificato). Per ulteriori informazioni, vedere <A href="lync-server-2013-configure-dns-host-records.md">configure DNS Host Records for Lync Server 2013</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Come i client Lync individuano i servizi

Microsoft Lync 2010, Lync 2013 e Lync mobile sono simili nel modo in cui il client trova e accede ai servizi in Lync Server 2013. L'eccezione notevole è l'app di Windows Store Lync che utilizza un processo di percorso del servizio diverso. In questa sezione vengono illustrati due scenari in cui i client individuano i servizi, in primo luogo il metodo tradizionale tramite una serie di record SRV e host, in secondo luogo utilizzando solo i record del servizio di individuazione automatica. Gli aggiornamenti cumulativi dei client desktop modificano il processo di percorso DNS da Lync Server 2010 per tutti i client, il processo di query DNS continua fino a quando non viene restituita una query completata oppure l'elenco dei record DNS possibili è esausto e viene restituito l'errore finale il client.

Per tutti i client **ad eccezione** dell'app di Windows Store Lync durante la ricerca DNS, i record SRV vengono interrogati e restituiti al client nell'ordine seguente:

1.  LyncdiscoverInternal. \<record\> del dominio a (host) per il servizio di individuazione automatica sui servizi Web interni

2.  Lyncdiscover. \<record\> del dominio a (host) per il servizio di individuazione automatica sui servizi Web esterni

3.  \_sipinternaltls. \_TCP. \<record\> Domain SRV (Service Locator) per le connessioni TLS interne

4.  \_sipinternal. \_TCP. \<record\> Domain SRV (Service Locator) per le connessioni TCP interne (eseguite solo se TCP è consentito)

5.  \_SIP. \_TLS. \<record\> Domain SRV (Service Locator) per connessioni TLS esterne

6.  sipinternal. \<record\> del dominio a (host) per il pool o il Director front end, risolvibile solo nella rete interna

7.  SIP. \<record\> del dominio a (host) per il pool Front end o il server Director nella rete interna oppure il servizio Access Edge quando il client è esterno

8.  sipexternal. \<record\> del dominio a (host) per il servizio Access Edge quando il client è esterno

L'app Lync Windows Store cambia completamente il processo perché utilizza due record:

1.  LyncdiscoverInternal. \<record\> del dominio a (host) per il servizio di individuazione automatica sui servizi Web interni

2.  Lyncdiscover. \<record\> del dominio a (host) per il servizio di individuazione automatica sui servizi Web esterni

Non è previsto alcun fallback per gli altri tipi di record.

La differenza tra i metodi utilizzati per i client più recenti rispetto ai client meno recenti è che il servizio di individuazione automatica sta diventando il metodo preferito per individuare tutti i servizi.

Quando una connessione ha esito positivo, il servizio di individuazione automatica restituisce tutti gli URL dei servizi Web per il pool principale dell'utente, incluso il servizio per dispositivi mobili (noto come MCX dalla directory virtuale creata per il servizio in IIS), Microsoft Lync Web App e gli URL dell'utilità di pianificazione Web. Tuttavia, sia l'URL del servizio per dispositivi mobili interno che l'URL del servizio per dispositivi mobili esterni è associato all'FQDN dei servizi Web esterni. Pertanto, indipendentemente dal fatto che un dispositivo mobile sia interno o esterno alla rete, il dispositivo si connette sempre al servizio per dispositivi mobili esternamente tramite il proxy inverso.

Se gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 sono stati installati, il servizio di individuazione automatica restituisce anche i riferimenti a Internal/UCWA, External/UCWA e UCWA. Queste voci si riferiscono al componente Web di Unified Communications Web API (UCWA). Al momento, viene utilizzata solo la voce UCWA e viene fornito un riferimento a un URL per il componente Web. UCWA viene utilizzato dai client per dispositivi mobili Lync 2013 anziché dal servizio per dispositivi mobili di MCX utilizzato dai client di telefonia mobile di Lync 2010.

<div>


> [!NOTE]  
> Quando si creano record SRV, è importante tenere presente che devono puntare a un record DNS a e AAAA (se si utilizza IPv6 Addressing) nello stesso dominio in cui viene creato il record DNS SRV. Ad esempio, se il record SRV è in contoso.com, il record A e AAAA (se si utilizza l'indirizzamento IPv6) indica che non può trovarsi in fabrikam.com.



</div>

<div>


> [!TIP]  
> La configurazione predefinita consiste nel indirizzare tutto il traffico client per dispositivi mobili tramite il sito esterno. È possibile modificare le impostazioni in modo da restituire solo l'URL interno, se questo è più preferibile per i requisiti. Con questa configurazione, gli utenti possono utilizzare le applicazioni di Lync mobile nei propri dispositivi mobili solo quando si trovano all'interno della rete aziendale. Per definire questa configurazione, è possibile utilizzare il cmdlet <STRONG>Set-CsMcxConfiguration</STRONG> .



</div>

<div>


> [!NOTE]  
> Anche se le applicazioni per dispositivi mobili possono connettersi ad altri servizi di Lync Server 2013, ad esempio il servizio Rubrica, le richieste Web interne dell'applicazione mobile passano all'FQDN Web esterno solo per il servizio per dispositivi mobili. Altre richieste di servizio, ad esempio le richieste della Rubrica, non richiedono questa configurazione.



</div>

I dispositivi mobili supportano l'individuazione manuale dei servizi. In questo caso, ogni utente deve configurare le impostazioni dei dispositivi mobili con gli URI del servizio di individuazione automatica interni ed esterni, inclusi il protocollo e il percorso, come indicato di seguito:

  - /Autodiscover/autodiscoverservice.svc/root\<d'\>ExtPoolFQDN https://per l'accesso esterno

  - /AutoDiscover/autodiscover.svc/root\<d'\>IntPoolFQDN https://per l'accesso interno

È consigliabile utilizzare l'individuazione automatica anziché l'individuazione manuale. Tuttavia, le impostazioni manuali possono essere utili per la risoluzione dei problemi relativi alla connettività del dispositivo mobile.

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Configurazione del DNS split-brain con Lync Server

Il DNS split-brain è conosciuto da un certo numero di nomi, ad esempio, Split DNS o Split-Horizon DNS. In questo articolo viene descritta una configurazione DNS in cui sono presenti due aree DNS con lo stesso spazio dei nomi, ma solo una richiesta di servizi di area DNS solo interna e l'altra richiede solo le richieste esterne di servizi di zona DNS. Tuttavia, molti dei DNS SRV e di un record contenuti nel DNS interno non saranno contenuti nel DNS esterno e anche l'inverso è vero. Nei casi in cui lo stesso record DNS esista sia nel DNS interno che in quello esterno (ad esempio, www.contoso.com), l'indirizzo IP restituito sarà diverso in base al percorso (interno o esterno) della query.

<div>


> [!IMPORTANT]  
> Attualmente, il DNS split-brain non è supportato per la mobilità, o più in particolare, i record DNS di LyncDiscover e LyncDiscoverInternal. LyncDiscover deve essere definito in un server DNS esterno e LyncDiscoverInternal deve essere definito in un server DNS interno.



</div>

Ai fini di questi argomenti, verrà utilizzato il termine DNS split-brain.

Se si sta configurando il DNS split-brain, l'area interna ed esterna seguente contiene un riepilogo dei tipi di record DNS necessari in ogni area. Per ulteriori informazioni, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**DNS interno:**

  - Contiene un'area DNS denominata contoso.com per la quale è autorevole

  - L'area interna di contoso.com contiene:
    
      - DNS A e AAAA (se si utilizza l'indirizzamento IPv6) e i record SRV per la configurazione automatica del client Lync Server 2013 (facoltativo)
    
      - DNS A e AAAA (se si utilizza l'indirizzamento IPv6) o i record CNAME per l'individuazione automatica dei servizi Web di Lync Server 2013 (facoltativo)
    
      - DNS A e AAAA (se si utilizzano i record per l'indirizzamento IPv6) per il nome del pool Front End, il nome del pool di Director o del server Director e tutti i server interni in cui è in esecuzione Lync 2013 nella rete aziendale
    
      - DNS A e AAAA (se si utilizzano i record per l'indirizzamento IPv6) per l'interfaccia interna perimetrale di ogni Lync Server 2013, Edge Server nella rete perimetrale
    
      - DNS A e AAAA (se si utilizzano i record per l'indirizzamento IPv6) per l'interfaccia interna di ogni server proxy inverso nella rete perimetrale (facoltativo per la gestione del proxy inverso)
    
      - Tutte le interfacce perimetrali interne di Lync Server 2013 perimetro della rete di bordo utilizzano l'area DNS interna per la risoluzione delle query in contoso.com
    
      - Tutti i server che eseguono Lync Server 2013 e i client che eseguono Lync 2013 nella rete aziendale puntano ai server DNS interni per la risoluzione delle query in contoso.com o all'utilizzo del file HOSTs in ogni server perimetrale ed elenchi A e AAAA (se si utilizzano i record di indirizzamento IPv6) per server hop successivo, in particolare il VIP del Director o del Director, il VIP del pool Front end o il server Standard Edition

**DNS esterno:**

  - Contiene un'area DNS denominata contoso.com per la quale è autorevole

  - L'area contoso.com esterna contiene:
    
      - DNS A e AAAA (se si utilizza l'indirizzamento IPv6) e i record SRV per la configurazione automatica del client di Lync Server 2013 (facoltativa)
    
      - DNS A e AAAA (se si utilizza l'indirizzamento IPv6) o i record CNAME per l'individuazione automatica dei servizi Web di Lync Server 2013 per l'utilizzo con i dispositivi mobili
    
      - DNS A e AAAA (se si utilizza l'indirizzamento IPv6) e i record SRV per l'interfaccia esterna perimetrale di ogni Lync Server 2013, server perimetrale o IP virtuale (VIP) del servizio di bilanciamento del carico hardware nella rete perimetrale
    
      - DNS A e AAAA (se si utilizzano i record per l'indirizzamento IPv6) per l'interfaccia esterna del server proxy inverso o VIP per un pool di server proxy inversi nella rete perimetrale

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>Configurazione automatica senza DNS split-brain

Tramite DNS split-brain, un utente di Lync Server 2013 che accede internamente può usufruire della configurazione automatica se la zona DNS interna contiene una \_sipinternaltls. \_record TCP SRV per ogni dominio SIP in uso. Tuttavia, se non si utilizza il DNS split-brain, la configurazione automatica interna dei client che eseguono Lync non funzionerà a meno che non venga implementata una delle soluzioni alternative descritte in più avanti in questa sezione. Ciò è dovuto al fatto che Lync Server 2013 richiede l'URI SIP dell'utente in modo che corrisponda al dominio del pool Front End designato per la configurazione automatica. Questo è stato anche il caso di versioni precedenti di Communicator.

Se ad esempio si dispone di due domini SIP in uso, sarebbero necessari i record del servizio DNS (SRV) seguenti:

  - Se un utente accede come bob@contoso.com, il record SRV seguente funzionerà per la configurazione automatica perché il dominio SIP dell'utente (contoso.com) corrisponde al dominio del pool di front end di configurazione automatica):
    
     \_sipinternaltls. \_TCP.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Se un utente accede come alice@fabrikam.com, il record DNS SRV seguente funzionerà per la configurazione automatica del secondo dominio SIP.
    
     \_sipinternaltls. \_TCP.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Per un confronto, se un utente accede come tim@litwareinc.com, il record SRV DNS seguente non funzionerà per la configurazione automatica, in quanto il dominio SIP del client (litwareinc.com) non corrisponde al dominio in cui si trova il pool (fabrikam.com):

 \_sipinternaltls. \_TCP.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Se è necessaria la configurazione automatica per i client che eseguono Lync, selezionare una delle opzioni seguenti:

  - **Gli oggetti**   criteri di gruppo utilizzano gli oggetti Criteri di gruppo per popolare i valori del server corretti.
    
    <div>
    

    > [!NOTE]  
    > Questa opzione non Abilita la configurazione automatica, ma consente di automatizzare il processo di configurazione manuale, quindi se si utilizza questo approccio, i record SRV associati alla configurazione automatica non sono necessari.

    
    </div>

  - **Area interna corrispondente**   creare un'area nel DNS interno che corrisponda alla zona DNS esterna (ad esempio, contoso.com) e creare record DNS a e aaaa (se si utilizzano gli indirizzi IPv6) corrispondenti al pool di Lync Server 2013 utilizzato per la configurazione automatica. Ad esempio, se un utente è ospitato in pool01.contoso.net, ma accede a Lync come bob@contoso.com, creare una zona DNS interna denominata contoso.com e al suo interno, creare un record DNS A e AAAA (se viene utilizzato IPv6 Addressing) per pool01.contoso.com.

  - **Area interna del pin-point**   se si sta creando un'intera area nel DNS interno non è un'opzione, è possibile creare zone pin-point, ovvero dedicate, che corrispondono ai record SRV necessari per la configurazione automatica e popolare tali zone tramite Dnscmd. exe. Dnscmd. exe è necessario perché l'interfaccia utente DNS non supporta la creazione di aree a punti pin. Ad esempio, se il dominio SIP è contoso.com e si dispone di un pool Front End denominato Pool01 che contiene due front end server, sono necessarie le seguenti aree di pin-point e un record nel DNS interno:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    Se l'ambiente contiene un secondo dominio SIP, ad esempio fabrikam.com, è necessario disporre delle seguenti aree di pin-point e di un record nel DNS interno:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> L'FQDN del pool Front end viene visualizzato due volte, ma con due indirizzi IP diversi. Questo perché viene utilizzato il bilanciamento del carico DNS, ma se viene utilizzato il bilanciamento del carico hardware, è presente una sola voce del pool Front end. Inoltre, i valori FQDN del pool Front End cambiano tra l'esempio di contoso.com e l'esempio di fabrikam.com, ma gli indirizzi IP rimangono invariati. Ciò è dovuto al fatto che gli utenti accedono da un dominio SIP o utilizzano lo stesso pool Front end per la configurazione automatica.



</div>

Per informazioni dettagliate, vedere l'articolo del Blog di DMTF, "configurazione automatica di Communicator e DNS split- [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707)Brain" all'indirizzo.

<div>


> [!NOTE]  
> Il contenuto di ogni blog e il relativo URL sono soggetti a modifica senza preavviso.



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>Configurazione del DNS (Domain Name System) per il ripristino di emergenza

Per configurare il DNS in modo da reindirizzare il traffico Web di Lync Server 2013 al ripristino di emergenza e ai siti di failover, è necessario utilizzare un provider DNS che supporti GeoDNS. È possibile configurare i record DNS per il Web per supportare il ripristino di emergenza, in modo che le funzionalità che utilizzano i servizi Web continuino anche se un intero pool Front-end viene interrotto. Questa funzionalità di ripristino di emergenza supporta gli URL semplici di individuazione automatica (URL Lyncdiscover), riunione e accesso esterno.

È possibile definire e configurare i record host DNS aggiuntivi (A e AAAA se si utilizza IPv6) per la risoluzione interna ed esterna dei servizi Web nel provider di GeoDNS. Nei dettagli seguenti si presuppone che i pool associati, distribuiti geograficamente e GeoDNS supportati dal provider con DNS round robin, siano configurati per l'utilizzo di pool1 come primari e che non vengano Pool2 in caso di perdita di comunicazioni o di errore hardware.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Record di GeoDNS (esempio)</th>
<th>Record del pool (ad esempio)</th>
<th>Record CNAME (esempio)</th>
<th>Impostazioni DNS (selezionare un'opzione)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias di Meet.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias di Meet.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra pool</p>
<p>Utilizzo primario, connessione a secondario in caso di errore</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias di Meet.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias di Meet.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra pool</p>
<p>Utilizzo primario, connessione a secondario in caso di errore</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias di Dialin.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias di Dialin.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra pool</p>
<p>Utilizzo primario, connessione a secondario in caso di errore</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias di Dialin.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias di Dialin.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra pool</p>
<p>Utilizzo primario, connessione a secondario in caso di errore</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias di Lyncdiscoverinternal.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias di Lyncdiscoverinternal.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra pool</p>
<p>Utilizzo primario, connessione a secondario in caso di errore</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias di Lyncdiscover.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias di Lyncdiscover.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra pool</p>
<p>Utilizzo primario, connessione a secondario in caso di errore</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Alias di Scheduler.contoso.com a Pool1InternalWebFQDN.contoso.com</p>
<p>Alias di Scheduler.contoso.com a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra pool</p>
<p>Utilizzo primario, connessione a secondario in caso di errore</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Alias di Scheduler.contoso.com a Pool1ExternalWebFQDN.contoso.com</p>
<p>Alias di Scheduler.contoso.com a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra pool</p>
<p>Utilizzo primario, connessione a secondario in caso di errore</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>Bilanciamento del carico DNS

Il bilanciamento del carico DNS è in genere implementato a livello di applicazione. L'applicazione, ad esempio un client che esegue Lync, tenta di connettersi a un server in un pool collegandosi a uno degli indirizzi IP restituiti dalla query di record DNS A e AAAA (se si utilizza l'indirizzamento IPv6) per il nome di dominio completo (FQDN) del pool.

Ad esempio, se sono presenti tre Front End Server in un pool denominato pool01.contoso.com, si verificherà quanto segue:

  - Client che eseguono Lync query DNS per pool01.contoso.com. La query restituisce tre indirizzi IP e li memorizza nella cache come indicato di seguito (non necessariamente nell'ordine):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - Il client tenta di stabilire una connessione TCP (Transmission Control Protocol) a uno degli indirizzi IP. In caso di esito negativo, il client tenterà l'indirizzo IP successivo nella cache.

  - Se la connessione TCP ha esito positivo, il client negozia TLS per la connessione al servizio di registrazione principale su pool01.contoso.com.

  - Se il client cerca tutte le voci memorizzate nella cache senza una connessione completata, l'utente riceve una notifica che attualmente non sono disponibili server che eseguono Lync Server 2013.

<div>


> [!NOTE]  
> Il bilanciamento del carico basato su DNS è diverso da quello del round robin DNS (RR DNS), che in genere si riferisce al bilanciamento del carico facendo affidamento sul DNS per fornire un diverso ordine di indirizzi IP corrispondenti ai server in un pool. Tipicamente DNS RR attiva solo la distribuzione del carico, ma non Abilita il failover. Ad esempio, se la connessione a un indirizzo IP restituito dalla query DNS A e AAAA (se si utilizza l'indirizzamento IPv6) ha esito negativo, la connessione ha esito negativo. Pertanto, il round robin DNS è di per sé meno affidabile rispetto al bilanciamento del carico basato su DNS. È possibile utilizzare il round robin DNS in combinazione con il bilanciamento del carico DNS.



</div>

Il bilanciamento del carico DNS viene utilizzato per gli elementi seguenti:

  - Bilanciamento del carico del SIP da server a server nei server perimetrali

  - Bilanciamento del carico delle applicazioni unificate (Unified Communications Application Services), ad esempio operatore automatico di conferenza, Response Group e parcheggio di chiamata

  - Impedire nuove connessioni alle applicazioni di unificate (note anche come "drenante")

  - Bilanciamento del carico di tutto il traffico da client a server tra client e server perimetrali

Non è possibile utilizzare il bilanciamento del carico DNS per gli elementi seguenti:

  - Traffico Web da client a server a Director o front end server

Bilanciamento del carico DNS e traffico federato:

Se più record DNS vengono restituiti da una query DNS SRV, il servizio Access Edge preleva sempre il record DNS SRV con la priorità numerica più bassa e il peso numerico più alto. Il documento Internet Engineering Task Force "un RR DNS per specificare il percorso dei servizi (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt> specifica che, se sono stati definiti più record SRV DNS, la priorità viene utilizzata per la prima volta, quindi peso. Ad esempio, il record DNS SRV A ha un peso di 20 e la priorità di 40 e il record DNS SRV B ha un peso di 10 e la priorità di 50. Verrà selezionato il record DNS SRV A con priorità 40. Le regole seguenti si applicano alla selezione dei record DNS SRV:

  - La priorità viene considerata per prima. Un client deve tentare di contattare l'host di destinazione definito dal record SRV DNS con la priorità più bassa numerata che può raggiungere. Gli obiettivi con la stessa priorità devono essere tentati in base a un ordine definito dal campo Weight.

  - Il campo Weight specifica un peso relativo per le voci con la stessa priorità. I pesi maggiori devono avere una probabilità proporzionalmente più alta di essere selezionati. Gli amministratori DNS devono utilizzare il peso 0 quando non è presente alcuna selezione del server. In presenza di record che contengono pesi maggiori di 0, i record con peso 0 devono avere una possibilità molto piccola di essere selezionati.

Se vengono restituiti più record SRV DNS con priorità e peso uguali, il servizio Access Edge selezionerà il record SRV ricevuto per primo dal server DNS.

</div>

</div>

<span> </span>

</div>

</div>

</div>

