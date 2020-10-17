---
title: 'Lync Server 2013: configurazione dei server proxy inversi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 640d8e97cf8b7a31e11cb2dc8f1b1394e4b1aae3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521813"
---
# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Configurazione dei server proxy inversi per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-08_

Per le distribuzioni di Microsoft Lync Server 2013 Edge Server, è necessario un proxy inverso HTTPS nella rete perimetrale per i client esterni per accedere ai servizi Web di Lync Server 2013 (denominati *componenti Web* in Office Communications Server) nel Director e nel pool Home dell'utente. Di seguito sono riportate alcune funzionalità che richiedono l'accesso esterno tramite un proxy inverso:

  - Consentire agli utenti esterni di scaricare il contenuto delle riunioni.

  - Consentire agli utenti esterni di espandere i gruppi di distribuzione.

  - Consentire agli utenti remoti di scaricare file dal servizio Rubrica.

  - Accesso al client Lync Web App.

  - Accedere alla pagina Web Impostazioni conferenza telefonica con accesso esterno.

  - Consentire ai dispositivi esterni di connettersi al servizio Web di aggiornamento dispositivi e ottenere gli aggiornamenti.

  - Consentire alle applicazioni mobili di individuare e utilizzare automaticamente gli URL mobili (MCX) da Internet.

  - Abilitazione del client Lync 2013, dell'app Lync Windows Store e del client per dispositivi mobili Lync 2013 per individuare gli URL di individuazione delle scoperte (individuazione automatica) di Lync e utilizzare Unified Communications Web API (UCWA).

È consigliabile configurare il proxy inverso HTTP per la pubblicazione di tutti i servizi Web in tutti i pool. Publishing https://ExternalFQDN/ \* pubblica tutte le directory virtuali di IIS per un pool. È necessaria una regola di pubblicazione per ogni server Standard Edition, pool Front End, Director o pool di server Director presente nell'organizzazione.

È inoltre necessario pubblicare gli URL semplici. Se l'organizzazione dispone di un Director o di un pool di server Director, il proxy inverso HTTP resterà in attesa delle richieste HTTP/HTTPS relative agli URL semplici e le invierà tramite proxy alla directory virtuale dei servizi Web esterni nel Director o nel pool di server Director. Se non è stato distribuito un Director, sarà necessario designare un pool per la gestione delle richieste dirette agli URL semplici. Se non si tratta del pool principale dell'utente, le richieste verranno reindirizzate ai servizi Web in tale pool principale. Gli URL semplici possono essere gestiti da una regola di pubblicazione Web dedicata oppure è possibile aggiungerli ai nomi pubblici della regola di pubblicazione Web per il Director. È inoltre necessario pubblicare l'URL del servizio di individuazione automatica esterno.

È possibile utilizzare Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 o Internet Information Server 7,0, 7,5 o 8,0 con Application Request Routing (IIS ARR) come proxy inverso. Nei passaggi dettagliati di questa sezione viene descritto come configurare Forefront Threat Management Gateway 2010, in quanto i passaggi per configurare ISA Server 2006 sono praticamente identici. Vengono inoltre fornite indicazioni per IIS ARR. Se si utilizza un proxy inverso diverso, consultare la documentazione relativa a tale prodotto e mappare i requisiti definiti qui alle caratteristiche associate in altri proxy inversi.

<div>


> [!IMPORTANT]  
> Internet Information Server Application Request Routing (IIS ARR) è un'opzione completamente testata e supportata per l'implementazione di un proxy inverso per Lync Server 2010 e Lync Server 2013. Nel novembre 2012, Microsoft ha interrotto la vendita delle licenze di ForeFront Threat Management Gateway 2010 o TMG. La TMG è ancora un prodotto pienamente supportato ed è ancora disponibile per la vendita su elettrodomestici venduti da terze parti. Inoltre, molti dispositivi di bilanciamento del carico hardware di terze parti e firewall forniscono supporto per il proxy inverso. Per i servizi di bilanciamento del carico hardware e firewall che forniscono funzionalità di proxy inverso, consultare il fornitore per istruzioni specifiche su come configurare il proprio prodotto per fornire il supporto per il proxy inverso per Lync Server. È inoltre possibile visualizzare terze parti che hanno inviato documentazione per il proprio prodotto a Microsoft. Il supporto tecnico viene fornito da terze parti per la propria soluzione. Per visualizzare terze parti attive nella fornitura di soluzioni, vedere <A href="https://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.



</div>

Negli argomenti e nelle procedure seguenti viene utilizzato Forefront Threat Management Gateway 2010 e IIS ARR come base per le procedure di distribuzione e configurazione.

  - [Configurare i nomi di dominio completi della Web farm per Lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Configurare le schede di rete in Lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Richiedere e configurare un certificato per il proxy inverso HTTP in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Configurare le regole di pubblicazione Web per un singolo pool interno in Lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Verificare o configurare l'autenticazione e la certificazione nelle directory virtuali di IIS in Lync Server 2013](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Creare record DNS per i server proxy inversi in Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Verificare l'accesso tramite il proxy inverso in Lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>Operazioni preliminari

Per una distribuzione corretta di Forefront Threat Management Gateway 2010 come proxy inverso, è necessario impostare e configurare un server, utilizzando i prerequisiti e i requisiti hardware definiti nella documentazione di Forefront Threat Management Gateway 2010. Vedere l'argomento seguente impostato per configurare correttamente l'hardware e per installare Forefront Threat Management Gateway 2010 sul server prima di continuare.

  - <span></span>  
    [Forefront Threat Management Gateway (TMG) 2010](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Consigli sull'hardware di Forefront TMG 2010](https://go.microsoft.com/fwlink/?linkid=291293)

Per distribuire correttamente IIS ARR come proxy inverso, esaminare gli argomenti seguenti per configurare l'hardware e il software prerequisito.

  - <span></span>  
    Per installare IIS su Windows Server 2008 o Windows Server 2008 R2, vedere [Installing IIS 7 on Windows server 2008 o Windows server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)

  - <span></span>  
    Per installare IIS su Windows Server 2012, vedere [installazione di IIS 8 su Windows server 2012](https://go.microsoft.com/fwlink/?linkid=291297)

  - <span></span>  
    Per installare IIS su Windows Server 2012 R2, vedere [installazione di iis 8,5 su Windows server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)

  - <span></span>  
    Per scaricare l'estensione di routing delle richieste di applicazioni per IIS, seguire le istruzioni sul [download di Application Request Routing v 2.5](https://go.microsoft.com/fwlink/?linkid=291298)

  - <span></span>  
    Per installare ARR, per le istruzioni riportate in [Install Application Request Routing versione 2](https://go.microsoft.com/fwlink/?linkid=291299)
    
    <div>
    

    > [!NOTE]  
    > Le istruzioni attualmente pubblicate sono per ARR 2,0. Per l'installazione dell'estensione, non esiste alcuna differenza tra le due versioni.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

