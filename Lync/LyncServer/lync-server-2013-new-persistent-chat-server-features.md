---
title: 'Lync Server 2013: Nuove funzionalità del server Chat persistente'
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
ms.openlocfilehash: fe207d2469a36d880e9ed519ff1d47d942ed79aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Nuove funzionalità del server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

Lync Server 2013, il server di chat persistente consente di partecipare a conversazioni basate su argomenti multiparte, che persistono nel tempo. Il server di chat persistente può aiutare l'organizzazione a eseguire le operazioni seguenti:

  - Migliorare la comunicazione tra team geograficamente dispersivi e interfunzionali

  - Ampliare la conoscenza e la partecipazione delle informazioni

  - Migliorare la comunicazione con l'organizzazione estesa

  - Ridurre il sovraccarico di informazioni

  - Migliorare la consapevolezza delle informazioni

  - Aumentare la dispersione di conoscenze e informazioni importanti

Lync Server 2013, il server di chat persistente non è disponibile in Microsoft Office 365. In questo momento, è disponibile solo per i clienti di Lync 2013 locali.

In Lync 2013 la funzionalità chat persistente è integrata nel client Lync 2013. Di conseguenza, gli utenti hanno accesso a messaggistica istantanea/presenza, audio/video, conferenze e chat persistente in tutti i client di Lync 2013. Per altre informazioni sul client Lync 2013, vedere <http://go.microsoft.com/fwlink/p/?linkid=270877>.

Questo argomento descrive le modifiche alle caratteristiche tra la nuova versione di Lync Server 2013, il server di chat persistente e la versione precedente (Microsoft Lync Server 2010, Group Chat), tra cui:

  - Fornisci un'esperienza amministrativa nel pannello di controllo di Lync Server ed Elimina lo strumento di amministrazione di chat di gruppo

  - Integrare le impostazioni di configurazione per il server di chat persistente in Generatore di topologia eliminando lo strumento di configurazione chat di gruppo

  - Semplificare la migrazione e l'aggiornamento dalle versioni precedenti del server di chat persistente

  - Fornisci soluzioni a elevata disponibilità e ripristino di emergenza

Per ulteriori informazioni sull'ultima versione del server di chat persistente, vedere quanto segue:

  - La guida per la chat <http://go.microsoft.com/fwlink/p/?linkid=270945> persistente in cui viene fornito un elenco dettagliato delle caratteristiche della chat persistente, come funzionano e come usarle durante l'esecuzione del server di chat persistente.

  - [Pianificazione per il server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione di pianificazione la distribuzione di un [server di chat persistente in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) nella documentazione di distribuzione, la [migrazione da Lync Server 2010, Group chat o Office Communications Server 2007 R2 group chat in Lync Server 2013, il server di chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) nella documentazione di migrazione e la [gestione di Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) nella documentazione Operations, che contengono tutte le istruzioni per la configurazione Server di chat persistente.

  - Il file MSI (Persistent Chat Server Documentation) (file di Windows Installer) consente agli utenti di accedere a una documentazione offline completa sul server di chat persistente.

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>Modifiche della topologia chiave per il server di chat persistente

Le seguenti modifiche di alto livello per il server di chat persistente includono:

Il server di chat persistente è ora un ruolo del server. In Microsoft Lync Server 2010, Group Chat Server è un'applicazione attendibile di terze parti per Microsoft Lync Server 2010. La chat persistente può essere aggiunta alla topologia di Lync Server 2013 tramite Generatore di topologie. In Lync Server 2013 la funzionalità del server di chat persistente viene implementata con tre nuovi ruoli del server:

  - **PersistentChatService:** Questo è il ruolo di front-end per la chat persistente. Nelle distribuzioni standard Edition, il ruolo del servizio server di chat persistente è collocato nel server Standard Edition distribuito da Bootstrapper, come qualsiasi altro ruolo di Lync Server. Nelle distribuzioni di Enterprise Edition, il ruolo del servizio chat persistente viene distribuito in computer autonomi tramite il programma di avvio automatico, come qualsiasi altro ruolo di Lync Server.

  - **PersistentChatStore:** Server back-end che corrisponde al database del contenuto della chat persistente, in cui è archiviato tutto il contenuto della chat.

  - **PersistentChatComplianceStore:** Ruolo del server back-end che corrisponde al database di conformità della chat persistente, in cui sono archiviati tutti gli eventi di conformità.

Questi ruoli del server di chat persistenti sono facoltativi e vengono installati solo dai clienti che desiderano una funzionalità completa del server di chat persistente. Il ruolo **PersistentChatComplianceStore** è necessario solo se si sceglie di distribuire la conformità della chat persistente.

Il ruolo **PersistentChatService** esegue due servizi:

  - Servizio chat persistente

  - Servizio di conformità della chat persistente

L'esecuzione di questi servizi su ogni server di chat persistente offre una disponibilità elevata per questi servizi in un pool di server di chat persistente multiserver.

Inoltre, per supportare il caricamento e il download di file nelle chat room persistenti, il server di chat persistente include un servizio Web. In precedenza, questo servizio era collocato nel server di chat persistente, Front End Server e Internet Information Services (IIS) richiesto per l'installazione come prerequisito. Nel server di chat persistente di Lync Server 2013, il servizio Web upload/download di file è collocato nel server front end di Lync Server 2013. Come effetto collaterale, Internet Information Services (IIS) non è più un prerequisito per il server di chat persistente. Il servizio Web upload/download del file è identificato come **PersistentChat** in Gestione Internet Information Services (IIS).

<div>


> [!IMPORTANT]  
> Il ruolo <STRONG>PersistentChatService</STRONG> può essere eseguito nello stesso server di un server front-&nbsp;end di Lync Server 2013 solo se il server front-end è&nbsp;un server front-end Standard Edition. Il ruolo <STRONG>PersistentChatService</STRONG> non può essere eseguito indipendentemente da un server&nbsp;Front-End di Lync Server 2013. Può essere installato solo nel contesto di una distribuzione di Lync Server 2013.



</div>

Nel server di chat persistente il servizio di ricerca è stato eliminato. In Lync Server 2010, Group Chat, il servizio di ricerca è stato eseguito su ogni server front-end di Group Chat Server e ha eseguito il routing su uno dei server del canale. Lync Server 2013 si basa sul routing usando gli oggetti contatto, in cui ogni pool di server di chat persistente è rappresentato da un oggetto contatto usato dai server front-end di Lync Server per identificare e instradare le richieste a un pool di server di chat persistente appropriato e a uno dei computer che eseguono il server di chat persistente nel pool.

In Lync Server 2013 sono presenti modifiche al servizio di conformità:

  - In Lync Server 2010 il servizio conformità è stato eseguito autonomamente (non collocato) e solo su un singolo server. Il servizio conformità viene ora eseguito su tutti i server front-end di Persistent Chat, accanto al servizio di chat persistente e offre quindi una disponibilità elevata in un pool di server di chat persistente multiserver. Un singolo adattatore di conformità può essere configurato per estrarre i dati dal database di conformità e in uno degli altri sistemi (file XML, archivi ospitati da Exchange e così via). Il server di chat persistente include un adattatore XML.

  - La coda di Accodamento messaggi (nota anche come MSMQ) condivisa dal servizio di chat persistente e il servizio di conformità su ogni server front end del server di chat persistente è ora una coda privata condivisa solo dai due servizi. Tutti i servizi di conformità scrivono nello stesso database back-end di conformità. Vengono inoltre letti tutti da tale database, allo scopo di inviare i dati all'istanza dell'adapter. Il server back-end di conformità è rappresentato come nuovo ruolo del server back-end.
    
    <div>
    

    > [!IMPORTANT]  
    > Come nelle versioni precedenti, tutti i dati di conformità vengono elaborati una sola volta. I dati possono essere elaborati da qualsiasi istanza di adapter richiamata dal servizio di conformità in esecuzione nei vari computer server di chat di Lync Server 2013. Nel server di chat persistente una delle istanze di adapter potrebbe elaborare i dati.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Per informazioni sull'installazione di Accodamento messaggi, vedere <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">installare sistemi operativi e software prerequisito nei server per Lync Server 2013</A> nella documentazione relativa alla distribuzione.

    
    </div>

In Lync Server 2013 sono disponibili miglioramenti sia per la disponibilità elevata che per il ripristino di emergenza:

  - Miglioramenti a elevata disponibilità: il mirroring di SQL Server viene usato per ottenere una disponibilità elevata per il database del contenuto del server di chat persistente e il database di conformità della chat persistente in un centro dati (nel sito).

  - Miglioramenti al ripristino di emergenza: il server di chat persistente supporta un'architettura di pool allungata che consente di estendere un singolo pool di server di chat persistente in due siti, ovvero un singolo pool logico nella topologia, con i server del pool fisicamente si trova in due siti). SQL Server log shipping viene usato per il ripristino di emergenza intersito.

Per altre informazioni sull'elevata disponibilità e il ripristino di emergenza, vedere [configurazione del server di chat persistente per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>Principali modifiche di amministrazione e gestione per il server di chat persistente

Lync Server 2013 ha semplificato l'amministrazione e la gestione del server di chat persistente fornendo:

  - Amministrazione e gestione unificata. Lync Server 2013 semplifica la gestione e l'amministrazione del server di chat persistente usando gli strumenti già noti agli amministratori di Lync. Il server di chat persistente include un'esperienza di interfaccia utente amministrativa integrata con il pannello di controllo di Lync Server, che risolve i problemi di prestazioni con le versioni precedenti dell'interfaccia utente di Group Chat Server. Inoltre, il server di chat persistente include una raccolta di cmdlet di Windows PowerShell per amministrare e gestire le categorie di server di chat persistenti, le sale del server di chat permanenti (tra cui l'eliminazione di sale ed eliminazione di contenuto obsoleto) e i componenti aggiuntivi

  - Modello di amministrazione semplificato. Lync Server 2013 ha modificato e semplificato il modello di server di chat persistente affrontando i seguenti requisiti principali per i clienti:
    
      - Rimuovere le gerarchie annidate complesse degli ambiti e delle categorie.
    
      - Supporto per la definizione di elenchi di negazione e di elenchi consentiti (ambiti) per gli attuali clienti di MindAlign che hanno intenzione di eseguire la migrazione a Persistent Chat Server.

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>Quali sono le differenze tra i ruoli utente delle versioni precedenti di Group Chat Server?

Lync Server 2010, Group Chat ha un ruolo di amministratore utente, un ruolo di amministratore della chat room e un ruolo di amministratore di Lync Server che può gestire i componenti aggiuntivi. il server di chat persistente fornisce semplicemente un ruolo di amministratore della chat persistente (simile ad altri Lync Ruoli di controllo di accesso basati sul ruolo del server (RBAC)). Chiunque sia membro di questo ruolo RBAC può gestire le chat room, i componenti aggiuntivi e le categorie (e quindi ottenere l'accesso degli utenti per queste categorie) e la configurazione del pool del server di chat persistente.

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>Quali sono le differenze tra le categorie delle chat room delle versioni precedenti di Group Chat Server?

Le categorie delle chat room non possono più essere annidate e la categoria radice non può più essere modificata. AllowedMembers/DeniedMembers comprende l'ambito usato nelle versioni legacy di Group Chat Server (ad eccezione del fatto che non ha supportato la specifica di un elenco negato). Non è più possibile eseguire l'override degli ambiti, perché non sono presenti categorie annidate. Un amministratore della chat persistente in Lync Server 2013 può creare e gestire le categorie delle chat room. Nell'ambito della creazione e della gestione delle categorie di chat room, un amministratore della chat persistente può configurare le entità (gruppi/contenitori/utenti di Active Directory) che hanno accesso a membri/creatori di chat room di una specifica categoria. Un amministratore della chat persistente può anche aggiungere DeniedMembers a una categoria e questi diventano esclusioni esplicite per l'elenco consentiti. I Membri non consentiti hanno la priorità rispetto al contenuto dei Membri consentiti.

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>Quali sono le differenze tra le proprietà delle chat room delle versioni precedenti di Group Chat Server?

Un nuovo concetto di chat room aperte esiste in Lync Server 2013, Persistent Chat Server. Tutti i membri consentiti possono partecipare alla chat room, senza membri esclusivi.

Le proprietà della chat room seguenti incluse nelle versioni precedenti del server di chat persistente sono state eliminate:

  - Argomento: ora una sala contiene solo una descrizione.

  - Creare un nuovo elenco di membri: nel server di chat persistente tutte le chat room iniziano con l'appartenenza vuota (e possono massimizzare l'appartenenza ai membri consentiti).

  - Upload di file: usato per essere un'impostazione per la chat room per controllare se il caricamento/download di file è stato consentito. Questo è ora impostato solo il livello di categoria e si applica a tutte le camere della categoria.

  - Cronologia chat: usato per essere un'impostazione per la chat room per controllare se la cronologia chat è stata abilitata, ma ora è impostata solo a livello di categoria e si applica a tutte le camere della categoria.

  - Invita: una sala eredita sempre l'impostazione invita per la categoria; oppure può essere disattivato nella sala. Una sala non può attivare gli inviti se la categoria è stata precedentemente impostata su invita off.

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>Quali sono le differenze tra i criteri delle versioni precedenti di Group Chat Server?

Il server di chat persistente ha un nuovo criterio di Lync abilitato con la chat persistente, per utente/pool/sito/impostazioni globali. Nel client Lync 2013 l'ambiente di chat persistente è disponibile solo per gli utenti abilitati per criteri per la chat persistente, direttamente o tramite il pool/sito/impostazione globale.

Le versioni precedenti di Group Chat Server non avevano criteri integrati nei criteri di Lync Server. Per ogni utente e per categoria/camera base, usando la caratteristica **può caricare file** per utente, è possibile rendere l'utente un amministratore dell'utente, un amministratore di chat room o configurare la capacità dell'utente di caricare i file. La caratteristica di **caricamento dei file** del server di chat persistente è solo per categoria.

</div>

<div>

## <a name="logging"></a>Registrazione

La registrazione per il server di chat persistente e System Center Operations Manager è integrata nella registrazione delle tracce di Lync Server 2013.

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

