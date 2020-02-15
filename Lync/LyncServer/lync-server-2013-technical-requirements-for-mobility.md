---
title: 'Lync Server 2013: requisiti tecnici per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb4c1eacf48940822ddb26ac41f238ccdb4452dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Requisiti tecnici per i dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Gli utenti di dispositivi mobili hanno a che fare con diversi scenari di applicazioni per dispositivi mobili che richiedono una pianificazione speciale. Ad esempio, qualcuno potrebbe iniziare a utilizzare un'applicazione per dispositivi mobili mentre è lontano dal lavoro collegandosi tramite la rete 3G, quindi passare alla rete Wi-Fi aziendale quando arriva al lavoro e quindi tornare a 3G quando si esce dall'edificio. È necessario pianificare l'ambiente per supportare tali transizioni di rete e garantire un'esperienza utente coerente. In questa sezione vengono descritti i requisiti dell'infrastruttura necessari per supportare le applicazioni mobili e l'individuazione automatica delle risorse mobili.

<div>


> [!NOTE]  
> Anche se le applicazioni mobili possono connettersi ad altri servizi di Lync Server 2013, il requisito di inviare tutte le richieste Web dell'applicazione per dispositivi mobili allo stesso nome di dominio completo (FQDN) del sito Web esterno è valido solo per il servizio per dispositivi mobili di Lync Server 2013. Altri servizi per dispositivi mobili non richiedono questa configurazione.



</div>

Il requisito dell'affinità dei cookie nei dispositivi di bilanciamento del carico hardware è ridotto drasticamente e si sostituisce l'affinità TCP (Transmission Control Protocol) se si utilizza Lync mobile recapitato con Lync Server 2013. È comunque possibile utilizzare l'affinità dei cookie, ma non è più necessario per i servizi Web.

<div>


> [!IMPORTANT]  
> Tutto il traffico del servizio per dispositivi mobili passa attraverso il proxy inverso, indipendentemente dalla posizione in cui si trova il punto di origine, ovvero interno o esterno. Nel caso di un singolo proxy inverso o di una farm di proxy inversi oppure di un dispositivo che fornisce la funzione proxy inverso, è possibile che si verifichi un problema quando il traffico interno viene egressing tramite un'interfaccia e si tenta di eseguire immediatamente l'ingresso sulla stessa interfaccia. Questo porta spesso a una violazione della regola di sicurezza nota come spoofing del pacchetto TCP o solo spoofing. Il <EM>blocco dei capelli</EM> (l'uscita e l'ingresso immediato di un pacchetto o di una serie di pacchetti) deve essere consentito affinché i dispositivi mobili funzionino. Un modo per risolvere il problema consiste nell'utilizzare un proxy inverso separato dal firewall (la regola di prevenzione dello spoofing dovrebbe essere sempre applicata al firewall, per motivi di sicurezza). La tornante può verificarsi all'interfaccia esterna del proxy inverso anziché all'interfaccia esterna del firewall. È possibile rilevare lo spoofing sul firewall e rilassare la regola nel proxy inverso, consentendo in tal modo la forcella che richiede la mobilità.<BR>Utilizzare l'host DNS (Domain Name System) o i record CNAME per definire il proxy inverso per il comportamento dei tornanti (non il firewall), se possibile.



</div>

Lync Server 2013 supporta i servizi per dispositivi mobili per i client di Lync 2010 mobile e Lync 2013 mobile. Entrambi i client utilizzano il servizio di individuazione automatica di Lync Server 2013 per individuare il punto di ingresso per dispositivi mobili, ma differiscono per il servizio per dispositivi mobili che utilizzano. Lync 2010 Mobile utilizza il servizio per dispositivi mobili noto come *MCX*, introdotto con l'aggiornamento cumulativo per lync Server 2010: novembre 2011. I client per dispositivi mobili Lync 2013 utilizzano l'API Web Unified Communications o *UCWA*, come provider del servizio di mobilità.

<div>

## <a name="internal-and-external-dns-configuration"></a>Configurazione del DNS interno ed esterno

I servizi per dispositivi mobili MCX (introdotti con l'aggiornamento cumulativo per Lync Server 2010: novembre 2011) e UCWA (introdotti negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013) usano DNS nello stesso modo.

Quando si utilizza il servizio di individuazione automatica, i dispositivi mobili utilizzano DNS per individuare le risorse. Durante la ricerca DNS, viene innanzitutto tentata una connessione al nome di dominio completo associato al record DNS interno (lyncdiscoverinternal.\< nome\>di dominio interno). Se non è possibile effettuare una connessione utilizzando il record DNS interno, viene tentata una connessione utilizzando il record DNS esterno (lyncdiscover.\< SipDomain\>). Un dispositivo mobile interno alla rete si connette all'URL interno del servizio di individuazione automatica, mentre un dispositivo mobile esterno alla rete si connette all'URL esterno del servizio di individuazione automatica. Le richieste di individuazione automatica esterne passano attraverso il proxy inverso. Il servizio di individuazione automatica di Lync Server 2013 restituisce tutti gli URL dei servizi Web per il pool di Home dell'utente, inclusi gli URL del servizio per dispositivi mobili (MCX e UCWA). Sia l'URL interno che quello esterno del servizio per dispositivi mobili, tuttavia, sono associati al nome FQDN esterno dei servizi Web. Pertanto, indipendentemente dal fatto che un dispositivo mobile sia interno o esterno alla rete, il dispositivo si connette sempre al servizio per dispositivi mobili Lync Server 2013 esternamente tramite il proxy inverso.

<div>


> [!NOTE]  
> È importante comprendere che la distribuzione può essere costituita da più spazi dei nomi distinti per l'utilizzo interno ed esterno. Il nome di dominio SIP potrebbe essere diverso dal nome di dominio di distribuzione interno. Ad esempio, il dominio SIP potrebbe essere <STRONG>contoso.com</STRONG>, mentre la distribuzione interna potrebbe essere <STRONG>contoso.NET</STRONG>. Gli utenti che accedono a Lync Server utilizzeranno il nome di dominio SIP, ad esempio <STRONG>John@contoso.com</STRONG>. Quando si indirizzano i servizi Web esterni (definiti in Generatore di topologie come <STRONG>servizi Web esterni</STRONG>), il nome di dominio e il nome di dominio SIP saranno coerenti, come definito in DNS. Quando si indirizzano i servizi Web interni (definiti in Generatore di topologie come <STRONG>servizi Web interni</STRONG>), il nome predefinito dei servizi Web interni sarà l'FQDN del server front end, del pool Front End, del Director o del pool di Director. È possibile eseguire l'override del nome dei servizi Web interni. È consigliabile utilizzare il nome di dominio interno (e non il nome di dominio SIP) per i servizi Web interni e definire il record host DNS a (o, per IPv6, AAAA) per riflettere il nome sottoposto a override. Ad esempio, l'FQDN dei servizi Web interni predefiniti potrebbe essere <STRONG>pool01.contoso.NET</STRONG>. Un FQDN dei servizi Web interni sottoposti a override potrebbe essere <STRONG>webpool.contoso.NET</STRONG>. La definizione dei servizi Web in questo modo consente di garantire che la località interna ed esterna dei servizi, e non la località dell'utente che li utilizza, sia osservata.<BR>Tuttavia, poiché i servizi Web sono definiti in Generatore di topologie e il nome dei servizi Web interni può essere ignorato, purché il nome dei servizi Web risultante, il certificato che la convalida e i record DNS che lo definiscono, siano coerenti, è possibile definire il Servizi Web interni con qualsiasi nome di dominio, incluso il nome di dominio SIP, che si desidera. Infine, la risoluzione per il nome dell'indirizzo IP è determinata dai record host DNS e da uno spazio dei nomi coerente.<BR>Ai fini di questo argomento e degli esempi, il nome di dominio interno viene utilizzato per illustrare la topologia e le definizioni DNS.



</div>

Nel diagramma seguente viene illustrato il flusso delle richieste Web dell'applicazione mobile per il servizio per dispositivi mobili e il servizio di individuazione automatica quando si utilizza una configurazione DNS interna ed esterna.

**Flusso del servizio per dispositivi mobili tramite individuazione automatica**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> Nel diagramma sono illustrati i servizi Web generici. Una directory virtuale denominata Mobility descrive i servizi per dispositivi mobili MCX e/o UCWA. Se non sono stati applicati gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, è possibile che la directory virtuale UCWA sia definita nei servizi Web interni ed esterni. Si avrà una directory virtuale di individuazione automatica e potrebbe essere presente una directory virtuale MCX.<BR>La funzionalità di individuazione automatica e la ricerca dei servizi funzionano allo stesso modo, indipendentemente dalla tecnologia dei servizi per dispositivi mobili distribuita.



</div>

Per supportare gli utenti mobili sia all'interno che all'esterno della rete aziendale, i nomi FQDN Web interni ed esterni devono soddisfare alcuni requisiti. È inoltre necessario che vengano soddisfatti altri requisiti, a seconda delle caratteristiche che si sceglie di implementare:

  - Nuovi record DNS, CNAME o A (host, se IPv6, AAAA) per l'individuazione automatica.

  - Nuova regola del firewall, se si desidera supportare le notifiche push tramite la rete Wi-Fi.

  - Nomi alternativi del soggetto sui certificati del server interno e sui certificati del proxy inverso, per l'individuazione automatica.

  - La configurazione del bilanciamento del carico hardware front end server cambia l'affinità di origine.

La topologia deve soddisfare i requisiti seguenti per supportare il servizio per dispositivi mobili e il servizio di individuazione automatica:

  - Il nome FQDN Web interno del pool Front end deve essere diverso dal nome FQDN Web esterno del pool Front end.

  - Il nome FQDN Web interno deve essere risolto solo all'interno della rete aziendale ed essere accessibile solo da tale posizione.

  - Il nome FQDN Web esterno deve essere risolto solo per essere accessibile da Internet.

  - Per un utente che si trova all'interno della rete aziendale, l'URL del servizio per dispositivi mobili deve essere indirizzato al nome FQDN Web esterno. Questo requisito riguarda il servizio per dispositivi mobili e si applica solo a questo URL.

  - Per un utente che si trova all'esterno della rete aziendale, la richiesta deve passare all'FQDN Web esterno del pool Front end o del server Director.

Se l'individuazione automatica è supportata, è necessario creare i record DNS seguenti per ogni dominio SIP:

  - Un record DNS interno per supportare gli utenti di dispositivi mobili che si connettono dall'interno della rete dell'organizzazione.

  - Un record DNS esterno, o pubblico, per supportare gli utenti di dispositivi mobili che si connettono da Internet.

L'URL interno di individuazione automatica non deve essere raggiungibile dall'esterno della rete. L'URL esterno di individuazione automatica non deve essere raggiungibile dall'interno della rete. Tuttavia, se non è possibile rispettare questo requisito per l'URL esterno, il client per dispositivi mobili probabilmente non verrà influenzato, poiché l'URL interno viene sempre provato per primo.

I record DNS possono essere record CNAME o A (host, se IPv6, AAAA).

<div>


> [!NOTE]  
> I client dei dispositivi mobili non supportano certificati SSL (Secure Sockets Layer) multipli da domini diversi. Di conseguenza, il reindirizzamento CNAME a domini diversi non è supportato in HTTPS. Ad esempio, un record CNAME DNS per lyncdiscover.contoso.com che esegue il reindirizzamento a un indirizzo director.contoso.net non è supportato in HTTPS. In una topologia di questo tipo, un client di dispositivo portatile deve utilizzare il protocollo HTTP per la prima richiesta, in modo che il reindirizzamento CNAME venga risolto in HTTP. Per le richieste successive viene quindi utilizzato HTTPS. Per supportare questo scenario, è necessario configurare il proxy inverso con una regola di pubblicazione Web per la porta 80 (HTTP). Per informazioni dettagliate, vedere la sezione relativa alla creazione di una regola di pubblicazione Web per la porta 80 in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013</A>.<BR>Il reindirizzamento CNAME allo stesso dominio è supportato in HTTPS. In questo caso, il certificato del dominio di destinazione copre il dominio di origine.



</div>

Per informazioni dettagliate sui record DNS necessari per lo scenario, vedere [DNS Summary-Autodiscover in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).

</div>

<div>

## <a name="port-and-firewall-requirements"></a>Requisiti relativi a porte e firewall

Se si supportano le notifiche push e si desidera che i dispositivi mobili Apple possano ricevere le notifiche push tramite la rete Wi-Fi, è necessario anche aprire la porta 5223 nella rete Wi-Fi aziendale. La porta 5223 è una porta TCP in uscita utilizzata dal servizio notifica Push Apple. Il dispositivo mobile avvia la connessione. Per informazioni dettagliate, [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) vedere.

<div>


> [!WARNING]  
> Un dispositivo Apple che utilizza il client per dispositivi mobili Lync 2013 non richiede notifiche push.



</div>

Si noti che se un utente è ospitato in un Survivable Branch Appliance (SBA), sono necessarie le seguenti porte:

  - UcwaSipExternalListeningPort richiede la porta 5088

  - UcwaSipPrimaryListeningPort richiede la porta 5089

Per ulteriori informazioni e indicazioni sui requisiti relativi a porte e protocolli per l'individuazione automatica, vedere [Riepilogo delle porte-individuazione automatica in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).

</div>

<div>

## <a name="certificate-requirements"></a>Requisiti relativi ai certificati

Se si supporta l'individuazione automatica per i client mobili Lync, è necessario modificare gli elenchi dei nomi alternativi soggetto dei certificati per supportare le connessioni sicure dai client mobili. È necessario richiedere e assegnare nuovi certificati, aggiungendo le voci del nome alternativo del soggetto descritte in questa sezione, per ogni Front End Server e Director che esegue il servizio di individuazione automatica. L'approccio consigliato prevede inoltre la modifica anche degli elenchi dei nomi alternativi soggetto dei certificati per i proxy inversi. È necessario aggiungere voci di nomi alternativi soggetto per ogni dominio SIP dell'organizzazione.

La riemissione di certificati utilizzando un'Autorità di certificazione interna è in genere un processo semplice, ma l'aggiunta di più voci di nomi alternativi soggetto ai certificati pubblici utilizzati dal proxy inverso può essere un'operazione dispendiosa. Se sono presenti molti domini SIP, e pertanto l'aggiunta di nomi alternativi soggetto è molto dispendiosa, è possibile configurare il proxy inverso per effettuare la richiesta iniziale al servizio di individuazione automatica tramite la porta 80 utilizzando il protocollo HTTP, anziché la porta 443 utilizzando il protocollo HTTPS (configurazione predefinita). La richiesta viene quindi reindirizzata alla porta 8080 nel pool di Director o front end. Quando si pubblica la richiesta iniziale al servizio di individuazione automatica nella porta 80, non è necessario modificare i certificati per il proxy inverso, in quanto per la richiesta viene utilizzato HTTP anziché HTTPS. Questo approccio è supportato, ma non è consigliabile.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Requisiti relativi a IIS (Internet Information Services)

È consigliabile utilizzare IIS 7,5, IIS 8,0 o IIS 8,5 per la mobilità. Il programma di installazione del servizio per dispositivi mobili imposta i flag in ASP.NET per migliorare le prestazioni. IIS 7,5 è installato per impostazione predefinita in Windows Server 2008 R2, IIS 8,0 è installato in Windows Server 2012 e IIS 8,5 è installato in Windows Server 2012 R2. Il programma di installazione del servizio per dispositivi mobili modifica automaticamente le impostazioni di ASP.NET.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Requisiti relativi al servizio di bilanciamento del carico hardware

Nel servizio di bilanciamento del carico hardware che supporta il pool Front End, è necessario configurare l'IP virtuale (VIP) dei servizi Web esterni per il traffico dei servizi Web per l'origine. L'affinità di origine consente di garantire che più connessioni da un singolo client vengano inviate a un solo server per mantenere lo stato della sessione. Per informazioni dettagliate sui requisiti di affinità, vedere [requisiti per il bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

Se si prevede di supportare i client per dispositivi mobili Lync solo tramite la rete Wi-Fi interna, è consigliabile configurare i VIP dei servizi Web interni per l'origine come descritto per i VIP dei servizi Web esterni. In questo caso, è necessario utilizzare l'\_affinità di origine addr (o TCP) per i VIP dei servizi Web interni nel servizio di bilanciamento del carico hardware. Per ulteriori informazioni, vedere [requisiti per il bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

</div>

<div>

## <a name="reverse-proxy-requirements"></a>Requisiti relativi al proxy inverso

Se si supporta l'individuazione automatica per i client mobili di Lync, è necessario aggiornare la regola di pubblicazione corrente come indicato di seguito:

  - Se si decide di aggiornare gli elenchi dei nomi alternativi del soggetto nei certificati del proxy inverso e utilizzare HTTPS per la richiesta di servizio di individuazione automatica iniziale, è necessario aggiornare la regola di pubblicazione Web per lyncdiscover. \<SipDomain\>. Questo è in genere combinato con la regola di pubblicazione per l'URL dei servizi Web esterni nel pool Front end.

  - Se si decide di utilizzare HTTP per la richiesta iniziale del servizio di individuazione automatica in modo che non sia necessario aggiornare l'elenco dei nomi alternativi del soggetto nei certificati del proxy inverso, è necessario creare una nuova regola di pubblicazione Web per la porta HTTP/TCP 80, se non ne esiste già una. Se una regola per HTTP/TCP 80 esiste già, è possibile aggiornare la regola in modo da includere il lyncdiscover. \<voce\> SipDomain.

</div>

</div>

<span> </span>

</div>

</div>

</div>

