---
title: 'Lync Server 2013: nuove funzionalità del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6203e6a7ee99f4b080fa93976a2a937e62fe9d3c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Nuove funzionalità del server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

Lync Server 2013, il server Chat persistente consente di partecipare a conversazioni a più parti, basate su argomenti che persistono nel tempo. Il server Chat persistente può aiutare l'organizzazione a eseguire le operazioni seguenti:

  - Migliorare le comunicazioni tra team interfunzionali e distribuiti in zone geografiche diverse

  - Ampliare la condivisione delle informazioni e la partecipazione

  - Migliorare le comunicazioni con l'organizzazione estesa

  - Ridurre il sovraccarico di informazioni

  - Migliorare la consapevolezza delle informazioni

  - Migliorare la diffusione di informazioni e conoscenze importanti

Lync Server 2013, il server Chat persistente non è disponibile in Microsoft 365 o Office 365. In questo momento, è disponibile solo per i clienti di Lync 2013 locali.

In Lync 2013, la funzionalità chat persistente è integrata nel client Lync 2013. Di conseguenza, gli utenti possono accedere a messaggistica istantanea/presenza, audio/video, conferenze e chat persistente tutti nel client Lync 2013. Per ulteriori informazioni sul client Lync 2013, vedere <https://go.microsoft.com/fwlink/p/?linkid=270877> .

In questo argomento vengono descritte le modifiche apportate alla caratteristica tra la nuova versione di Lync Server 2013, il server Chat persistente e la versione precedente (Microsoft Lync Server 2010, Group Chat), tra cui:

  - Fornire un'esperienza amministrativa nel pannello di controllo di Lync Server ed eliminare lo strumento di amministrazione di Group Chat

  - Integrazione delle impostazioni di configurazione per il server Chat persistente in Generatore di topologie eliminando lo strumento di configurazione di Group Chat

  - Semplificare la migrazione e l'aggiornamento dalle versioni precedenti del server Chat persistente

  - Fornire soluzioni di disponibilità elevata e ripristino di emergenza

Per ulteriori informazioni sulla versione più recente del server Chat persistente, vedere gli argomenti seguenti:

  - La guida per la chat persistente in <https://go.microsoft.com/fwlink/p/?linkid=270945> cui viene fornito un elenco dettagliato delle funzionalità di chat persistente, il loro funzionamento e come utilizzarle durante l'esecuzione del server Chat persistente.

  - La [pianificazione del server Chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione [distribuzione del server Chat persistente in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) nella documentazione relativa alla distribuzione, [migrazione da Lync Server 2010, Group chat o Office Communications Server 2007 R2 group chat a Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) nella documentazione relativa alla migrazione e [gestione di Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) nella documentazione relativa alle operazioni, che forniscono tutte le istruzioni per la configurazione del server Chat persistente.

  - Il file di documentazione. msi del server di chat persistente (file di Windows Installer) consente agli utenti di accedere alla documentazione offline completa sul server Chat persistente.

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>Modifiche alla topologia chiave per il server Chat persistente

Di seguito sono riportate le seguenti modifiche di alto livello per il server Chat persistente:

Il server Chat persistente è ora un ruolo del server. In Microsoft Lync Server 2010, Group Chat Server era un'applicazione attendibile di terze parti per Microsoft Lync Server 2010. È possibile aggiungere la chat persistente alla topologia di Lync Server 2013 utilizzando Generatore di topologie. In Lync Server 2013, la funzionalità del server Chat persistente viene implementata utilizzando tre nuovi ruoli del server:

  - **PersistentChatService:** Si tratta del ruolo front-end per la chat persistente. Nelle distribuzioni standard Edition, il ruolo del servizio server Chat persistente è collocato nel server Standard Edition distribuito dal programma di avvio automatico, come qualsiasi altro ruolo di Lync Server. Nelle distribuzioni di Enterprise Edition, il ruolo del servizio chat persistente è distribuito in computer autonomi da parte del programma di avvio automatico, come qualsiasi altro ruolo di Lync Server.

  - **PersistentChatStore:** Server back-end che corrisponde al database del contenuto di chat persistente, in cui è archiviato tutto il contenuto della chat.

  - **PersistentChatComplianceStore:** Ruolo del server back-end corrispondente al database di conformità di Persistent Chat, in cui vengono archiviati tutti gli eventi di conformità.

Questi ruoli del server Chat persistente sono facoltativi e vengono installati solo dai clienti che desiderano una funzionalità completa del server Chat persistente. Il ruolo **PersistentChatComplianceStore** è necessario solo se si sceglie di distribuire la conformità Persistent Chat.

Il ruolo **PersistentChatService** esegue due servizi:

  - Servizio chat persistente

  - Servizio di conformità chat persistente

L'esecuzione di questi servizi su ogni server Chat persistente garantisce una disponibilità elevata per questi servizi in un pool di server Chat persistente multiserver.

Inoltre, per supportare il caricamento e il download dei file nelle chat room persistent, il server Chat persistente include un servizio Web. In precedenza, il servizio è stato collocato nel server Chat persistente, Front End Server e Internet Information Services (IIS) richiesto per l'installazione come prerequisito. In Lync Server 2013 Persistent Chat Server, il servizio Web caricamento/download file è collocato con il front end server Lync Server 2013. Come effetto collaterale, Internet Information Services (IIS) non è più un prerequisito per il server Chat persistente. Il servizio Web caricamento/scaricamento file è identificato come **PersistentChat** in Gestione Internet Information Services (IIS).

<div>


> [!IMPORTANT]  
> Il ruolo <STRONG>PersistentChatService</STRONG> può essere eseguito nello stesso server di un server front-end di Lync Server 2013 solo se il front end server è un server front end &nbsp; Standard Edition &nbsp; . Il ruolo <STRONG>PersistentChatService</STRONG> non può essere eseguito indipendentemente da un &nbsp; server front-end di Lync Server 2013. Può essere installato solo nel contesto di una distribuzione di Lync Server 2013.



</div>

Nel server Chat persistente, il servizio di ricerca è stato eliminato. In Lync Server 2010, Group Chat, il servizio di ricerca è stato eseguito su ogni server front-end di Group Chat Server e ha eseguito il routing su uno dei server di canale. Lync Server 2013 si basa sul routing tramite gli oggetti contatto, in cui ogni pool di server Chat persistente è rappresentato da un oggetto contatto utilizzato dai Front End Server Lync Server per identificare e instradare le richieste a un pool di server Chat persistente appropriato e a uno dei computer in cui è in esecuzione il server Chat persistente nel pool.

In Lync Server 2013, sono disponibili modifiche del servizio conformità:

  - In Lync Server 2010, il servizio di conformità ha eseguito la versione autonoma (non collocata) e solo su un server singolo. Il servizio di conformità è ora in esecuzione su tutti i front end server di Persistent Chat, insieme al servizio chat persistente e fornisce quindi la disponibilità elevata in un pool di server Chat persistente multiserver. Una singola scheda di conformità può essere configurata in modo da estrarre i dati dal database di conformità e in uno degli altri sistemi (file XML, archivi ospitati da Exchange e così via). Il server Chat persistente include un adattatore XML.

  - La coda di Accodamento messaggi (nota anche come MSMQ) condivisa dal servizio chat persistente e il servizio di conformità su ogni server front-end Persistent Chat Server è ora una coda privata condivisa solo dai due servizi. Tutti i servizi di conformità scrivono nello stesso database back-end di conformità. Sono inoltre tutte lette da tale database, allo scopo di inviare i dati all'istanza dell'adapter. Il server back-end Compliance è rappresentato come nuovo ruolo del server back-end.
    
    <div>
    

    > [!IMPORTANT]  
    > Come nelle versioni precedenti, tutti i dati di conformità vengono elaborati solo una volta. I dati possono essere elaborati da una qualsiasi delle istanze degli adattatori richiamate dal servizio di conformità in esecuzione sui vari computer server di chat persistente di Lync Server 2013. Nel server Chat persistente, una qualsiasi delle istanze dell'adapter potrebbe elaborare i dati.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Per informazioni sull'installazione di Accodamento messaggi, vedere <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">installare i sistemi operativi e il software prerequisito nei server per Lync Server 2013</A> nella documentazione relativa alla distribuzione.

    
    </div>

In Lync Server 2013, sono disponibili miglioramenti sia per la disponibilità elevata che per il ripristino di emergenza:

  - Miglioramenti a disponibilità elevata: il mirroring di SQL Server viene utilizzato per garantire la disponibilità elevata per il database del contenuto del server Chat persistente e il database di conformità di Persistent Chat all'interno di un Data Center (nel sito).

  - Miglioramenti al ripristino di emergenza: il server Chat persistente supporta un'architettura del pool estesa che consente di estendere un singolo pool di server Chat persistente tra due siti, ovvero un singolo pool logico nella topologia, con i server del pool che si trovano fisicamente su due siti. Il log shipping di SQL Server viene utilizzato per il ripristino di emergenza tra siti.

Per ulteriori informazioni sulla disponibilità elevata e il ripristino di emergenza, vedere [Configuring Persistent Chat Server for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>Modifiche principali dell'amministrazione e della gestione per il server Chat persistente

Lync Server 2013 ha semplificato l'amministrazione e la gestione del server Chat persistente fornendo:

  - Amministrazione e gestione unificata. Lync Server 2013 facilita la gestione e l'amministrazione del server Chat persistente tramite gli strumenti già noti agli amministratori di Lync. Il server Chat persistente include un'esperienza dell'interfaccia utente amministrativa integrata con il pannello di controllo di Lync Server, che consente di risolvere i problemi relativi alle prestazioni con le versioni precedenti dell'interfaccia utente di Group Chat Server. Inoltre, il server Chat persistente include un insieme di cmdlet di Windows PowerShell per amministrare e gestire le categorie del server Chat persistente, le sale del server Chat persistente (tra cui l'eliminazione di sale e l'eliminazione di contenuto obsoleto) e i componenti aggiuntivi.

  - Modello di amministrazione semplificato. Lync Server 2013 è stato modificato e semplificato il modello del server Chat persistente affrontando i seguenti requisiti principali del cliente:
    
      - Rimuovere le gerarchie nidificate complesse degli ambiti e delle categorie.
    
      - Supporto per definire gli elenchi negati e gli elenchi consentiti (ambiti) per i clienti di MindAlign correnti che stanno pianificando la migrazione al server Chat persistente.

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>Cosa c'è di diverso nei ruoli degli utenti dalle versioni precedenti di Group Chat Server?

Lync Server 2010, Group Chat aveva un ruolo di amministratore utente, un ruolo di amministratore della chat room e un ruolo di amministratore di Lync Server in grado di gestire i componenti aggiuntivi. il server Chat persistente fornisce semplicemente un ruolo amministratore di chat persistente (simile ad altri ruoli di controllo di accesso basato sul ruolo di Lync Server). Chiunque sia membro di questo ruolo RBAC può gestire le chat room, i componenti aggiuntivi e le categorie (e quindi ottenere l'accesso degli utenti per queste categorie) e la configurazione del pool di server Chat persistente.

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>Che cos'è diverse categorie di chat room dalle versioni precedenti di Group Chat Server?

Le categorie delle chat room non possono più essere annidate e la categoria radice non può più essere modificata. AllowedMembers/DeniedMembers è costituito da un ambito utilizzato nelle versioni legacy di Group Chat Server (eccetto per il fatto che non supportava la specifica di un elenco negato). Gli ambiti non possono più essere ignorati, perché non sono presenti categorie nidificate. Un amministratore di chat persistente in Lync Server 2013 è in grado di creare e gestire le categorie delle chat room. Durante la creazione e la gestione delle categorie di chat room, un amministratore di chat persistente può configurare le entità (gruppi/contenitori/utenti di Active Directory) che hanno accesso ai membri/creatori delle chat room di una categoria specifica. Un amministratore di chat persistente può anche aggiungere DeniedMembers a una categoria e queste diventano esclusioni esplicite per l'elenco consentiti. I Membri non consentiti hanno la priorità rispetto al contenuto dei Membri consentiti.

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>Quali sono le differenze tra le proprietà delle chat room delle versioni precedenti di Group Chat Server?

In Lync Server 2013, Persistent Chat Server esiste un nuovo concetto di chat room aperta. Tutti i membri consentiti possono partecipare alla chat room, senza l'appartenenza esclusiva.

Sono state eliminate le seguenti proprietà della chat room incluse nelle versioni precedenti del server Chat persistente:

  - Topic: una sala ora contiene solo una descrizione.

  - Creare un nuovo elenco di membri: nel server Chat persistente tutte le chat room iniziano con l'appartenenza vuota (e possono essere massimizzate a un'appartenenza uguale ai membri consentiti).

  - Caricamento file: utilizzato per essere un'impostazione per chat room per controllare se i file di caricamento/download sono stati consentiti. Questo è ora impostato solo il livello di categoria e si applica a tutte le sale di quella categoria.

  - Cronologia chat: utilizzata come impostazione per la chat room per controllare se la cronologia della chat è stata abilitata, ma è ora impostata solo a livello di categoria e si applica a tutte le sale di quella categoria.

  - Invita: una sala eredita sempre l'impostazione invita per la categoria; oppure può essere disattivata nella sala. Una chat room non può essere attivata se la categoria è stata precedentemente impostata su inviti.

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>Quali sono le differenze relative ai criteri delle versioni precedenti di Group Chat Server?

Il server Chat persistente ha un nuovo criterio di Lync abilitato con chat persistente, per le impostazioni utente/pool/sito/globale. Nel client Lync 2013, l'ambiente di chat persistente è disponibile solo per gli utenti abilitati dal criterio per la chat persistente (direttamente o tramite l'impostazione pool/site/Global).

Le versioni precedenti di Group Chat Server non disponevano di criteri integrati nei criteri di Lync Server. Per ogni utente e per categoria/sala base, utilizzando la funzionalità **può caricare i file** per utente, è possibile rendere l'utente un amministratore utente, un amministratore di chat room o configurare la capacità dell'utente di caricare i file. La caratteristica di **caricamento dei file** del server Chat persistente è solo per categoria.

</div>

<div>

## <a name="logging"></a>Registrazione

La registrazione per il server Chat persistente e System Center Operations Manager è integrata nella registrazione di traccia di Lync Server 2013.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del server Chat persistente in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
