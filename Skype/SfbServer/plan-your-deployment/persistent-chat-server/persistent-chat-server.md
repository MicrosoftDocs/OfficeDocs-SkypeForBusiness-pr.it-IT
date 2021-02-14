---
title: Pianificare il server Chat persistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Riepilogo: leggere questo argomento per informazioni su come pianificare il server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 9195c149744b9aab9927f0b2a6e490442cff6573
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813666"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Pianificare il server Chat persistente in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come pianificare il server Chat persistente in Skype for Business Server 2015.
  
Il server Chat persistente è un ruolo facoltativo che consente a più utenti dell'organizzazione di partecipare a conversazioni di chat room persistenti nel tempo. Anche se gli utenti possono comunicare in tempo reale durante una sessione di chat, il contenuto di ogni sessione, inclusi testo, collegamenti e file, è persistente, il che significa che gli utenti possono visualizzare e cercare tutto il contenuto della sessione in qualsiasi momento.
  
Il server Chat persistente consente di migliorare le comunicazioni all'interno dell'organizzazione tramite:
  
- Ampliare la consapevolezza e la partecipazione delle informazioni in tutta l'organizzazione
    
- Abilitazione di una condivisione efficiente delle informazioni 
    
- Miglioramento delle comunicazioni tra team, inclusi team geograficamente distribuiti e interfunzionale
    
- Riduzione del sovraccarico di informazioni
    
- Seguire le normative di conformità distribuendo facoltativamente il servizio di conformità di Persistent Chat

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. Le stesse funzionalità sono disponibili in Teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here) Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Architettura di alto livello del server Chat persistente

Nel diagramma seguente viene illustrata una visualizzazione di alto livello dell'architettura del server Chat persistente. 
  
![Architettura di alto livello del server Persistent Chat](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
Persistent Chat è costituito da un ruolo del server front-end che fornisce i servizi di Persistent Chat e un componente di database di SQL back-end. Sia i componenti front-end che back-end sono inclusi in un pool di Persistent Chat dedicato. Ogni computer che ospita il server Chat persistente deve avere accesso a una topologia di Skype for Business Server 2015 esistente. In questo diagramma è presente un pool di server Chat persistente (A), che dipende dal pool A di Skype for Business Server per il routing dei messaggi.
  
È possibile distribuire uno o più pool di server Chat persistente, ognuno con un massimo di quattro server Chat persistente attivi che supportano fino a 80.000 utenti simultanei.
  
Skype for Business Server 2015 comunica con il servizio Persistent Chat utilizzando il protocollo SIP (Session Initiation Protocol) per la registrazione e il protocollo XCCOS (Extensible Chat Communication Over SIP) per la chat. 
  
## <a name="persistent-chat-services"></a>Servizi chat persistente

Nel diagramma seguente vengono illustrati i servizi front-end del server Chat persistente e il modo in cui tali servizi comunicano con i componenti di database back-end. I componenti front-end includono i servizi Persistent Chat e il servizio conformità. I componenti back-end includono l'archivio di Persistent Chat e l'archivio di conformità di Persistent Chat.
  
![Servizi di alto livello del server Persistent Chat](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Servizio chat

Il servizio chat, denominato anche servizio di canale, è il servizio principale responsabile del server Chat persistente. Il servizio Chat offre le funzioni seguenti:
  
- Accetta i messaggi in arrivo
    
- Registra ed elenca i partecipanti online all'interno di una chat room di Persistent Chat
    
- Ritrasmette i messaggi ai sottoscrittori di altri canali
    
- Implementa la logica per la gestione dei canali, gli inviti alle chat room, la ricerca e le notifiche di nuovo contenuto
    
Il servizio Persistent Chat archivia e accede al contenuto delle chat room e ad altri metadati di sistema (regole di autorizzazione e così via) utilizzando l'archivio di Persistent Chat. Il servizio archivia i file caricati nelle chat room nell'archivio file di Persistent Chat.
  
### <a name="compliance-service"></a>Servizio di conformità

Se l'organizzazione dispone di normative che richiedono l'archiviazione dell'attività di Persistent Chat, è possibile distribuire il servizio di conformità di Persistent Chat facoltativo. Il servizio di conformità è responsabile dell'archiviazione del contenuto e degli eventi delle chat, ad esempio l'aggiunta e l'uscita da chat room, all'archivio file di conformità di Persistent Chat. Il servizio di conformità viene installato in ogni server Chat persistente in un pool di Chat persistente. 
  
### <a name="web-services"></a>Servizi Web

I servizi Web di Persistent Chat vengono eseguiti nei Front End Server di Skype for Business. I servizi Web dipendono da Internet Information Services (IIS) e vengono implementati come componenti Web:
  
- I servizi Web di Persistent Chat per il caricamento e il download dei file sono responsabili dell'inserimento e del recupero di file dalle chat room.
    
- I servizi Web di Chat persistente per la gestione delle chat room hanno la responsabilità di offrire agli utenti la possibilità di gestire le proprie chat room e di creare nuove chat room.
    
## <a name="defining-requirements-for-your-organization"></a>Definizione dei requisiti per l'organizzazione

Se si decide di distribuire il server Chat persistente, sarà necessario determinare i requisiti aziendali dell'organizzazione, quindi definire la topologia, l'infrastruttura e i requisiti tecnici per supportare le esigenze aziendali. Per ottimizzare la distribuzione, è necessario rispondere alle domande seguenti:
  
- Si sta eseguendo la migrazione da una versione precedente di Group Chat Server o da una versione precedente del server Chat persistente oppure si sta distribuendo il server Chat persistente per la prima volta?
    
- Chi può utilizzare il server Chat persistente? È possibile specificare criteri di Persistent Chat per determinare l'accesso degli utenti a livello globale, di sito o di utente.
    
- Quanti utenti richiederanno l'accesso al server Chat persistente? Il server Chat persistente supporta 150.000 utenti di cui è stato eseguito il provisioning (abilitati dai criteri) e un massimo di 80.000 utenti simultanei. Un singolo server Chat persistente può supportare 20.000 utenti connessi e un singolo pool di server Chat persistente può avere fino a 4 server attivi per un totale di 80.000 utenti connessi contemporaneamente.
    
- In che modo si vogliono controllare ambiti, limiti etici e accesso? È possibile definire categorie per separare questi limiti e scegliere gli utenti autorizzati a essere presenti nelle chat create in ognuna di queste categorie.
    
- In che modo si vuole controllare chi può creare chat? È possibile definire i creatori che possono creare chat room. I creatori possono assegnare altri membri come responsabili delle chat room per la gestione continua delle chat room.
    
- In che modo si vogliono creare le chat? Il server Chat persistente offre una funzionalità basata sul Web per la creazione e la gestione delle chat room. Questo può essere avviato dal client Skype for Business. È possibile scegliere di definire una soluzione per i clienti che implementa i requisiti aziendali e i flussi di lavoro e configurare il server Chat persistente per indirizzare gli utenti alla soluzione personalizzata.
    
- Di che tipo di componenti aggiuntivi si vuole effettuare il provisioning? I componenti aggiuntivi migliorano l'esperienza in sala sfruttando il riquadro di estendibilità nel client Skype for Business per fornire il contesto rilevante per la sala. È possibile scegliere i componenti aggiuntivi generici che si ritengono più utili, ad esempio il sito Web aziendale, i documenti di collaborazione interni e così via. I responsabili di chat room, se vogliono, possono scegliere uno dei componenti aggiuntivi registrati e associarlo alla propria chat. 
    
- Quali sono i requisiti di disponibilità elevata e di ripristino di emergenza? Il server Chat persistente supporta SQL Server e SQL Server clustering per la disponibilità elevata. Per il ripristino di emergenza, il server Chat persistente supporta fino a 8 server (4 attivi e 4 di standby) in un pool con estensione SQL Server log shipping. 
    
- Ci sono requisiti normativi da rispettare? Se l'azienda si trova in un paese o un'area geografica in cui i dati devono essere conservati all'interno del paese, potrebbe essere necessario distribuire più pool di server Chat persistente, ognuno locale in una specifica area geografica. Una chat room, una categoria o un componente aggiuntivo non si estende su pool, ma appartiene a un solo pool di server Chat persistente. 
    
    > [!NOTE]
    > La presenza di più pool di server Chat persistente non consente una scalabilità maggiore( è comunque possibile avere solo 80.000 utenti simultanei in tutti i pool di server Chat persistente). Il motivo principale per il supporto di più pool di server Chat persistente è quello di supportare problemi normativi. 
  
## <a name="for-more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sull'installazione e la configurazione del server Chat persistente, vedere i seguenti argomenti:
  
- Per informazioni dettagliate su come distribuire il server Chat persistente, vedere [Deploy Persistent Chat Server in Skype for Business Server 2015.](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md) 
    
- Per informazioni dettagliate su come configurare le impostazioni nella distribuzione del server Chat persistente, vedere Gestire il [server Chat persistente in Skype for Business Server 2015.](../../manage/persistent-chat/persistent-chat.md)
    

