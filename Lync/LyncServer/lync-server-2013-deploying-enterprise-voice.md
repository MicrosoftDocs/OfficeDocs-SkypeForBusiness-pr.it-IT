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
ms.openlocfilehash: 5a19016a095e38a0df70a561976c6b03d59fdfd1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Distribuzione di VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Lync Server 2013, VoIP aziendale fa parte dell'infrastruttura di Lync Server 2013.

Per la distribuzione di VoIP aziendale è necessario:

<div id="sectionSection0" class="section">

1.  Esaminare la sezione [pianificazione per VoIP aziendale in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) della documentazione relativa alla pianificazione.

2.  Finalizzare i piani per le funzionalità e i componenti da distribuire con questo carico di lavoro.

3.  Eseguire lo strumento di pianificazione per progettare una topologia che rispecchi le decisioni di distribuzione.

4.  Aprire la progettazione della topologia in Generatore di topologie, come descritto in [define and Configuring the topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) nella documentazione relativa alla distribuzione.
    
    <div>
    

    > [!NOTE]  
    > L'installazione di generatore di topologie è parte integrante del processo di distribuzione per il pool interno. Per informazioni dettagliate, vedere <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 Administrative Tools</A> nella documentazione relativa alla distribuzione.

    
    </div>

È inoltre necessario che sia già stato distribuito Lync Server, Enterprise Edition nei siti centrali e nei siti di succursale che corrispondono alla topologia di riferimento che si sceglie di distribuire. Non è possibile distribuire i componenti di VoIP aziendale fino a quando non sono stati definiti, pubblicati e installati file per almeno un pool interno ed è necessario utilizzare Generatore di topologie per definire e pubblicare un pool interno.

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

Per visualizzare le topologie di riferimento con esempi in cui è possibile distribuire i ruoli del server VoIP aziendale e la relazione tra loro e con altri ruoli del server Lync Server 2013, vedere [Reference Topologies in Lync server 2013](lync-server-2013-reference-topologies.md) nella documentazione relativa alla pianificazione.

Per visualizzare una topologia di riferimento in cui è illustrata una distribuzione del controllo di ammissione di chiamata di esempio, tra cui aree di rete, siti di rete e subnet, vedere [esempio: raccolta dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> Per distribuire VoIP aziendale in un sito centrale, continuare a leggere gli argomenti in questa sezione. Per distribuire VoIP aziendale in un sito di succursale, passare a <A href="lync-server-2013-deploying-branch-sites.md">distribuzione dei siti di succursale in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

In questa sezione sono incluse le procedure per le distribuzioni in cui un Mediation Server è collocato in ogni Front End Server o server Standard Edition, come consigliato, e anche per le distribuzioni con un pool Mediation Server autonomo.

Se è stato utilizzato il generatore di topologie per definire e pubblicare una topologia che colloca un Mediation Server in ogni Front End Server o server Standard Edition, è possibile ignorare il seguente contenuto, in quanto la distribuzione guidata ha già installato automaticamente i file per Mediation Server quando sono stati installati file per il pool Front End Server o il server Standard Edition:

  - [Configurazione di trunk in Lync Server 2013](lync-server-2013-configuring-trunks.md)

Se è stato utilizzato il generatore di topologie per definire e pubblicare un Mediation Server in un pool autonomo, è possibile utilizzare il contenuto seguente:

  - Verificare che la topologia soddisfi i prerequisiti del software e dell'ambiente, come descritto in [Enterprise Voice Prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).

</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - <span></span>  
    [Prerequisiti di VoIP aziendale per Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Distribuzione di Mediation Server e definizione di peer in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Configurazione di trunk in Lync Server 2013](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Configurazione di dial plan in Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Esportazione e importazione della configurazione del routing vocale in Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Testare il routing vocale in Lync Server 2013](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [Distribuzione della messaggistica unificata di Exchange locale per fornire la segreteria telefonica di Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Fornire ai messaggi vocali di Lync Server 2013 utenti la messaggistica unificata di Exchange ospitata](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [Configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Distribuzione di funzionalità di VoIP aziendale avanzate in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Informazioni su aree di rete, siti e subnet in Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Creare o modificare un'area di rete in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Creare o modificare un sito di rete in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Configurare il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Configurare Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Configurare il bypass multimediale in Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione di siti di succursale in Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Configurazione delle conferenze telefoniche con accesso esterno in Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Configurazione del parcheggio di chiamata in Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Configurazione degli annunci per i numeri non assegnati in Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Distribuzione del monitoraggio in Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

