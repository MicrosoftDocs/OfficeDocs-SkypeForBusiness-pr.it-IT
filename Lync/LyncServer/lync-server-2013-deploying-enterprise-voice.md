---
title: 'Lync Server 2013: distribuzione di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf57d55899d556ddfde633c975ae9f0516e48e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Distribuzione di VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

Lync Server 2013, Enterprise Voice fa parte dell'infrastruttura di Lync Server 2013.

La distribuzione di VoIP aziendale richiede che:

<div id="sectionSection0" class="section">

1.  Esaminare la sezione [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) della documentazione relativa alla pianificazione.

2.  Finalizzare i piani per le funzionalità e i componenti da distribuire con questo carico di lavoro.

3.  Eseguire lo strumento pianificazione per progettare una topologia che rispecchi le decisioni di distribuzione.

4.  Aprire la struttura della topologia in Generatore di topologia, come descritto in [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) nella documentazione relativa alla distribuzione.
    
    <div>
    

    > [!NOTE]  
    > L'installazione di generatore di topologia fa parte del processo di distribuzione per il pool interno. Per informazioni dettagliate, vedere <A href="lync-server-2013-install-lync-server-administrative-tools.md">installare gli strumenti di amministrazione di Lync Server 2013</A> nella documentazione relativa alla distribuzione.

    
    </div>

Inoltre, è necessario che sia già stato distribuito Lync Server, Enterprise Edition presso i siti centrali e i siti di succursale che corrispondono alla topologia di riferimento che si sceglie di distribuire. Non è possibile distribuire i componenti di VoIP aziendale finché non sono stati definiti, pubblicati e installati file per almeno un pool interno ed è necessario usare generatore di topologia per definire e pubblicare un pool interno.

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

Per visualizzare le topologie di riferimento con esempi di posizione in cui è possibile distribuire ruoli del server VoIP aziendale (e la loro relazione tra loro e altri ruoli del server di Lync Server 2013), vedere [topologie di riferimento in Lync server 2013](lync-server-2013-reference-topologies.md) nella documentazione relativa alla pianificazione.

Per visualizzare una topologia di riferimento che illustra e spiega una distribuzione del controllo di ammissione alle chiamate di esempio, incluse le aree di rete, i siti di rete e le subnet, vedere [esempio: raccolta dei requisiti per il controllo dell'ammissione delle chiamate in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> Per distribuire VoIP aziendale in un sito centrale, continuare a leggere gli argomenti in questa sezione. Per distribuire VoIP aziendale in un sito di succursale, passare alla <A href="lync-server-2013-deploying-branch-sites.md">distribuzione dei siti di succursale in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

Questa sezione include procedure per le distribuzioni in cui un Mediation Server è collocato in ogni server front-end o Standard Edition, come raccomandato e anche per le distribuzioni con un pool di Mediation Server autonomo.

È possibile ignorare il contenuto seguente se è stato usato generatore di topologie per definire e pubblicare una topologia che colloca un Mediation Server in ogni server front-end o Standard Edition, perché la distribuzione guidata ha già installato automaticamente i file per Mediation Server quando i file sono stati installati per il pool di front end server o per il server Standard Edition:

  - [Configurazione di trunk in Lync Server 2013](lync-server-2013-configuring-trunks.md)

Se è stato usato generatore di topologie per definire e pubblicare un Mediation Server in un pool autonomo, è possibile usare il contenuto seguente:

  - Verificare che la topologia soddisfi i prerequisiti software e ambiente, come descritto in [prerequisiti VoIP aziendale per Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).

</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - <span></span>  
    [Prerequisiti di VoIP aziendale per Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Distribuzione di Mediation Server e definizione di peer in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Configurazione di trunk in Lync Server 2013](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Configurazione dei dial plan in Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Esportazione e importazione della configurazione di route vocali in Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Testare il routing vocale in Lync Server 2013](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [Distribuzione della messaggistica unificata di Exchange in locale per fornire la funzionalità di segreteria telefonica di Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Fornire agli utenti di Lync Server 2013 la segreteria telefonica nella messaggistica unificata di Exchange ospitata](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [Configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Distribuzione di funzionalità vocali avanzate di Enterprise in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Informazioni su aree di rete, siti e subnet in Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Creare o modificare un'area di rete in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Creare o modificare un sito di rete in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Configurare il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Configurare i servizi di emergenza avanzati in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Configurare il bypass multimediale in Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Consentire agli utenti di VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione di siti di succursale in Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Configurazione di conferenze telefoniche con accesso esterno in Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Configurazione del parcheggio di chiamata in Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Configurazione degli annunci per i numeri non assegnati in Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Distribuzione del monitoraggio in Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

