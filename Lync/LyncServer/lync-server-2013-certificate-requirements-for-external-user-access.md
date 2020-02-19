---
title: "Lync Server 2013: requisiti dei certificati per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0561c2d6b36090a9499abf360373cf0468cdbda8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Requisiti dei certificati per l'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-03-29_

Il software di comunicazione Microsoft Lync Server 2013 supporta l'utilizzo di un singolo certificato pubblico per le interfacce esterne di Access e Web Conferencing Edge, oltre al servizio di autenticazione A/V. L'interfaccia interna perimetrale utilizza in genere un certificato privato emesso da un'autorità di certificazione (CA) interna, ma può anche utilizzare un certificato pubblico, purché provenga da una CA pubblica attendibile. Il proxy inverso della distribuzione utilizza un certificato pubblico e crittografa le comunicazioni dal proxy inverso ai client e dal proxy inverso ai server interni mediante HTTP, ovvero Transport Layer Security su HTTP.

Di seguito sono riportati i requisiti dei certificati pubblici utilizzati per le interfacce esterne dell'Access Edge Server e del Web Conferencing Edge Server, nonché per il servizio di autenticazione A/V:

  - Il certificato deve essere emesso da una CA pubblica approvata che supporta il nome alternativo del soggetto. Per informazioni dettagliate, vedere l'articolo 929395 della Microsoft Knowledge Base "partner di certificati per comunicazioni unificate per Exchange Server e per Communications [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)server" all'indirizzo.

  - Se il certificato verrà utilizzato in un pool di server perimetrali, deve essere creato come esportabile, con lo stesso certificato utilizzato in ogni server perimetrale del pool. Il requisito della chiave privata esportabile è previsto per il servizio di autenticazione A/V, che deve utilizzare la stessa chiave privata in tutti i server perimetrali del pool.

  - Se si desidera massimizzare il tempo di ingrandimento per i servizi audio/video, esaminare i requisiti dei certificati per l'implementazione di un certificato del servizio A/V Edge separato, ovvero un certificato del servizio A/V Edge A parte di altri scopi del certificato esterno. Per informazioni dettagliate, vedere [changes in Lync server 2013 che influiscono sulla pianificazione del server perimetrale](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [pianificare i certificati server perimetrali in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) e la [gestione temporanea dei certificati AV e OAuth in Lync Server 2013 utilizzando-roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).

  - Il nome del soggetto del certificato è l'interfaccia esterna del servizio Access Edge completo (FQDN) o il VIP del dispositivo di bilanciamento del carico hardware (ad esempio, access.contoso.com). ). Il nome del soggetto non può avere un carattere jolly, deve essere un nome esplicito.
    
    <div>
    

    > [!NOTE]  
    > Per Lync Server 2013, questo non è più un requisito, ma è comunque consigliato per la compatibilità con Office Communications Server.

    
    </div>

  - L'elenco di nomi alternativi del soggetto contiene i nomi FQDN dei componenti seguenti:
    
      - L'interfaccia esterna del servizio Access Edge o il VIP del dispositivo di bilanciamento del carico hardware (ad esempio, sip.contoso.com).
        
        <div>
        

        > [!NOTE]  
        > Anche se il nome del soggetto del certificato è uguale al nome FQDN dell'Access Edge Server, deve contenere anche questo FQDN perché Transport Layer Security (TLS) ignora il nome del soggetto e utilizza le voci dei nomi alternativi del soggetto per la convalida.

        
        </div>
    
      - L'interfaccia esterna del Web Conferencing Edge Server o il VIP del dispositivo di bilanciamento del carico hardware, ad esempio webcon.contoso.com.
    
      - Se si utilizza la configurazione automatica dei client o la federazione, includere anche eventuali FQDN di dominio SIP utilizzati all'interno dell'organizzazione, ad esempio sip.contoso.com, sip.fabrikam.com.
    
      - Il servizio A/V Edge non utilizza le voci Subject Name o Subject Alternative names.
    
    <div>
    

    > [!NOTE]  
    > L'ordine dei nomi FQDN nell'elenco di nomi alternativi del soggetto non è importante.

    
    </div>

Se si distribuiscono più server perimetrali con bilanciamento del carico in un sito, il certificato del servizio di autenticazione A/V installato in ogni server perimetrale deve provenire dalla stessa CA e deve utilizzare la stessa chiave privata. Si noti che la chiave privata del certificato deve essere esportabile, indipendentemente dal fatto che venga utilizzata in uno o in più server perimetrali. Deve essere esportabile anche se il certificato viene richiesto da qualsiasi altro computer diverso dal server perimetrale. Poiché il servizio di autenticazione A/V non utilizza il nome del soggetto o il nome alternativo del soggetto, è possibile riutilizzare il certificato dell'Access Edge Server, purché vengano soddisfatti i requisiti del nome del soggetto e del nome alternativo del soggetto per l'Access Edge Server e il Web Conferencing Edge Server e la chiave privata del certificato sia esportabile.

I requisiti per il certificato privato (o pubblico) utilizzato per l'interfaccia interna del server perimetrale sono i seguenti:

  - Il certificato può essere emesso da una CA interna o da una CA pubblica approvata.

  - Il nome del soggetto del certificato corrisponde in genere al nome FQDN dell'interfaccia interna perimetrale o al VIP del servizio di bilanciamento del carico hardware, ad esempio lsedge.contoso.com. È tuttavia possibile utilizzare anche un certificato con caratteri jolly.

  - Non è richiesto alcun elenco di nomi alternativi del soggetto.

Il proxy inverso dei servizi di distribuzione richiede:

  - Accesso di utenti esterni al contenuto delle riunioni

  - Accesso di utenti esterni per espandere e visualizzare i membri di gruppi di distribuzione

  - Accesso di utenti esterni a file scaricabili dal servizio Rubrica

  - Accesso degli utenti esterni al client Lync Web App

  - Accesso di utenti esterni alla pagina Web Impostazioni conferenza telefonica con accesso esterno

  - Accesso di utenti esterni al servizio Informazioni percorso

  - Accesso di utenti esterni al servizio Aggiornamento dispositivo e recupero di aggiornamenti

Il proxy inverso pubblica gli URL dei componenti Web del server interno. Gli URL dei componenti Web sono definiti in Director, Front End Server o pool Front end come **servizi Web esterni** in Generatore di topologie.

Le voci con caratteri jolly sono supportate nel campo del nome alternativo del soggetto del certificato assegnato al proxy inverso. Per informazioni dettagliate su come configurare la richiesta di certificato per il proxy inverso, vedere [request and Configure a certificate for your inverse http proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).

<div>

## <a name="see-also"></a>Vedere anche


[Supporto per i certificati con caratteri jolly in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

