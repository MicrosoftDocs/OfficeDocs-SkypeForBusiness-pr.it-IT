---
title: 'Lync Server 2013: Configurare server proxy inversi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef13f2351ab74c0e3b2ba558a9dbf0aef43d71b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Configurare server proxy inversi per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-08_

Per le distribuzioni di Microsoft Lync Server 2013 Edge Server, è necessario un proxy inverso HTTPS nella rete perimetrale per i client esterni per accedere ai servizi Web di Lync Server 2013 (detti *Web Components* in Office Communications Server) sul Director e sul pool di Home dell'utente. Di seguito sono elencate alcune delle caratteristiche che richiedono l'accesso esterno tramite proxy inverso:

  - Consentire agli utenti esterni di scaricare il contenuto della riunione per le riunioni.

  - Consentire agli utenti esterni di espandere i gruppi di distribuzione.

  - Consentire agli utenti remoti di scaricare file dal servizio Rubrica.

  - Accesso al client Lync Web App.

  - Accedere alla pagina Web delle impostazioni di conferenza telefonica con accesso esterno.

  - Abilitazione di dispositivi esterni per la connessione al servizio Web Update per dispositivi e per ottenere gli aggiornamenti.

  - Consentendo alle applicazioni mobili di individuare e utilizzare automaticamente gli URL di mobilità (MCX) da Internet.

  - Abilitare il client Lync 2013, l'app Lync di Windows Store e il client per dispositivi mobili Lync 2013 per individuare gli URL di individuazione di Lync (individuazione automatica) e usare Unified Communications Web API (UCWA).

È consigliabile configurare il proxy inverso HTTP per pubblicare tutti i servizi Web in tutti i pool. Pubblicazione di https://ExternalFQDN\* /pubblica tutte le directory virtuali di IIS per un pool. È necessaria una regola di pubblicazione per ogni server Standard Edition, pool Front-end o pool di Director o Director nell'organizzazione.

Inoltre, devi pubblicare gli URL semplici. Se l'organizzazione ha un pool di Director o Director, il proxy inverso HTTP ascolta le richieste HTTP/HTTPS per gli URL semplici e li delega alla directory virtuale dei servizi Web esterni nel pool di Director o Director. Se non è stato distribuito un Director, è necessario designare un pool per gestire le richieste per gli URL semplici. Se non si tratta del pool di Home dell'utente, verranno reindirizzati ai servizi Web nel pool Home dell'utente. Gli URL semplici possono essere gestiti da una regola di pubblicazione Web dedicata oppure aggiungerli ai nomi pubblici della regola di pubblicazione Web per il Director. Devi anche pubblicare l'URL del servizio di individuazione automatica esterna.

È possibile usare Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 o Internet Information Server 7,0, 7,5 o 8,0 con Application Request Routing (IIS ARR) come proxy inverso. La procedura dettagliata in questa sezione descrive come configurare Forefront Threat Management Gateway 2010 e la procedura per la configurazione di ISA Server 2006 è quasi identica. Vengono fornite indicazioni anche per IIS ARR. Se si usa un proxy inverso diverso, consultare la documentazione relativa al prodotto e mappare i requisiti definiti in questa sezione alle caratteristiche associate in altri proxy inversi.

<div>


> [!IMPORTANT]  
> Internet Information Server Application Request Routing (IIS ARR) è un'opzione completamente testata e supportata per l'implementazione di un proxy inverso per Lync Server 2010 e Lync Server 2013. In novembre 2012, Microsoft ha cessato le vendite di licenze di ForeFront Threat Management Gateway 2010 o TMG. TMG è ancora un prodotto completamente supportato ed è ancora disponibile per la vendita sugli elettrodomestici venduti da terze parti. Inoltre, molti dispositivi di bilanciamento del carico hardware e firewall di terze parti garantiscono il supporto del proxy inverso. Per i dispositivi di bilanciamento del carico hardware e i firewall che includono funzionalità proxy inversa, consultare il fornitore per istruzioni specifiche su come configurare il proprio prodotto per consentire il supporto del proxy inverso per Lync Server. È anche possibile visualizzare le terze parti che hanno inviato la documentazione per il proprio prodotto a Microsoft. Il supporto viene fornito dalla terza parte per la soluzione. Per visualizzare le terze parti attive nella fornitura di soluzioni, vedere <A href="http://go.microsoft.com/fwlink/?linkid=268730">infrastruttura qualificata per Microsoft Lync</A>.



</div>

Gli argomenti e le procedure seguenti usano Forefront Threat Management Gateway 2010 e IIS ARR come base per le procedure di distribuzione e configurazione.

  - [Configurare i nomi di dominio completi (FQDN) delle Web farm per Lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Configurare le schede di rete in Lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Richiedere e configurare un certificato per il proxy inverso HTTP in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Configurare le regole di pubblicazione Web per un singolo pool interno in Lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Verificare o configurare l'autenticazione e la certificazione nelle directory virtuali IIS in Lync Server 2013](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Creare record DNS per server proxy inversi in Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Verificare l'accesso tramite il proxy inverso in Lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>Prima di iniziare

Per distribuire correttamente Forefront Threat Management Gateway 2010 come proxy inverso, è necessario installare e configurare un server usando i prerequisiti e i requisiti hardware definiti nella documentazione di Forefront Threat Management Gateway 2010. Vedere l'argomento seguente impostato per configurare correttamente l'hardware e per installare Forefront Threat Management Gateway 2010 sul server prima di procedere.

  - <span></span>  
    [Forefront Threat Management Gateway (TMG) 2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Raccomandazioni hardware di Forefront TMG 2010](http://go.microsoft.com/fwlink/?linkid=291293)

Per distribuire correttamente IIS ARR come proxy inverso, esaminare gli argomenti seguenti per configurare l'hardware e il software prerequisito.

  - <span></span>  
    Per installare IIS in Windows Server 2008 o Windows Server 2008 R2, vedere [installazione di IIS 7 in Windows server 2008 o Windows server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)

  - <span></span>  
    Per installare IIS in Windows Server 2012, vedere [installazione di IIS 8 in Windows server 2012](http://go.microsoft.com/fwlink/?linkid=291297)

  - <span></span>  
    Per installare IIS in Windows Server 2012 R2, vedere [installazione di iis 8,5 in Windows server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)

  - <span></span>  
    Per scaricare l'estensione di routing della richiesta di applicazione per IIS, seguire le istruzioni alla [richiesta di applicazione routing v 2.5 download](http://go.microsoft.com/fwlink/?linkid=291298)

  - <span></span>  
    Per installare ARR, per le istruzioni su [Install Application Request Routing versione 2](http://go.microsoft.com/fwlink/?linkid=291299)
    
    <div>
    

    > [!NOTE]  
    > Le istruzioni attualmente pubblicate sono per ARR 2,0. Per l'installazione dell'estensione, non c'è differenza tra le due versioni.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

