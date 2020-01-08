---
title: "Lync Server 2013: Requisiti dei certificati per l'accesso utente esterno"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e7a0802cee8b91e18eaf50e5c2c3942ca54308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Requisiti dei certificati per l'accesso utente esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-03-29_

Il software di comunicazione di Microsoft Lync Server 2013 supporta l'uso di un unico certificato pubblico per le interfacce esterne Edge di Access e Web Conferencing, oltre al servizio di autenticazione A/V. L'interfaccia interna di Edge in genere usa un certificato privato emesso da un'autorità di certificazione interna (CA), ma può anche usare un certificato pubblico, purché si trovi in una CA pubblica attendibile. Il proxy inverso nella distribuzione usa un certificato pubblico e crittografa la comunicazione dal proxy inverso ai client e il proxy inverso ai server interni tramite HTTP (ovvero, Transport Layer Security su HTTP).

Di seguito sono riportati i requisiti per il certificato pubblico usato per le interfacce esterne Edge di Access e Web Conferencing e il servizio di autenticazione A/V:

  - Il certificato deve essere emesso da un'autorità di certificazione pubblica approvata che supporta il nome alternativo soggetto. Per informazioni dettagliate, vedere l'articolo 929395 della Microsoft Knowledge Base "partner per i certificati delle comunicazioni unificate per Exchange Server e per [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)Communications Server".

  - Se il certificato verrà usato in un pool di Edge, deve essere creato come esportabile, con lo stesso certificato usato in ogni Edge Server nel pool di Edge. Il requisito della chiave privata esportabile è per gli scopi del servizio di autenticazione A/V, che deve usare la stessa chiave privata in tutti i server perimetrali nel pool.

  - Se si vuole massimizzare l'uptime per i servizi audio/video, esaminare i requisiti di certificato per l'implementazione di un certificato di servizio A/V Edge disaccoppiato, ovvero un certificato di servizio A/V Edge separato dagli altri scopi del certificato esterno. Per informazioni dettagliate, vedere [le modifiche apportate a Lync server 2013 che influiscono sulla pianificazione di Edge Server](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [pianificare i certificati Edge Server in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) e la [gestione dei certificati AV e OAuth in Lync Server 2013 con-roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).

  - Il nome dell'oggetto del certificato è l'interfaccia esterna del servizio di Access Edge Fully Qualified Domain Name (FQDN) o il bilanciamento del carico hardware VIP (ad esempio, access.contoso.com). ). Il nome soggetto non può avere un carattere jolly, ma deve essere un nome esplicito.
    
    <div>
    

    > [!NOTE]  
    > Per Lync Server 2013, questo non è più un requisito, ma è comunque consigliato per la compatibilità con Office Communications Server.

    
    </div>

  - L'elenco nome alternativo oggetto contiene gli FQDN seguenti:
    
      - Interfaccia esterna o servizio di bilanciamento del carico hardware VIP di Access Edge (ad esempio, sip.contoso.com).
        
        <div>
        

        > [!NOTE]  
        > Anche se il nome del soggetto del certificato è uguale all'FQDN di Access Edge, il nome dell'oggetto alternativo deve contenere anche il nome di dominio completo di Access Edge, perché Transport Layer Security (TLS) ignora i nomi dei soggetti e usa le voci alternative per il nome del soggetto convalida.

        
        </div>
    
      - Interfaccia esterna di Web Conferencing Edge o VIP di bilanciamento del carico hardware (ad esempio, webcon.contoso.com).
    
      - Se si usa la configurazione automatica client o la Federazione, includere anche gli FQDN di dominio SIP usati all'interno della società, ad esempio sip.contoso.com, sip.fabrikam.com.
    
      - Il servizio A/V Edge non usa il nome del soggetto o le voci alternative oggetto.
    
    <div>
    

    > [!NOTE]  
    > L'ordine degli FQDN nell'elenco nomi alternativi oggetto non ha importanza.

    
    </div>

Se si distribuiscono più server Edge con bilanciamento del carico in un sito, il certificato del servizio di autenticazione A/V installato in ogni server perimetrale deve essere della stessa autorità di certificazione e deve usare la stessa chiave privata. Tieni presente che la chiave privata del certificato deve essere esportabile, indipendentemente dal fatto che venga usata in un server perimetrale o in molti server perimetrali. Deve anche essere esportabile se Richiedi il certificato da qualsiasi computer diverso da Edge Server. Poiché il servizio di autenticazione A/V non usa il nome dell'oggetto o il nome alternativo dell'oggetto, è possibile riutilizzare il certificato di Access Edge purché vengano soddisfatti i requisiti per il nome dell'oggetto e l'oggetto alternativo per il bordo di accesso e il Web Conferencing Edge e la chiave privata del certificato sia esportabile.

I requisiti per il certificato privato (o pubblico) usato per l'interfaccia interna del bordo sono i seguenti:

  - Il certificato può essere emesso da una CA interna o da una CA di un certificato pubblico approvato.

  - Il nome dell'oggetto del certificato è in genere l'FQDN dell'interfaccia interna del bordo o del bilanciamento del carico hardware VIP (ad esempio, lsedge.contoso.com). Tuttavia, puoi usare un certificato con carattere jolly sul bordo interno.

  - Nessun elenco di nomi alternativi soggetto è obbligatorio.

Proxy inverso nelle richieste di servizi di distribuzione per:

  - Accesso degli utenti esterni al contenuto della riunione per le riunioni

  - Accesso degli utenti esterni per espandere e visualizzare i membri dei gruppi di distribuzione

  - Accesso degli utenti esterni ai file scaricabili dal servizio Rubrica

  - Accesso degli utenti esterni al client Lync Web App

  - Accesso degli utenti esterni alla pagina Web delle impostazioni dei servizi di conferenza telefonica con chiamata in ingresso

  - Accesso degli utenti esterni al servizio informazioni sulla posizione

  - Accesso al dispositivo esterno al servizio di aggiornamento del dispositivo e ottenere gli aggiornamenti

Il proxy inverso pubblica gli URL dei componenti Web di server interni. Gli URL dei componenti Web sono definiti in Director, Front End Server o front end pool come **servizi Web esterni** in Generatore di topologie.

Le voci con caratteri jolly sono supportate nel campo nome alternativo oggetto del certificato assegnato al proxy inverso. Per informazioni dettagliate su come configurare la richiesta di certificato per il proxy inverso, vedere [richiedere e configurare un certificato per il proxy inverso HTTP in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).

<div>

## <a name="see-also"></a>Vedere anche


[Supporto dei certificati con caratteri jolly in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

