---
title: 'Lync Server 2013: Supporto dei certificati con caratteri jolly'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9422c3bebbb5fb32be88cfe5c41968207bbed2ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Supporto dei certificati con caratteri jolly in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-21_

Lync Server 2013 USA i certificati per consentire l'autenticazione delle comunicazioni e delle identità del server. In alcuni casi, ad esempio la pubblicazione Web tramite il proxy inverso, il nome di voce alternativo soggetto forte (SAN) corrispondente al nome di dominio completo (FQDN) del server che presenta il servizio non è obbligatorio. In questi casi, è possibile usare i certificati con le voci SAN jolly (comunemente note come "certificati con caratteri jolly") per ridurre il costo di un certificato richiesto da un'autorità di certificazione pubblica e ridurre la complessità del processo di pianificazione per i certificati .

<div>


> [!WARNING]  
> Per mantenere la funzionalità dei dispositivi UC (Unified Communications), ad esempio i telefoni da tavolo, è consigliabile testare attentamente il certificato distribuito per verificare che i dispositivi funzionino correttamente dopo l'implementazione di un certificato con caratteri jolly.



</div>

Per qualsiasi ruolo non è disponibile alcun supporto per una voce con carattere jolly come nome dell'oggetto, denominato anche nome comune o CN. I ruoli del server seguenti sono supportati quando si usano voci con caratteri jolly nella SAN:

  - <span></span>  
    **Proxy inverso.**    La voce San jolly è supportata per il certificato di pubblicazione URL semplice (riunione e chiamata).

  - <span></span>  
    **Proxy inverso.**    La voce San jolly è supportata per le voci San per Lyncdiscover nel certificato di pubblicazione.

  - <span></span>  
    **Director.**    La voce San jolly è supportata per gli URL semplici (riunione e chiamata) e per le voci San per Lyncdiscover e lyncdiscoverinternal in Director Web Components.

  - <span></span>  
    **Server front-end (Standard Edition) e pool Front-End (Enterprise Edition).** La voce SAN jolly è supportata per gli URL semplici (riunione e chiamata) e per le voci SAN per LyncDiscover e LyncDiscoverInternal nei componenti Web front-end.

  - <span></span>  
    **Messaggistica unificata di Exchange (UM).**    Il server non usa le voci San quando viene distribuito come server autonomo.

  - <span></span>  
    **Server Accesso client di Microsoft Exchange Server.**    Le voci con caratteri jolly nella San sono supportate per i client interni ed esterni.

  - <span></span>  
    **Messaggistica UNIFICAta di Exchange e server Accesso client di Microsoft Exchange Server nello stesso server.**    Sono supportate le voci San con caratteri jolly.

Ruoli del server non trattati in questo argomento:

  - Ruoli del server interni (inclusi, ma non limitati a Mediation Server, server di archiviazione e monitoraggio, Survivable Branch Appliance o Survivable Branch Server)

  - Interfacce di Edge Server esterne

  - Server perimetrale interno
    
    <div>
    

    > [!NOTE]  
    > Per l'interfaccia Internal Edge Server, è possibile assegnare una voce con carattere jolly alla SAN ed è supportata. La SAN nel server perimetrale interno non viene eseguita una query e una voce SAN con carattere jolly è di valore limitato.

    
    </div>

Per informazioni dettagliate sulle configurazioni dei certificati, incluso l'uso di caratteri jolly nei certificati, vedere gli argomenti seguenti:

  - [Requisiti dei certificati per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisiti dei certificati per l'accesso utente esterno in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Riepilogo dei certificati - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Riepilogo dei certificati - singolo server Director in Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Riepilogo dei certificati - pool di server Director con scalabilità implementata, servizio di bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Riepilogo dei certificati - proxy inverso in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Linee guida per l'integrazione della messaggistica unificata locale con Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Per informazioni dettagliate sulla configurazione dei certificati per Exchange, incluso l'uso di caratteri jolly, vedere la documentazione del prodotto Exchange 2013.

</div>

<span> </span>

</div>

</div>

</div>

