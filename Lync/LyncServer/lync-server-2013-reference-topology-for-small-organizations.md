---
title: Topologia di riferimento per Lync Server 2013 per organizzazioni di piccole dimensioni
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
ms.openlocfilehash: 726056b63dfa37864171a77913b5126c23b27045
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>Topologia di riferimento per Lync Server 2013 in organizzazioni di piccole dimensioni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-07_

La topologia di riferimento per le organizzazioni di piccole dimensioni dimostra come è possibile distribuire una soluzione robusta e a disponibilità elevata distribuendo solo tre server che eseguono Lync Server.

**Topologia di riferimento per le organizzazioni di piccole dimensioni**

![Topologia di riferimento per la distribuzione di tre server diagramma](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Topologia di riferimento per la distribuzione di tre server diagramma")

  - **Coppia di server Standard Edition distribuiti**     in questa organizzazione sono disponibili 4.000 utenti nel sito centrale. L'organizzazione ha distribuito due server Standard Edition e li ha accoppiati insieme per abilitare la disponibilità elevata e il ripristino di emergenza. Ogni server Homes 2.000 utenti, ma le informazioni su tutti gli utenti vengono sincronizzate tra i due server. Se si abbassa, un amministratore può avere esito negativo su quegli utenti che devono essere serviti dall'altro server, con un minimo di interruzioni per gli utenti. Per ulteriori informazioni sulle funzionalità di disponibilità elevata e ripristino di emergenza in Lync Server 2013, vedere [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **La distribuzione del server perimetrale è consigliata.**    Anche se la distribuzione di un server perimetrale non è necessaria per la messaggistica istantanea, la presenza e le conferenze interne, è consigliabile anche per le distribuzioni di piccole dimensioni. È possibile massimizzare l'investimento di Lync Server distribuendo un server perimetrale per fornire il servizio agli utenti attualmente esterni ai firewall dell'organizzazione. Tra i vantaggi derivanti dall'utilizzo di server perimetrali sono inclusi i seguenti:
    
      - Gli utenti dell'organizzazione possono utilizzare le funzionalità di Lync Server, se lavorano da casa o sono in viaggio.
    
      - Gli utenti possono invitare utenti esterni a partecipare alle riunioni.
    
      - Se si dispone di un partner, un fornitore o un'organizzazione del cliente che utilizza anche Lync Server, è possibile creare una *relazione federata* con tale organizzazione. La distribuzione di Lync Server dovrebbe quindi riconoscere gli utenti provenienti da tale organizzazione federata, determinando una maggiore collaborazione.
    
      - Gli utenti possono scambiare messaggi istantanei con gli utenti di servizi di messaggistica istantanea pubblici, inclusi uno o più dei seguenti: Windows Live,\!AOL, Yahoo e Google Talk. Potrebbe essere necessaria una licenza separata per la connettività di messaggistica istantanea pubblica con questi servizi.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio. Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
        > <LI>
        > <P>Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo! Messaggero. La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</P>
        > <LI>
        > <P>Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</P></LI></UL>

        
        </div>

  - **Survivable site di succursale.**    Questa organizzazione esegue un programma pilota della caratteristica VoIP aziendale di Lync Server. Alcuni utenti utilizzano Lync Server come soluzione vocale unica. Alcuni di questi utenti sono ubicati nel sito di succursale. Il sito di succursale non dispone di un collegamento WAN (Wide Area Network) affidabile al sito centrale, quindi viene distribuito un Survivable Branch Appliance. Con questa distribuzione, se il collegamento WAN si abbassa, gli utenti del sito di succursale possono ancora effettuare e ricevere chiamate (sia le chiamate all'interno dell'organizzazione che le chiamate PSTN), hanno la funzionalità della segreteria telefonica e comunicano con la messaggistica istantanea con due parti. Gli utenti possono inoltre essere autenticati anche quando il collegamento WAN non è disponibile.

  - **Distribuzione di Messaggistica unificata di Exchange.** Questa topologia di riferimento include un server di messaggistica unificata di Exchange, che esegue Microsoft Exchange Server, non Lync Server.
    
    Per informazioni dettagliate sulla messaggistica UNIFICAta di Exchange, vedere [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) nella documentazione relativa alla pianificazione.

  - **Server Office Web Apps.** È consigliabile distribuire un server Office Web Apps o una farm di server Office Web Apps in ogni organizzazione che utilizza le conferenze Web. Il server Office Web Apps rende possibile la presentazione di diapositive di PowerPoint nelle conferenze Web. Per ulteriori informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

</div>

<span> </span>

</div>

</div>

</div>

