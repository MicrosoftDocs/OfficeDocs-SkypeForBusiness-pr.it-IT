---
title: 'Lync Server 2013: Decisioni di pianificazione iniziali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dd1359e27f6869dab1ead38da3716135a2468ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Decisioni di pianificazione iniziali per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

La prima parte del processo di pianificazione consiste nel decidere quali carichi di lavoro di Lync Server e le caratteristiche principali desiderate per l'organizzazione.

1.  **Si vuole una distribuzione locale o online?**    Lync Server supporta entrambi gli scenari di distribuzione. Per altre informazioni su come prendere questa decisione, vedere [decidere come distribuire Lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md), più indietro in questa sezione

2.  **Si vuole una topologia fisica o virtualizzata?**    Lync Server supporta tutti i carichi di lavoro e i ruoli del server nelle topologie sia fisiche che virtualizzate. La capacità e la scalabilità degli utenti possono variare tra topologie fisiche e virtuali. Per altre informazioni, vedere [eseguire Lync server 2013 nei server virtuali](lync-server-2013-running-lync-server-on-virtual-servers.md).

3.  **La messaggistica istantanea *(im)* e la *presenza* sono sempre abilitate.**    In qualsiasi distribuzione di Lync Server, il carico di lavoro istantaneo (im) e la presenza sono installati e abilitati per impostazione predefinita. La messaggistica istantanea consente agli utenti di comunicare con messaggi di testo in tempo reale e la presenza consente loro di visualizzare lo stato di altri utenti nella rete. Lo stato presenza di un utente fornisce informazioni utili per consentire agli altri utenti di decidere se provare a contattare l'utente e in che modo. Per informazioni dettagliate, vedere [pianificazione per i server front-end, la messaggistica istantanea e la presenza in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) nella documentazione relativa alla pianificazione.

4.  **Si desidera distribuire qualsiasi modalità di conferenza?**    La funzionalità di conferenza è un'altra caratteristica principale di Lync Server. Sono supportate diverse modalità di conferenza. È possibile scegliere di distribuire tutti i tipi di servizi di conferenza supportati o solo alcuni di essi. *Web Conferencing* consente agli utenti di visualizzare un file, ad esempio una presentazione creata con Microsoft PowerPoint Presentation graphics Program, che viene presentato. La *condivisione delle applicazioni* consente agli utenti di condividere tutto o parte del desktop tra loro in tempo reale. Con i servizi di *conferenza a/V*, gli utenti possono aggiungere audio e possibilmente video alle loro conferenze e alle comunicazioni peer-to-peer. I servizi di *conferenza telefonica con accesso esterno* consentono agli utenti di usare telefoni PSTN standard per partecipare alla parte audio delle conferenze ospitate presso l'organizzazione. Per informazioni dettagliate, vedere Pianificazione per i servizi di [conferenza in Lync Server 2013](lync-server-2013-planning-for-conferencing.md) nella documentazione relativa alla pianificazione.
    
    In Lync Server 2013, se si distribuiscono i servizi di conferenza Web, è necessario pianificare l'integrazione con Office Web Apps Server per abilitare la condivisione e la visualizzazione di PowerPoint nelle riunioni. Per altre informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

5.  **Se si distribuisce una conferenza telefonica A/V, è consigliabile monitorare anche la qualità audio di queste conferenze.**    Molti fattori influenzano la qualità audio e video delle conferenze A/V di Lync Server. Tramite il monitoraggio è possibile monitorare la qualità A/V delle chiamate e delle conferenze. È possibile rilevare i problemi che interessano la qualità multimediale e verificare che gli utenti abbiano la migliore esperienza multimediale possibile. Per altre informazioni, vedere [pianificazione del monitoraggio in Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

6.  **Si desidera una disponibilità elevata per i server di messaggistica istantanea, presenza e conferenza?**    Se si dispone di un solo server in un sito che fornisce funzionalità di messaggistica istantanea, presenza e conferenza, la produttività degli utenti sarà fortemente influenzata se il server non funziona. Distribuendo un *pool* Enterprise Edition di almeno tre server per queste funzioni, è possibile che Lync Server continui a funzionare con tutte queste funzionalità intatte anche se un server non è disponibile.
    
    Un'altra opzione per le organizzazioni con 5000 o meno utenti che desiderano una disponibilità elevata consiste nel distribuire due server che utilizzano Lync Server Standard Edition e associare questi server insieme. Per altre informazioni, vedere [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

7.  **Si desiderano le opzioni di ripristino di emergenza?**    Se si hanno due centri dati e si vuole che le opzioni di ripristino di emergenza consentano agli utenti di continuare a lavorare se tutti o molti server di un Data Center scendono, è possibile distribuire i server con il ripristino di emergenza. Per questa distribuzione, è possibile associare un pool di server a un centro dati con un pool corrispondente in un altro centro dati. Se si abbassa un Data Center, l'altro pool nella coppia può servire gli utenti in entrambi i pool con l'interruzione minima dei servizi. Per altre informazioni, vedere [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

8.  **Si vuole consentire agli utenti di comunicare e collaborare con utenti esterni?**    L'attivazione della comunicazione e della collaborazione con utenti esterni può aumentare il ritorno sugli investimenti in Lync Server. In questo modo gli utenti dell'organizzazione possono trarre vantaggio dalle funzionalità di Lync Server anche quando lavorano all'esterno dei firewall dell'organizzazione. È anche possibile eseguire la Federazione con le organizzazioni partner o del cliente che eseguono Lync Server. In questo modo, gli utenti e gli utenti partner federati possono facilmente inviare e ricevere messaggi ISTANTANEi, invitarsi a riunioni e vedere la presenza dell'altro. Inoltre, gli utenti possono usare un messaggio di posta elettronica per invitare specifici utenti esterni alle conferenze che organizzano. Per altre informazioni, vedere [pianificazione per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

9.  **Si vuole distribuire Enterprise Voice?**     *Enterprise Voice* è la soluzione VoIP (Voice over IP) fornita da Lync Server. Offre un'alternativa interessante alla telefonia tradizionale basata su PBX. Enterprise Voice consente agli utenti di effettuare chiamate da computer o telefoni VoIP facendo clic su un contatto in Outlook o Lync Server. Possono effettuare chiamate tramite la rete IP da un computer a un computer, da un computer a un telefono o da un telefono al computer. Gli utenti traggono vantaggio dall'avere tutte le opzioni di comunicazione: voce, posta elettronica, messaggistica istantanea e servizi di conferenza, disponibili e integrate nei propri computer. Per informazioni dettagliate, vedere [pianificazione di Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) nella documentazione relativa alla pianificazione.

10. **Se si distribuisce VoIP aziendale, è consigliabile monitorare anche la qualità audio di queste chiamate.**    È consigliabile usare il monitoraggio per garantire la qualità audio delle chiamate vocali aziendali, se si distribuisce VoIP aziendale. Per altre informazioni, vedere [pianificazione del monitoraggio in Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

11. **È necessario archiviare contenuto di messaggistica istantanea o contenuto della riunione per scopi di conformità?**    Se l'organizzazione deve archiviare contenuto di messaggistica istantanea o contenuto della riunione per scopi di conformità, è possibile distribuire l'archiviazione. Per altre informazioni, vedere [pianificazione dell'archiviazione in Lync Server 2013](lync-server-2013-planning-for-archiving.md).

12. **Si vuole distribuire la chat persistente?**    Se si vuole consentire agli utenti di avere conversazioni in tempo reale che possono essere mantenute nel tempo, è possibile distribuire la chat persistente. Per altre informazioni, vedere [pianificazione del server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

13. **Si è distribuito Microsoft Exchange?**    Se l'organizzazione usa Microsoft Exchange Server per i propri servizi di posta elettronica, è possibile abilitare diverse funzionalità che migliorano l'utilità sia di Lync Server che di Microsoft Exchange Server. Alcune di queste funzionalità, denominate messaggistica UNIFICAta di Exchange, includono consentire agli utenti di ricevere notifiche per la segreteria telefonica e ascoltare la segreteria telefonica da Outlook o Outlook Web Access, accedere alle cassette postali di Microsoft Exchange tramite telefono e ricevere fax in cassette postali di Microsoft Exchange. Inoltre, se si dispone di Exchange 2013 distribuito, è possibile integrare gli archivi di contatti per gli utenti tra i due sistemi, usare Exchange per archiviare le foto di contatto a maggiore risoluzione e integrare l'archiviazione di messaggi di posta elettronica e messaggistica istantanea. Per altre informazioni, vedere [pianificazione dell'integrazione di Exchange Server con Lync server 2013](lync-server-2013-planning-for-exchange-server-integration.md).

14. **Sono presenti filiali nell'organizzazione?**    Se l'organizzazione dispone di filiali, Lync Server supporta diversi modi per supportarli e garantirne la resilienza per la voce e altre funzionalità. In particolare, in una filiale che non ha un collegamento WAN resiliente a un centro dati, è possibile installare un Survivable Branch Appliance o Survivable Branch Server per mantenere il supporto VoIP aziendale nel caso in cui il collegamento WAN (Wide Area Network) venga premuto. Per altre informazioni, vedere [pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

</div>

<span> </span>

</div>

</div>

</div>

