---
title: Supporto per i certificati con caratteri jolly di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d639ba422bde7b936bd58ff58abae47ea365bb70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508523"
---
# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Supporto per i certificati con caratteri jolly in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-21_

Lync Server 2013 utilizza i certificati per fornire la crittografia delle comunicazioni e l'autenticazione dell'identità del server. In alcuni casi, ad esempio per la pubblicazione Web tramite il proxy inverso, non è necessaria la corrispondenza esatta tra la voce di nome alternativo del soggetto e il nome di dominio completo (FQDN) del server che presenta il servizio. In questi casi è possibile utilizzare certificati con voci di nome alternativo del soggetto con caratteri jolly, comunemente noti come "certificati con caratteri jolly", per ridurre il costo di un certificato richiesto a un'autorità di certificazione pubblica e per semplificare il processo di pianificazione per i certificati.

<div>


> [!WARNING]  
> Per mantenere la funzionalità dei dispositivi per le comunicazioni unificate, quali ad esempio i telefoni da tavolo, è necessario verificare attentamente il certificato distribuito per assicurarsi che i dispositivi funzionino correttamente dopo l'implementazione di un certificato con caratteri jolly.



</div>

Non viene fornito il supporto per una voce con caratteri jolly come nome soggetto, ovvero come nome comune o CN, per alcun ruolo. Quando si utilizzano voci con caratteri jolly nel nome alternativo del soggetto, sono supportati i ruoli del server seguenti:

  - <span></span>  
    **Proxy inverso.**     La voce SAN jolly è supportata per il certificato di pubblicazione URL semplice (Meet e dialin).

  - <span></span>  
    **Proxy inverso.**     La voce SAN jolly è supportata per le voci SAN per LyncDiscover nel certificato di pubblicazione.

  - <span></span>  
    **Director.**     La voce SAN jolly è supportata per gli URL semplici (Meet e dialin) e per le voci SAN per LyncDiscover e LyncDiscoverInternal in Director Web Components.

  - <span></span>  
    **Front End Server (Standard Edition) e pool Front End (Enterprise Edition).** La voce SAN jolly è supportata per gli URL semplici (Meet e dialin) e per le voci SAN per LyncDiscover e LyncDiscoverInternal nei componenti Web front-end.

  - <span></span>  
    Messaggistica unificata di **Exchange (UM).**     Il server non utilizza le voci di SAN quando viene distribuito come server autonomo.

  - <span></span>  
    **Server Accesso client di Microsoft Exchange Server.**     Le voci con caratteri jolly nel SAN sono supportate per i client interni ed esterni.

  - <span></span>  
    **Messaggistica unificata di Exchange e server Accesso client di Microsoft Exchange Server sullo stesso server.**     Sono supportate le voci di SAN con caratteri jolly.

In questo argomento non vengono trattati i ruoli del server seguenti:

  - Ruoli del server interni (inclusi, ma non limitati al Mediation Server, all'archiviazione e al Monitoring Server, Survivable Branch Appliance o Survivable Branch Server)

  - Interfacce server perimetrali esterne

  - Server perimetrale interno
    
    <div>
    

    > [!NOTE]  
    > Per l'interfaccia del server perimetrale interno, è possibile assegnare una voce con caratteri jolly alla rete SAN ed è supportata. La SAN nel server perimetrale interno non è sottoposta a query e una voce SAN jolly è di valore limitato.

    
    </div>

Per informazioni dettagliate sulle configurazioni dei certificati, incluso l'utilizzo di caratteri jolly nei certificati, vedere i seguenti argomenti:

  - [Requisiti dei certificati per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisiti dei certificati per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Riepilogo del certificato-bilanciamento del carico DNS e del caricamento in Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Riepilogo del certificato-singolo amministratore in Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Riepilogo del certificato-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware in Lync 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Riepilogo del certificato-proxy inverso in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Linee guida per l'integrazione della messaggistica unificata locale e di Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Per informazioni dettagliate sulla configurazione dei certificati per Exchange, incluso l'utilizzo di caratteri jolly, vedere la documentazione del prodotto Exchange 2013.

</div>

<span> </span>

</div>

</div>

</div>

