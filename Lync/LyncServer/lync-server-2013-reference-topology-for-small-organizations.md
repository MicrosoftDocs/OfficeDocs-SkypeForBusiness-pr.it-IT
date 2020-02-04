---
title: Topologia di riferimento di Lync Server 2013 per le organizzazioni di piccole dimensioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e0171d9678d5d890cf4ecb81f6de25f9b558b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>Topologia di riferimento per Lync Server 2013 in piccole organizzazioni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-07_

La topologia di riferimento per le piccole organizzazioni Mostra come distribuire una soluzione robusta e altamente disponibile distribuendo solo tre server che esegue Lync Server.

**Topologia di riferimento per piccole organizzazioni**

![Diagramma della topologia di riferimento per la distribuzione di tre server](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Diagramma della topologia di riferimento per la distribuzione di tre server")

  - **Coppia di server standard distribuiti**     questa organizzazione ha 4.000 utenti nel loro sito centrale. L'organizzazione ha distribuito due server standard e li ha abbinati per consentire l'elevata disponibilità e il ripristino di emergenza. Ogni server abita 2.000 utenti, ma le informazioni su tutti gli utenti vengono sincronizzate tra i due server. Se si abbassa, un amministratore può eseguire il failover di questi utenti per essere serviti dall'altro server, con un minimo di interruzioni per gli utenti. Per altre informazioni sulle caratteristiche di disponibilità elevata e ripristino di emergenza in Lync Server 2013, vedere [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **È consigliabile distribuire Edge Server.**    Anche se la distribuzione di un server perimetrale non è necessaria per la messaggistica istantanea, la presenza e le conferenze interne, è consigliabile anche per piccole distribuzioni. Puoi massimizzare l'investimento di Lync Server distribuendo un server perimetrale per garantire il servizio agli utenti al di fuori dei firewall dell'organizzazione. I vantaggi includono i seguenti:
    
      - Gli utenti dell'organizzazione possono usare le funzionalità di Lync Server, se lavorano da casa o sono fuori strada.
    
      - Gli utenti possono invitare utenti esterni a partecipare alle riunioni.
    
      - Se si ha un partner, un fornitore o un'organizzazione di clienti che usa anche Lync Server, è possibile creare una *relazione federata* con tale organizzazione. La distribuzione di Lync Server riconoscerebbe quindi gli utenti di tale organizzazione federata, con una migliore collaborazione.
    
      - Gli utenti possono scambiare messaggi istantanei con utenti di servizi di messaggistica istantanea pubblici, inclusi uno o più dei seguenti: Windows Live, AOL\!, Yahoo e Google Talk. Potrebbe essere necessaria una licenza separata per la connettività di messaggistica istantanea pubblica con questi servizi.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio. Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
        > <LI>
        > <P>Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messenger. La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</P>
        > <LI>
        > <P>Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</P></LI></UL>

        
        </div>

  - **Sopravvivenza del sito della filiale.**    Questa organizzazione sta usando un programma pilota della funzionalità VoIP aziendale di Lync Server. Alcuni utenti usano Lync Server come soluzione vocale unica. Alcuni di questi utenti di Voice Pilot si trovano nel sito della filiale. Il sito di succursale non ha un collegamento WAN (Wide Area Network) affidabile al sito centrale, quindi viene distribuito un Survivable Branch Appliance. Con questa distribuzione, se il collegamento WAN si abbassa, gli utenti del sito della filiale possono ancora effettuare e ricevere chiamate (sia le chiamate all'interno dell'organizzazione che le chiamate PSTN), avere la funzionalità della segreteria telefonica e comunicare con messaggistica istantanea a due parti. Gli utenti possono essere autenticati anche quando il collegamento WAN non è disponibile.

  - **Distribuzione della messaggistica unificata di Exchange.** Questa topologia di riferimento include un server di messaggistica UNIFICAta di Exchange, che esegue Microsoft Exchange Server e non Lync Server.
    
    Per informazioni dettagliate sulla messaggistica unificata di Exchange, vedere [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) nella documentazione relativa alla pianificazione.

  - **Server di Office Web Apps.** È consigliabile distribuire un server di Office Web Apps o una server farm di Office Web Apps in tutte le organizzazioni che usano servizi di conferenza Web. Office Web Apps Server rende possibile la presentazione di diapositive di PowerPoint in conferenze Web. Per altre informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

</div>

<span> </span>

</div>

</div>

</div>

