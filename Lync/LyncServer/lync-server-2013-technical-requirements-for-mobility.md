---
title: 'Lync Server 2013: Requisiti tecnici per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac74f7e9e85829e500900e03d4b7cfedf89d1e0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Requisiti tecnici per i dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Gli utenti di dispositivi mobili incontrano diversi scenari di applicazioni mobili che richiedono una pianificazione speciale. Ad esempio, un utente potrebbe iniziare a usare un'applicazione per dispositivi mobili mentre si allontana dal lavoro connettendosi tramite la rete 3G, quindi passare alla rete Wi-Fi aziendale quando si arriva al lavoro e quindi tornare alla versione 3G quando si esce dall'edificio. È necessario pianificare l'ambiente per supportare tali transizioni di rete e garantire un'esperienza utente coerente. Questa sezione descrive i requisiti di infrastruttura che devono avere per supportare le applicazioni mobili e l'individuazione automatica delle risorse di mobilità.

<div>


> [!NOTE]  
> Anche se le applicazioni per dispositivi mobili possono anche connettersi ad altri servizi di Lync Server 2013, il requisito di inviare tutte le richieste Web dell'applicazione per dispositivi mobili allo stesso nome di dominio completo (FQDN) Web esterno si applica solo al servizio di mobilità di Lync Server 2013. Altri servizi di mobilità non richiedono questa configurazione.



</div>

Il requisito per l'affinità dei cookie nei dispositivi di bilanciamento del carico hardware è drasticamente ridotto e si sostituisce l'affinità TCP (Transmission Control Protocol) se si usa Lync mobile recapitato con Lync Server 2013. L'affinità dei cookie può essere ancora usata, ma i servizi Web non lo richiedono più.

<div>


> [!IMPORTANT]  
> Tutto il traffico del servizio di mobilità passa attraverso il proxy inverso, indipendentemente dalla posizione in cui si trova il punto di origine, ovvero interno o esterno. Nel caso di un singolo proxy inverso o di una farm di proxy inverso o di un dispositivo che fornisce la funzione proxy inverso, può verificarsi un problema quando il traffico interno viene egressing tramite un'interfaccia e si tenta di eseguire immediatamente l'ingresso nella stessa interfaccia. Questo porta spesso a una violazione della regola di sicurezza nota come spoofing del pacchetto TCP o solo spoofing. Il <EM>blocco dei capelli</EM> (l'uscita e l'ingresso immediato di un pacchetto o una serie di pacchetti) devono essere consentiti per consentire la funzione mobilità. Un modo per risolvere questo problema consiste nell'usare un proxy inverso separato dal firewall (la regola di prevenzione dello spoofing deve sempre essere applicata al firewall per motivi di sicurezza). Il tornante può presentarsi all'interfaccia esterna del proxy inverso invece dell'interfaccia esterna del firewall. Si rileva lo spoofing sul firewall e si distende la regola al proxy inverso, consentendo così alla forcella che richiede la mobilità.<BR>Usa l'host DNS (Domain Name System) o CNAME Records per definire il proxy inverso per il comportamento dei tornanti (non il firewall), se possibile.



</div>

Lync Server 2013 supporta i servizi di mobilità per i client mobili Lync 2010 per dispositivi mobili e Lync 2013. Entrambi i client usano il servizio di individuazione automatica di Lync Server 2013 per trovare il punto di ingresso per la mobilità, ma differiscono per il servizio di mobilità che usano. Lync 2010 Mobile USA il servizio di mobilità noto come *MCX*, introdotto con l'aggiornamento cumulativo per lync Server 2010: novembre 2011. I client mobili di Lync 2013 usano l'API Web Unified Communications o *UCWA*, come provider di servizi mobili.

<div>

## <a name="internal-and-external-dns-configuration"></a>Configurazione DNS interna ed esterna

La MCX servizi mobili (introdotta con l'aggiornamento cumulativo per Lync Server 2010: novembre 2011) e UCWA (introdotti negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013) usano DNS nello stesso modo.

Quando si usa l'individuazione automatica, i dispositivi mobili usano DNS per individuare le risorse. Durante la ricerca DNS, una connessione viene prima tentata con il nome di dominio completo associato al record DNS interno (lyncdiscoverinternal\< . nome\>di dominio interno). Se non è possibile effettuare una connessione usando il record DNS interno, viene tentata una connessione usando il record DNS esterno (lyncdiscover.\< SipDomain\>). Un dispositivo mobile interno alla rete si connette all'URL del servizio di individuazione automatica interno e un dispositivo mobile esterno alla rete si connette all'URL del servizio di individuazione automatica esterno. Le richieste di individuazione automatica esterne passano attraverso il proxy inverso. Il servizio di individuazione automatica di Lync Server 2013 restituisce tutti gli URL dei servizi Web per il pool di Home dell'utente, inclusi gli URL del servizio di mobilità (MCX e UCWA). Tuttavia, sia l'URL del servizio di mobilità interno che l'URL del servizio di mobilità esterna sono associati all'FQDN dei servizi Web esterni. Di conseguenza, indipendentemente dal fatto che un dispositivo mobile sia interno o esterno alla rete, il dispositivo si connette sempre al servizio di mobilità di Lync Server 2013 esternamente tramite il proxy inverso.

<div>


> [!NOTE]  
> È importante comprendere che la distribuzione può essere costituita da più spazi dei nomi distinti per l'uso interno ed esterno. Il nome di dominio SIP può essere diverso dal nome del dominio di distribuzione interno. Ad esempio, il dominio SIP può essere <STRONG>contoso.com</STRONG>, mentre la distribuzione interna può essere <STRONG>contoso.NET</STRONG>. Gli utenti che accedono a Lync Server utilizzeranno il nome di dominio SIP, ad esempio <STRONG>John@contoso.com</STRONG>. Quando si indirizzano i servizi Web esterni (definiti in Generatore di topologia come <STRONG>servizi Web esterni</STRONG>), il nome di dominio e il nome di dominio SIP saranno coerenti, come definito in DNS. Quando si indirizzano i servizi Web interni (definiti in Generatore di topologia come <STRONG>servizi Web interni</STRONG>), il nome predefinito dei servizi Web interni sarà l'FQDN del server front-end, del pool di front-end, del direttore o del pool di Director. È possibile eseguire l'override del nome dei servizi Web interni. È consigliabile usare il nome di dominio interno (e non il nome di dominio SIP) per i servizi Web interni e definire il record host DNS a (o, per IPv6, AAAA) per riflettere il nome sottoposto a override. Ad esempio, l'FQDN dei servizi Web interni predefiniti può essere <STRONG>pool01.contoso.NET</STRONG>. Un FQDN dei servizi Web interni sottoposti a override può essere <STRONG>webpool.contoso.NET</STRONG>. La definizione dei servizi Web in questo modo consente di verificare che la località interna ed esterna dei servizi e non la località dell'utente che li usa, sia osservata.<BR>Tuttavia, poiché i servizi Web sono definiti in Generatore di topologie e il nome dei servizi Web interni può essere ignorato, purché il nome dei servizi Web risultante, il certificato che lo convalida e i record DNS che la definiscono, siano coerenti, è possibile definire la Servizi Web interni con qualsiasi nome di dominio, incluso il nome di dominio SIP, che si desidera. In definitiva, la risoluzione per il nome dell'indirizzo IP è determinata dai record host DNS e uno spazio dei nomi coerente.<BR>Ai fini di questo argomento e degli esempi, il nome di dominio interno viene usato per illustrare la topologia e le definizioni DNS.



</div>

Il diagramma seguente illustra il flusso delle richieste Web dell'applicazione per dispositivi mobili per il servizio di mobilità e per il servizio di individuazione automatica quando si usa una configurazione DNS interna ed esterna.

**Flusso del servizio di mobilità con individuazione automatica**

![cdb96424-96f2-4ABF-88D7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4ABF-88D7-1d32d1010ffd")

<div>


> [!NOTE]  
> Il diagramma illustra i servizi Web generici. Una directory virtuale denominata Mobility descrive i servizi di mobilità MCX e/o UCWA. Se non sono stati applicati gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, è possibile che la directory virtuale UCWA definita nei servizi Web interni ed esterni. Si avrà una directory virtuale individuazione automatica e si potrebbe avere una directory virtuale MCX.<BR>L'individuazione automatica e il rilevamento dei servizi funzionano allo stesso modo, indipendentemente dalla tecnologia dei servizi mobili distribuiti.



</div>

Per supportare utenti mobili sia all'interno che all'esterno della rete aziendale, i nomi di dominio completi Web interni ed esterni devono soddisfare alcuni prerequisiti. Inoltre, potresti dover rispettare altri requisiti, a seconda delle caratteristiche che scegli di implementare:

  - Nuovi record DNS, CNAME o A (host, se IPv6, AAAA) per l'individuazione automatica.

  - Nuova regola del firewall, se si vuole supportare le notifiche push tramite la rete Wi-Fi.

  - Nomi alternativi oggetto di certificati server interni e certificati di reverse proxy per l'individuazione automatica.

  - La configurazione del bilanciamento del carico hardware del server front-end cambia l'affinità di origine.

La topologia deve soddisfare i requisiti seguenti per supportare il servizio di mobilità e il servizio di individuazione automatica:

  - Il nome FQDN interno del pool di front end deve essere distinto dall'FQDN Web esterno del pool Front-end.

  - Il nome di dominio completo Web interno deve essere risolto e accessibile dall'interno della rete aziendale.

  - Il nome FQDN Web esterno deve essere risolto e accessibile da Internet.

  - Per un utente che si trova all'interno della rete aziendale, l'URL del servizio di mobilità deve essere indirizzato al nome di dominio completo Web esterno. Questo requisito è per il servizio di mobilità e si applica solo a questo URL.

  - Per un utente esterno alla rete aziendale, la richiesta deve andare al nome FQDN Web esterno del pool o del direttore del front-end.

Se si supporta l'individuazione automatica, è necessario creare i record DNS seguenti per ogni dominio SIP:

  - Record DNS interno che supporta gli utenti di dispositivi mobili che si connettono dalla rete dell'organizzazione.

  - Un record DNS esterno o pubblico per supportare gli utenti di dispositivi mobili che si connettono da Internet.

L'URL di individuazione automatica interno non deve essere indirizzabile all'esterno della rete. L'URL di individuazione automatica esterna non deve essere indirizzabile dall'interno della rete. Tuttavia, se non è possibile soddisfare questo requisito per l'URL esterno, il client per dispositivi mobili non sarà probabilmente influenzato, perché l'URL interno viene sempre provato per primo.

I record DNS possono essere record CNAME o A (host, se IPv6, AAAA).

<div>


> [!NOTE]  
> I client di dispositivi mobili non supportano più certificati SSL (Secure Sockets Layer) provenienti da domini diversi. Di conseguenza, il reindirizzamento CNAME a domini diversi non è supportato su HTTPS. Ad esempio, un record CNAME DNS per lyncdiscover.contoso.com che reindirizza a un indirizzo di director.contoso.net non è supportato tramite HTTPS. In tale topologia, un client di dispositivi mobili deve usare HTTP per la prima richiesta, in modo che il reindirizzamento CNAME venga risolto tramite HTTP. Le richieste successive usano HTTPS. Per supportare questo scenario, è necessario configurare il proxy inverso con una regola di pubblicazione Web per la porta 80 (HTTP). Per informazioni dettagliate, vedere "per creare una regola di pubblicazione Web per la porta 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configurazione del proxy inverso per la mobilità in Lync Server 2013</A>.<BR>Il reindirizzamento CNAME allo stesso dominio è supportato tramite HTTPS. In questo caso, il certificato del dominio di destinazione copre il dominio di origine.



</div>

Per informazioni dettagliate sui record DNS necessari per lo scenario, vedere [Riepilogo DNS-individuazione automatica in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

</div>

<div>

## <a name="port-and-firewall-requirements"></a>Requisiti per la porta e il firewall

Se si supportano le notifiche push e si vuole che i dispositivi mobili Apple ricevano notifiche push tramite la rete Wi-Fi, è anche necessario aprire la porta 5223 sulla rete Wi-Fi aziendale. La porta 5223 è una porta TCP in uscita usata dal servizio di notifica push di Apple (APN). Il dispositivo mobile avvia la connessione. Per informazioni dettagliate, [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) vedere.

<div>


> [!WARNING]  
> Un dispositivo Apple che usa il client per dispositivi mobili Lync 2013 non richiede notifiche push.



</div>

Tieni presente che se un utente è ospitato in un Survivable Branch Appliance (SBA), sono necessarie le porte seguenti:

  - UcwaSipExternalListeningPort richiede la porta 5088

  - UcwaSipPrimaryListeningPort richiede la porta 5089

Per ulteriori informazioni e indicazioni sui requisiti per la porta e il protocollo per l'individuazione automatica, vedere [Riepilogo della porta-individuazione automatica in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

</div>

<div>

## <a name="certificate-requirements"></a>Requisiti per i certificati

Se si supporta l'individuazione automatica per i client mobili Lync, è necessario modificare gli elenchi di nomi alternativi oggetto in certificati per supportare connessioni sicure dai client mobili. È necessario richiedere e assegnare nuovi certificati, aggiungendo le voci alternative per i nomi degli argomenti descritti in questa sezione, per ogni server front-end e Director che esegue il servizio di individuazione automatica. L'approccio consigliato consiste nel modificare anche i nomi alternativi oggetto in certificati per i proxy inversi. È necessario aggiungere voci di nome alternative oggetto per ogni dominio SIP dell'organizzazione.

La riemissione di certificati tramite un'autorità di certificazione interna è in genere un processo semplice, ma l'aggiunta di più voci di nomi alternativi soggetto ai certificati pubblici usati dal proxy inverso può essere costosa. Se si hanno molti domini SIP, l'aggiunta di nomi alternativi soggetto è molto costosa, è possibile configurare il proxy inverso per eseguire la richiesta di servizio di individuazione automatica sulla porta 80 tramite HTTP, invece della porta 443 tramite HTTPS (la configurazione predefinita). La richiesta viene quindi reindirizzata alla porta 8080 nel pool di Director o front end. Quando si pubblica la richiesta di servizio di individuazione automatica iniziale nella porta 80, non è necessario modificare i certificati per il proxy inverso, perché la richiesta Usa HTTP anziché HTTPS. Questo approccio è supportato, ma non è consigliabile.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Requisiti di Internet Information Services (IIS)

È consigliabile usare IIS 7,5, IIS 8,0 o IIS 8,5 per la mobilità. Il programma di installazione del servizio di mobilità imposta i contrassegni in ASP.NET per migliorare le prestazioni. IIS 7,5 viene installato per impostazione predefinita in Windows Server 2008 R2, IIS 8,0 è installato in Windows Server 2012 e IIS 8,5 è installato in Windows Server 2012 R2. Il programma di installazione del servizio mobilità modifica automaticamente le impostazioni di ASP.NET.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Requisiti di bilanciamento del carico hardware

Nel servizio di bilanciamento del carico hardware che supporta il pool Front-End, i servizi Web esterni Virtual IPs (VIP) per il traffico di servizi Web devono essere configurati per l'origine. L'affinità di origine consente di garantire che più connessioni da un singolo client vengano inviate a un server per mantenere lo stato della sessione. Per informazioni dettagliate sui requisiti di affinità, vedere [requisiti di bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Se si prevede di supportare i client di Lync mobile solo tramite la rete Wi-Fi interna, è consigliabile configurare i VIP Servizi Web interni per l'origine, come descritto per i VIP dei servizi Web esterni. In questo caso, devi usare l'affinità origine\_addr (o TCP) per i VIP dei servizi Web interni nel servizio di bilanciamento del carico hardware. Per informazioni dettagliate, vedere [requisiti di bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

</div>

<div>

## <a name="reverse-proxy-requirements"></a>Requisiti del proxy inverso

Se si supporta l'individuazione automatica per i client mobili Lync, è necessario aggiornare la regola di pubblicazione corrente come indicato di seguito:

  - Se si decide di aggiornare gli elenchi di nomi alternativi oggetto nei certificati proxy inverso e si usa HTTPS per la richiesta di servizio di individuazione automatica iniziale, è necessario aggiornare la regola di pubblicazione Web per lyncdiscover. \<SipDomain\>. In genere, questo viene combinato con la regola di pubblicazione per l'URL dei servizi Web esterni nel pool Front-end.

  - Se si decide di usare HTTP per la richiesta di servizio di individuazione automatica iniziale, in modo che non sia necessario aggiornare l'elenco di nomi alternativi oggetto nei certificati proxy inverso, è necessario creare una nuova regola di pubblicazione Web per la porta HTTP/TCP 80, se non esiste già. Se una regola per HTTP/TCP 80 esiste già, è possibile aggiornare la regola per includere lyncdiscover. \<voce\> SipDomain.

</div>

</div>

<span> </span>

</div>

</div>

</div>

