---
title: 'Lync Server 2013: Determinare i requisiti di DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e299f138a28ba4863250d2e0be1f31f705f4a173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a>Determinare i requisiti di DNS per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

Usare il diagramma di flusso seguente per determinare i requisiti DNS (Domain Name System). Le modifiche apportate agli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 sono note nel punto in cui si applicano.

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 supporta l'uso di indirizzi IPv6. Per usare gli indirizzi IPv6, è necessario specificare anche il supporto per DNS IPv6 e configurare i record DNS host AAAA, detti "Quad-A". Nelle distribuzioni in cui vengono usati sia IPv4 che IPv6, è consigliabile configurare e gestire sia l'host di un record per IPv4 che l'host AAAA per IPv6. Anche se la distribuzione ha effettuato una transizione completa a IPv6, i record host DNS IPv4 potrebbero essere ancora necessari quando gli utenti esterni usano ancora IPv4.



</div>

**Diagramma di flusso Determinazione dei requisiti DNS**

![175782ac-363e-408A-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408A-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> Per impostazione predefinita, il nome del computer di un computer che non è associato a un dominio è un nome host, non un nome di dominio completo (FQDN). Generatore di topologie USA FQDN e non i nomi host. Devi quindi configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale che non è associato a un dominio. <STRONG>Usare solo caratteri standard</STRONG> (tra cui a-z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi di Lync Server, Edge Server e pool. Non usare caratteri Unicode o carattere di sottolineatura. I caratteri non standard di un nome di dominio completo spesso non sono supportati dal DNS esterno e dalle CA pubbliche, ovvero quando il nome di dominio completo deve essere assegnato a SN nel certificato. Per ulteriori informazioni, vedere <A href="lync-server-2013-configure-dns-host-records.md">configurare i record host DNS per Lync Server 2013</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Come i client Lync individuano i servizi

Microsoft Lync 2010, Lync 2013 e Lync mobile sono simili nel modo in cui il client trova e accede ai servizi in Lync Server 2013. L'eccezione nota è l'app Lync di Windows Store che usa un processo di posizione del servizio diverso. In questa sezione vengono illustrati due scenari relativi al modo in cui i client individuano i servizi, prima il metodo tradizionale che usa una serie di record SRV e host, secondo usando solo i record del servizio di individuazione automatica. Gli aggiornamenti cumulativi per i client desktop modificano il processo di posizione DNS da Lync Server 2010 per tutti i client, il processo di query DNS continua fino a quando non viene restituita una query corretta oppure l'elenco dei record DNS possibili è esaurito e viene restituito l'errore finale il client.

Per tutti i client **eccetto** l'app Lync di Windows Store durante la ricerca DNS, i record SRV vengono interrogati e restituiti al client nell'ordine seguente:

1.  lyncdiscoverinternal. \<record\> Domain a (host) per il servizio di individuazione automatica nei servizi Web interni

2.  Lyncdiscover. \<record\> Domain a (host) per il servizio di individuazione automatica nei servizi Web esterni

3.  \_sipinternaltls. \_TCP. \<record\> Domain SRV (Service Locator) per connessioni TLS interne

4.  \_sipinternal. \_TCP. \<record\> Domain SRV (Service Locator) per le connessioni TCP interne (eseguito solo se è consentito TCP)

5.  \_SIP. \_TLS. \<record\> Domain SRV (Service Locator) per connessioni TLS esterne

6.  sipinternal. \<record\> Domain a (host) per il pool o il Director front-end, risolvibile solo nella rete interna

7.  SIP. \<dominio\> a (host) record per il pool o il Director front-end nella rete interna o il servizio Access Edge quando il client è esterno

8.  sipexternal. \<record\> Domain a (host) per il servizio Access Edge quando il client è esterno

L'app Lync di Windows Store cambia completamente il processo perché usa due record:

1.  lyncdiscoverinternal. \<record\> Domain a (host) per il servizio di individuazione automatica nei servizi Web interni

2.  Lyncdiscover. \<record\> Domain a (host) per il servizio di individuazione automatica nei servizi Web esterni

Non esiste alcun fallback per gli altri tipi di record.

La differenza tra i metodi usati per i nuovi client rispetto ai client meno recenti è che il servizio di individuazione automatica sta diventando il metodo preferito per individuare tutti i servizi.

Quando una connessione ha esito positivo, il servizio di individuazione automatica restituisce tutti gli URL dei servizi Web per il pool di Home dell'utente, incluso il servizio di mobilità (noto come MCX dalla directory virtuale creata per il servizio in IIS), gli URL di Microsoft Lync Web App e Web Scheduler. Tuttavia, sia l'URL del servizio di mobilità interna che l'URL del servizio di mobilità esterna sono associati all'FQDN dei servizi Web esterni. Di conseguenza, indipendentemente dal fatto che un dispositivo mobile sia interno o esterno alla rete, il dispositivo si connette sempre al servizio di mobilità esternamente tramite il proxy inverso.

Se gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 sono stati installati, il servizio di individuazione automatica restituisce anche i riferimenti a Internal/UCWA, External/UCWA e UCWA. Queste voci si riferiscono al componente Web Unified Communications Web API (UCWA). Attualmente viene usato solo il UCWA voce e fornisce un riferimento a un URL per il componente Web. UCWA viene usato dai client per dispositivi mobili Lync 2013 invece del servizio di mobilità MCX usato dai client mobili di Lync 2010.

<div>


> [!NOTE]  
> Quando si creano record SRV, è importante tenere presente che devono puntare a un record DNS a e AAAA (se si usa l'indirizzo IPv6) nello stesso dominio in cui viene creato il record SRV DNS. Ad esempio, se il record SRV si trova in contoso.com, il record A e AAAA (se si usa l'indirizzo IPv6) indica che non può essere in fabrikam.com.



</div>

<div>


> [!TIP]  
> La configurazione predefinita è quella di indirizzare tutto il traffico client per dispositivi mobili attraverso il sito esterno. Puoi modificare le impostazioni per restituire solo l'URL interno, se questo è più preferibile per i tuoi requisiti. Con questa configurazione, gli utenti possono usare le applicazioni mobili di Lync sui loro dispositivi mobili solo quando si trovano all'interno della rete aziendale. Per definire questa configurazione, puoi usare il cmdlet <STRONG>Set-CsMcxConfiguration</STRONG> .



</div>

<div>


> [!NOTE]  
> Anche se le applicazioni per dispositivi mobili possono anche connettersi ad altri servizi di Lync Server 2013, ad esempio il servizio Rubrica, le richieste Web interne per dispositivi mobili accedono al nome FQDN Web esterno solo per il servizio mobilità. Altre richieste di servizio, ad esempio le richieste della Rubrica, non richiedono questa configurazione.



</div>

I dispositivi mobili supportano l'individuazione manuale dei servizi. In questo caso, ogni utente deve configurare le impostazioni del dispositivo mobile con gli URI del servizio di individuazione automatica interni ed esterni, inclusi il protocollo e il percorso, come indicato di seguito:

  - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/root per l'accesso esterno

  - https://\<IntPoolFQDN\>/autodiscover/autodiscover.svc/root per l'accesso interno

È consigliabile usare l'individuazione automatica anziché l'individuazione manuale. Le impostazioni manuali possono tuttavia essere utili per la risoluzione dei problemi relativi alla connettività di dispositivi mobili.

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Configurazione del DNS con il cervello diviso con Lync Server

Il DNS split-brain è noto per un numero di nomi, ad esempio, Split DNS o Split-Horizon DNS. Descrive semplicemente una configurazione DNS in cui sono presenti due aree DNS con lo stesso spazio dei nomi, ma una per le richieste solo interne di servizi di zona DNS e le altre richieste solo esterne di servizi di zona DNS. Tuttavia, molti DNS SRV e record contenuti nel DNS interno non saranno contenuti nel DNS esterno e anche il contrario è vero. Nei casi in cui lo stesso record DNS esiste sia nel DNS interno che in quello esterno (ad esempio, www.contoso.com), l'indirizzo IP restituito sarà diverso in base a dove (interno o esterno) è stata avviata la query.

<div>


> [!IMPORTANT]  
> Attualmente, il DNS split-brain non è supportato per la mobilità o, più in particolare, per i record DNS LyncDiscover e LyncDiscoverInternal. LyncDiscover deve essere definito in un server DNS esterno e LyncDiscoverInternal deve essere definito in un server DNS interno.



</div>

Ai fini di questi argomenti verrà usato il termine DNS split-brain.

Se si sta configurando il DNS split-brain, la zona interna ed esterna seguente contiene un riepilogo dei tipi di record DNS necessari in ogni zona. Per informazioni dettagliate, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**DNS interno:**

  - Contiene una zona DNS denominata contoso.com per la quale è autorevole

  - La zona contoso.com interna contiene:
    
      - DNS A e AAAA (se si usa l'indirizzamento IPv6) e i record SRV per la configurazione automatica client Lync Server 2013 interna (facoltativo)
    
      - DNS A e AAAA (se si usa l'indirizzamento IPv6) o CNAME Records per l'individuazione automatica dei servizi Web di Lync Server 2013 (facoltativo)
    
      - DNS A e AAAA (se si usano i record di indirizzamento IPv6) per il nome del pool di front end, il nome del pool di Director o Director e tutti i server interni che esegue Lync Server 2013 nella rete aziendale
    
      - DNS A e AAAA (se si usano i record di indirizzamento IPv6) per l'interfaccia interna Edge di ogni Lync Server 2013, Edge Server nella rete perimetrale
    
      - DNS A e AAAA (se si usano i record di indirizzamento IPv6) per l'interfaccia interna di ogni server proxy inverso nella rete perimetrale (facoltativo per la gestione del proxy inverso)
    
      - Tutte le interfacce Edge Server Edge di Lync Server 2013 nella rete perimetrale usano la zona DNS interna per la risoluzione delle query in contoso.com
    
      - Tutti i server che usano Lync Server 2013 e i client che usano Lync 2013 nella rete aziendale puntano ai server DNS interni per la risoluzione delle query in contoso.com o all'uso di file host in ogni server perimetrale ed elenchi A e AAAA (se si utilizzano i record di indirizzamento IPv6) per server hop successivo, in particolare il VIP Director o Director, il VIP del pool Front-end o il server Standard Edition

**DNS esterno:**

  - Contiene una zona DNS denominata contoso.com per la quale è autorevole

  - La zona contoso.com esterna contiene:
    
      - DNS A e AAAA (se si usa l'indirizzamento IPv6) e i record SRV per la configurazione automatica client di Lync Server 2013 (facoltativo)
    
      - DNS A e AAAA (se si usa l'indirizzamento IPv6) o CNAME Records per l'individuazione automatica dei servizi Web di Lync Server 2013 per l'uso con la mobilità
    
      - DNS A e AAAA (se si usa l'indirizzamento IPv6) e i record SRV per l'interfaccia esterna di ogni Lync Server 2013, server perimetrale o IP virtuale di bilanciamento del carico hardware (VIP)
    
      - DNS A e AAAA (se si usano i record di indirizzamento IPv6) per l'interfaccia esterna del server proxy inverso o VIP per un pool di server proxy inverso nella rete perimetrale

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>Configurazione automatica senza DNS split-brain

L'uso di un DNS split-brain, un utente di Lync Server 2013 che effettua l'accesso internamente può sfruttare la configurazione automatica se la \_zona DNS interna contiene un sipinternaltls. \_record SRV TCP per ogni dominio SIP in uso. Tuttavia, se non usi il DNS split-brain, la configurazione automatica interna dei client che eseguono Lync non funzionerà a meno che non venga implementata una delle soluzioni alternative descritte in seguito in questa sezione. Questo perché Lync Server 2013 richiede che l'URI SIP dell'utente corrisponda al dominio del pool Front-End designato per la configurazione automatica. Questo è stato anche il caso delle versioni precedenti di Communicator.

Se ad esempio sono presenti due domini SIP in uso, è necessario che siano necessari i record del servizio DNS (SRV) seguente:

  - Se un utente accede come bob@contoso.com, il record SRV seguente funzionerà per la configurazione automatica perché il dominio SIP dell'utente (contoso.com) corrisponde al dominio del pool di front-end di configurazione automatica:
    
     \_sipinternaltls. \_TCP.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - Se un utente accede come alice@fabrikam.com, il record SRV DNS seguente funzionerà per la configurazione automatica del secondo dominio SIP.
    
     \_sipinternaltls. \_TCP.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Per il confronto, se un utente accede come tim@litwareinc.com il record SRV DNS seguente non funzionerà per la configurazione automatica, perché il dominio SIP del client (litwareinc.com) non corrisponde al dominio in cui si trova il pool (fabrikam.com):

 \_sipinternaltls. \_TCP.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

Se è necessaria la configurazione automatica per i client che utilizzano Lync, selezionare una delle opzioni seguenti:

  - **Gli oggetti**   criteri di gruppo usano oggetti Criteri di gruppo per popolare i valori del server corretti.
    
    <div>
    

    > [!NOTE]  
    > Questa opzione non consente la configurazione automatica, ma automatizza il processo di configurazione manuale, quindi se questo approccio viene usato, i record SRV associati alla configurazione automatica non sono obbligatori.

    
    </div>

  - **La zona**   interna corrispondente crea una zona nel DNS interno che corrisponde all'area DNS esterna (ad esempio contoso.com) e crea DNS a e aaaa (se si usano i record di indirizzamento IPv6) corrispondenti al pool di Lync Server 2013 usato per la configurazione automatica. Ad esempio, se un utente viene ospitato in pool01.contoso.net, ma accede a Lync come bob@contoso.com, crea una zona DNS interna denominata contoso.com e al suo interno, crea un record DNS A e AAAA (se si usa l'indirizzamento IPv6) per pool01.contoso.com.

  - **La zona**   interna del pin-point se si sta creando un'intera area nel DNS interno non è un'opzione, è possibile creare zone pin-point (ovvero dedicate) che corrispondono ai record SRV necessari per la configurazione automatica e popolare tali zone tramite Dnscmd. exe. Dnscmd. exe è necessario perché l'interfaccia utente DNS non supporta la creazione di aree con punti pin. Ad esempio, se il dominio SIP è contoso.com e si dispone di un pool Front-End denominato Pool01 che contiene due server front-end, sono necessarie le seguenti aree di punti pin e un record nel DNS interno:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    Se l'ambiente contiene un secondo dominio SIP (ad esempio, fabrikam.com), è necessario disporre delle aree di punti pin seguenti e di un record nel DNS interno:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> Il nome FQDN del pool Front-end viene visualizzato due volte, ma con due indirizzi IP diversi. Questo perché viene usato il bilanciamento del carico DNS, ma se viene usato il bilanciamento del carico hardware, esisterebbe solo una singola voce del pool Front-end. Inoltre, i valori FQDN del pool di front end cambiano tra l'esempio contoso.com e l'esempio fabrikam.com, ma gli indirizzi IP rimangono invariati. Il motivo è che gli utenti che accedono da un dominio SIP usano lo stesso pool Front-end per la configurazione automatica.



</div>

Per informazioni dettagliate, vedere l'articolo su [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)Blog di DMTF, "configurazione automatica di Communicator e DNS split-brain".

<div>


> [!NOTE]  
> Il contenuto di ogni blog e il relativo URL sono soggetti a modifiche senza preavviso.



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>Configurazione del DNS (Domain Name System) per il ripristino di emergenza

Per configurare il DNS per reindirizzare il traffico Web di Lync Server 2013 ai siti di failover e ripristino di emergenza, è necessario usare un provider DNS che supporti GeoDNS. È possibile configurare i record DNS per il Web per supportare il ripristino di emergenza, in modo che le caratteristiche che usano i servizi Web continuino anche se un intero pool Front-End scende. Questa caratteristica di ripristino di emergenza supporta l'individuazione automatica (URL Lyncdiscover), gli URL semplici di riunione e accesso esterno.

Si definiscono e si configurano altri record host DNS (A e AAAA se si usano IPv6) per la risoluzione interna ed esterna dei servizi Web presso il provider di GeoDNS. I dettagli seguenti presuppongono pool associati, dislocati geograficamente e GeoDNS supportati dal provider con il DNS round-robin o configurati per l'uso di pool1 come primari e non vengono rientrati in Pool2 in caso di perdita di comunicazioni o errori hardware.


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
<th>Record del pool (esempio)</th>
<th>Record CNAME (esempio)</th>
<th>Impostazioni DNS (selezionare un'opzione)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com alias a Pool1InternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com alias a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra i pool</p>
<p>USA primaria, Connetti a un errore secondario</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com alias a Pool1ExternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com alias a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra i pool</p>
<p>USA primaria, Connetti a un errore secondario</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com alias a Pool1InternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com alias a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra i pool</p>
<p>USA primaria, Connetti a un errore secondario</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com alias a Pool1ExternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com alias a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra i pool</p>
<p>USA primaria, Connetti a un errore secondario</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscoverinternal.contoso.com alias a Pool1InternalWebFQDN.contoso.com</p>
<p>Lyncdiscoverinternal.contoso.com alias a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra i pool</p>
<p>USA primaria, Connetti a un errore secondario</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscover.contoso.com alias a Pool1ExternalWebFQDN.contoso.com</p>
<p>Lyncdiscover.contoso.com alias a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra i pool</p>
<p>USA primaria, Connetti a un errore secondario</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com alias a Pool1InternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com alias a Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra i pool</p>
<p>USA primaria, Connetti a un errore secondario</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com alias a Pool1ExternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com alias a Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Round Robin tra i pool</p>
<p>USA primaria, Connetti a un errore secondario</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>Bilanciamento del carico DNS

Il bilanciamento del carico DNS viene in genere implementato a livello di applicazione. L'applicazione, ad esempio un client che esegue Lync, cerca di connettersi a un server in un pool connettendosi a uno degli indirizzi IP restituiti dalla query di record DNS A e AAAA (se si usa l'Addressing IPv6) per il nome di dominio completo del pool.

Se ad esempio sono presenti tre server front-end in un pool denominato pool01.contoso.com, si verificheranno le operazioni seguenti:

  - Client che eseguono Lync query DNS per pool01.contoso.com. La query restituisce tre indirizzi IP e li memorizza nella cache come indicato di seguito (non necessariamente in questo ordine):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - Il client cerca di stabilire una connessione TCP (Transmission Control Protocol) a uno degli indirizzi IP. Se l'operazione non riesce, il client tenterà l'indirizzo IP successivo nella cache.

  - Se la connessione TCP riesce, il client negozia TLS per connettersi al registrar principale in pool01.contoso.com.

  - Se il client cerca tutte le voci memorizzate nella cache senza una connessione riuscita, viene avvisato che al momento non sono disponibili server che esegue Lync Server 2013.

<div>


> [!NOTE]  
> Il bilanciamento del carico basato su DNS è diverso da DNS round robin (DNS RR) che in genere si riferisce al bilanciamento del carico facendo affidamento sul DNS per specificare un ordine diverso di indirizzi IP corrispondenti ai server in un pool. In genere il record DNS consente solo la distribuzione del carico, ma non Abilita il failover. Ad esempio, se la connessione a un indirizzo IP restituito dal DNS A e AAAA (se si usa l'indirizzamento IPv6) non riesce, la connessione non riesce. Di conseguenza, il round robin DNS è meno attendibile del bilanciamento del carico basato su DNS. È possibile usare DNS round robin insieme al bilanciamento del carico DNS.



</div>

Il bilanciamento del carico DNS viene usato per le operazioni seguenti:

  - Bilanciamento del carico del SIP da server a server per gli Edge Server

  - Bilanciamento del carico delle applicazioni UCAS (Unified Communications Application Services) come l'operatore automatico di conferenza, il gruppo di risposta e il parcheggio delle chiamate

  - Impedire le nuove connessioni alle applicazioni di UCAS (nota anche come "drenante")

  - Bilanciamento del carico di tutto il traffico da client a server tra client e Edge Server

Non è possibile usare il bilanciamento del carico DNS per gli elementi seguenti:

  - Traffico Web da client a server a server Director o front end

Bilanciamento del carico DNS e traffico federativo:

Se più record DNS vengono restituiti da una query SRV DNS, il servizio Edge di Access sceglie sempre il record SRV DNS con la priorità numerica più bassa e il peso numerico più alto. Il documento Internet Engineering Task Force "un RR DNS per specificare la posizione dei servizi (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt> specifica che se sono definiti più record SRV DNS, viene usata prima la priorità e quindi Weight. Ad esempio DNS SRV record A ha un peso di 20 e una priorità di 40 e DNS SRV record B ha un peso di 10 e la priorità di 50. Verrà selezionato il record SRV DNS A con priorità 40. Le regole seguenti si applicano alla selezione del record SRV DNS:

  - La priorità viene considerata per prima. Un client deve tentare di contattare l'host di destinazione definito dal record SRV DNS con la priorità di numerazione più bassa che può raggiungere. Le destinazioni con la stessa priorità devono essere provate in un ordine definito dal campo peso.

  - Il campo peso specifica un peso relativo per le voci con la stessa priorità. I pesi più grandi dovrebbero avere una probabilità di essere selezionata proporzionalmente più alta. Gli amministratori DNS dovrebbero usare il peso 0 quando non è presente alcuna selezione del server. In presenza di record che contengono pesi superiori a 0, i record con peso 0 dovrebbero avere una probabilità molto piccola di essere selezionati.

Se vengono restituiti più record SRV DNS con priorità e peso uguali, il servizio Access Edge selezionerà il record SRV ricevuto per primo dal server DNS.

</div>

</div>

<span> </span>

</div>

</div>

</div>

