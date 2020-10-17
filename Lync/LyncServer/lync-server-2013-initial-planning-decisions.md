---
title: Decisioni di pianificazione iniziale di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fdc9b9e2494078a8db4b524e9ffb6b2794c545d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512573"
---
# <a name="initial-planning-decisions-for-lync-server-2013"></a>Decisioni di pianificazione iniziali per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

La prima parte del processo di pianificazione è la scelta dei carichi di lavoro di Lync Server e delle caratteristiche principali desiderate per l'organizzazione.

1.  **Si desidera una distribuzione online o locale?**     Lync Server supporta entrambi gli scenari di distribuzione. Per ulteriori informazioni su come prendere questa decisione, vedere [decidere come distribuire Lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md), più indietro in questa sezione

2.  **Si desidera una topologia fisica o virtualizzata?**     Lync Server supporta tutti i carichi di lavoro e i ruoli del server sia nelle topologie fisiche che virtualizzate. La capacità utenti e la scalabilità possono differire tra topologia virtualizzata e topologia fisica. Per ulteriori informazioni, vedere [esecuzione di Lync Server 2013 nei server virtuali](lync-server-2013-running-lync-server-on-virtual-servers.md).

3.  La **messaggistica *(IM)* istantanea e la *presenza* sono sempre attivate.**     In qualsiasi distribuzione di Lync Server, il carico di lavoro per la messaggistica istantanea e la presenza sono installati e abilitati per impostazione predefinita. La messaggistica istantanea consente agli utenti di comunicare con messaggi di testo in tempo reale, mentre la presenza consente loro di visualizzare lo stato di altri utenti connessi in rete. Lo stato di presenza di un utente fornisce informazioni che consentono ad altri utenti di decidere se provare o meno a contattarlo e secondo quali modalità. Per informazioni dettagliate, vedere [pianificazione di front end server, messaggistica istantanea e presenza in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) nella documentazione relativa alla pianificazione.

4.  **Si desidera distribuire qualsiasi modalità di conferenza?**     La funzionalità di conferenza è un'altra caratteristica principale di Lync Server. Sono supportate diverse modalità di conferenza. È possibile scegliere di distribuire tutti i tipi di conferenza supportati o solo alcuni di essi. *Web Conferencing* consente agli utenti di visualizzare un file, ad esempio un Deck diapositiva creato con il programma di grafica di presentazione di Microsoft PowerPoint, che viene presentato. La *condivisione delle applicazioni* consente agli utenti di condividere in tempo reale tutto o parte del proprio desktop. Con *a/V Conferencing*, gli utenti possono aggiungere audio (e possibilmente video) alle proprie conferenze e alle comunicazioni peer-to-peer. I servizi di *conferenza telefonica con accesso esterno* consentono agli utenti di utilizzare telefoni PSTN standard per partecipare alla parte audio delle conferenze ospitate all'interno dell'organizzazione. Per informazioni dettagliate, vedere [Planning for Conferencing in Lync Server 2013](lync-server-2013-planning-for-conferencing.md) nella documentazione relativa alla pianificazione.
    
    In Lync Server 2013, se si distribuiscono Web Conferencing, è inoltre necessario pianificare l'integrazione con il server Office Web Apps per abilitare la condivisione e la visualizzazione di PowerPoint nelle riunioni. Per ulteriori informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

5.  **Se si distribuisce la funzionalità di conferenza A/V, è necessario monitorare anche la qualità audio di queste conferenze.**     Molti fattori influiscono sulla qualità audio e video delle conferenze A/V di Lync Server. Se si utilizza il monitoraggio, è possibile monitorare la qualità A/V delle chiamate e delle conferenze. È possibile rilevare i problemi che influiscono sulla qualità multimediale e assicurarsi che gli utenti abbiano la migliore esperienza multimediale possibile. Per ulteriori informazioni, vedere [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

6.  **Si desidera un'elevata disponibilità per i server di messaggistica istantanea, presenza e conferenza?**     Se si dispone di un solo server in un sito che fornisce funzionalità di messaggistica istantanea, presenza e conferenza, la produttività degli utenti sarà fortemente intaccata se il server viene abbassato. Distribuendo un *pool* Enterprise Edition di almeno tre server per queste funzioni, è possibile che Lync Server continui a funzionare con tutte queste funzionalità intatte anche se un server non è disponibile.
    
    Un'altra opzione per le organizzazioni con 5000 o meno utenti che desiderano una disponibilità elevata consiste nel distribuire due server che eseguono Lync Server Standard Edition e associare questi server insieme. Per ulteriori informazioni, vedere [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

7.  **Si desiderano le opzioni di ripristino di emergenza?**     Se si dispone di due centri dati e si desidera che le opzioni di ripristino di emergenza consentano agli utenti di continuare a funzionare se tutti i server di un centro dati vengono disattivati, è possibile distribuire i server con il ripristino di emergenza. Per questa distribuzione, si accoppia un pool di server di un data center con un pool corrispondente in un altro data center. Se si verifica un errore in un data center, l'altro pool della coppia può gestire gli utenti di entrambi i pool con un'interruzione minima dei servizi. Per ulteriori informazioni, vedere [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

8.  **Si desidera consentire agli utenti di comunicare e collaborare con utenti esterni?**     L'abilitazione della comunicazione e della collaborazione con gli utenti esterni può aumentare il rendimento degli investimenti in Lync Server. In questo modo gli utenti dell'organizzazione possono trarre vantaggio dalle funzionalità di Lync Server anche quando lavorano all'esterno dei firewall dell'organizzazione. È inoltre possibile eseguire la Federazione con le organizzazioni partner o dei clienti che eseguono Lync Server. In questo modo, gli utenti e il partner federato possono inviare e ricevere facilmente messaggi istantanei, invitarsi alle riunioni e visualizzare informazioni sulla rispettiva presenza. Possono inoltre utilizzare un messaggio di posta elettronica per invitare specifici utenti esterni alle conferenze da essi organizzate. Per ulteriori informazioni, vedere [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

9.  **Si desidera distribuire VoIP aziendale?**     *Enterprise Voice* è la soluzione VoIP (Voice over IP) fornita da Lync Server. Fornisce un'alternativa interessante alla telefonia tradizionale basata su PBX. VoIP aziendale consente agli utenti di effettuare chiamate dal proprio computer o dal proprio telefonino facendo clic su un contatto in Outlook o Lync Server. Possono effettuare chiamate tramite la rete IP da un computer a un computer, da un computer a un altro o da un telefono a un computer. Gli utenti possono usufruire di tutte le opzioni di comunicazione-voce, posta elettronica, messaggistica istantanea e servizi di conferenza-disponibili e integrate nei propri computer. Per informazioni dettagliate, vedere [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) nella documentazione relativa alla pianificazione.

10. **Se si distribuisce VoIP aziendale, è necessario monitorare anche la qualità audio delle chiamate.**     Se si distribuisce VoIP aziendale, è consigliabile utilizzare il monitoraggio per garantire la qualità audio delle chiamate vocali dell'organizzazione. Per ulteriori informazioni, vedere [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

11. **È necessario archiviare contenuto di messaggistica istantanea o soddisfare la riunione per scopi di conformità?**     Se l'organizzazione deve archiviare contenuto di messaggistica istantanea o soddisfare le riunioni per scopi di conformità, è possibile distribuire l'archiviazione. Per ulteriori informazioni, vedere [Planning for archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md).

12. **Si desidera distribuire la chat persistente?**     Se si desidera consentire agli utenti di avere conversazioni in tempo reale che possono essere mantenute nel tempo, è possibile distribuire Chat persistente. Per ulteriori informazioni, vedere [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

13. **Microsoft Exchange è stato distribuito?**     Se l'organizzazione utilizza Microsoft Exchange Server per i propri servizi di posta elettronica, è possibile abilitare diverse funzionalità che migliorano l'utilità sia di Lync Server che di Microsoft Exchange Server. Alcune di queste funzionalità, denominate messaggistica unificata di Exchange, includono la possibilità per gli utenti di ricevere notifiche di segreteria telefonica e ascoltare la segreteria telefonica da Outlook o Outlook Web Access, di accedere alle cassette postali di Microsoft Exchange utilizzando un telefono e di ricevere fax nelle loro cassette postali di Microsoft Exchange. Inoltre, se si dispone di Exchange 2013 distribuito, è possibile integrare gli archivi contatti per gli utenti tra i due sistemi, utilizzare Exchange per archiviare le foto dei contatti di maggiore risoluzione e integrare l'archiviazione di messaggi di posta elettronica e di messaggistica istantanea. Per ulteriori informazioni, vedere [Planning for Exchange Server Integration with Lync server 2013](lync-server-2013-planning-for-exchange-server-integration.md).

14. **Sono presenti succursali nell'organizzazione?**     Se nell'organizzazione sono presenti succursali, Lync Server supporta vari modi per supportarli e garantire la propria resilienza per la voce e altre caratteristiche. In particolare, in una succursale che non dispone di un collegamento WAN resiliente a un Data Center, è possibile installare un Survivable Branch Appliance o un Survivable Branch Server per gestire il supporto VoIP aziendale nel caso in cui il collegamento WAN (Wide Area Network) venga premuto. Per ulteriori informazioni, vedere [pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

</div>

<span> </span>

</div>

</div>

</div>

