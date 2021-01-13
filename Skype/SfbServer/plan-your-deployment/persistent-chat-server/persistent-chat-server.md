---
title: Pianificare il server Chat persistente in Skype for Business Server 2015
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
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Pianificare il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come pianificare il server Chat persistente in Skype for Business Server 2015.
  
Il server Chat persistente è un ruolo facoltativo che consente a più utenti dell'organizzazione di partecipare a conversazioni chat room che persistono nel tempo. Anche se gli utenti possono comunicare in tempo reale durante una sessione di chat, il contenuto di ogni sessione, inclusi testo, collegamenti e file, è persistente, il che significa che gli utenti possono visualizzare e cercare tutto il contenuto della sessione in qualsiasi momento.
  
Il server Chat persistente può contribuire a migliorare la comunicazione all'interno dell'organizzazione:
  
- Ampliare la consapevolezza delle informazioni e la partecipazione nell'intera organizzazione
    
- Abilitazione di una condivisione delle informazioni efficiente 
    
- Migliorare le comunicazioni tra team, inclusi i team geograficamente dispersivi e cross-functional
    
- Riduzione dell'overload delle informazioni
    
- Seguendo le normative di conformità, facoltativamente distribuendo il servizio di conformità di Persistent Chat

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Architettura di alto livello del server Chat persistente

Nel diagramma seguente viene illustrata una visualizzazione di alto livello dell'architettura del server Chat persistente. 
  
![Architettura di alto livello del server Persistent Chat](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
Persistent Chat è costituito da un ruolo del server front-end che fornisce i servizi di chat persistente e un componente di database SQL back-end. Entrambi i componenti front-end e back-end sono inclusi in un pool di chat persistente dedicato. Ogni computer che ospita il server Chat persistente deve avere accesso a una topologia di Skype for Business Server 2015 esistente. In questo diagramma, è presente un pool di server Chat persistente (A), che dipende dal pool di Skype for Business Server a per instradare i messaggi.
  
È possibile distribuire uno o più pool di server Chat persistente, ognuno con un massimo di quattro server di chat persistente attivi che supportano fino a 80K utenti simultanei.
  
Skype for Business Server 2015 comunica con il servizio chat persistente usando il protocollo SIP (Session Initiation Protocol) per la registrazione e il protocollo XCCOS (Extensible chat Communication over SIP Protocol) per la chat. 
  
## <a name="persistent-chat-services"></a>Servizi di chat persistente

Nel diagramma seguente vengono illustrati i servizi front-end del server Chat persistente e il modo in cui questi servizi comunicano con i componenti di database back-end. I componenti front-end includono i servizi di chat persistente e il servizio di conformità. I componenti back-end includono l'archivio di chat persistente e l'archivio di conformità di Persistent Chat.
  
![Servizi di alto livello del server Persistent Chat](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Servizio chat

Il servizio chat, denominato anche servizio canale, è il servizio di base responsabile del server Chat persistente. Il servizio chat fornisce le funzioni seguenti:
  
- Accetta i messaggi in arrivo
    
- Registra ed elenca i partecipanti online in una chat room persistente
    
- Ritrasmette i messaggi ai sottoscrittori di altri canali
    
- Implementa la logica per la gestione dei canali, gli inviti delle chat room, la ricerca e le nuove notifiche del contenuto
    
Il servizio chat persistente archivia e accede al contenuto delle chat room e ad altri metadati di sistema (regole di autorizzazione e così via) utilizzando l'Archivio Chat persistente. Il servizio archivia i file caricati nelle chat room nell'archivio file di Persistent Chat.
  
### <a name="compliance-service"></a>Servizio di conformità

Se nell'organizzazione sono presenti normative che richiedono l'archiviazione di attività di chat persistente, è possibile distribuire il servizio di conformità di Persistent Chat facoltativo. Il servizio di conformità è responsabile dell'archiviazione del contenuto e degli eventi della chat, ad esempio l'aggiunta e la mancata chat, all'archivio file di conformità per la persistenza. Il servizio di conformità è installato in ogni server Chat persistente in un pool di chat persistente. 
  
### <a name="web-services"></a>Servizi Web

I servizi Web di chat persistente vengono eseguiti nei front end server Skype for business. I servizi Web dipendono da Internet Information Services (IIS) e sono implementati come componenti Web:
  
- I servizi Web di chat persistente per il caricamento e il download dei file sono responsabili della registrazione e del recupero dei file dalle chat room.
    
- I servizi Web di chat persistente per la gestione delle chat room sono responsabili di fornire agli utenti la possibilità di gestire le chat room e creare nuove chat room.
    
## <a name="defining-requirements-for-your-organization"></a>Definizione dei requisiti per l'organizzazione

Se si decide di distribuire il server Chat persistente, è necessario determinare i requisiti aziendali dell'organizzazione, quindi definire la topologia, l'infrastruttura e i requisiti tecnici per supportare le esigenze aziendali. Per ottimizzare la distribuzione, è necessario rispondere alle seguenti domande:
  
- Si sta eseguendo la migrazione da una versione precedente di Group Chat Server o da una versione precedente del server Chat persistente oppure si sta distribuendo il server Chat persistente per la prima volta?
    
- Chi può utilizzare il server Chat persistente? È possibile specificare i criteri di Persistent Chat per determinare l'accesso degli utenti a livello globale, del sito o dell'utente.
    
- Quanti utenti avranno bisogno di accedere al server Chat persistente? Il server Chat persistente supporta gli utenti con provisioning 150.000 (abilitati dai criteri) e un massimo di 80.000 utenti simultanei. Un singolo server Chat persistente può supportare gli utenti connessi a 20.000 e un singolo pool di server Chat persistente può avere fino a 4 server attivi per un totale di 80.000 utenti connessi contemporaneamente.
    
- In che modo si vogliono controllare ambiti, limiti etici e accesso? È possibile definire le categorie per separare tali limiti e scegliere gli utenti autorizzati a trovarsi nelle chat create in ognuna di queste categorie.
    
- In che modo si vuole controllare chi può creare chat? È possibile definire creatori che possono creare sale. I creatori possono assegnare altri membri come Manager della chat room per la gestione continua delle sale.
    
- In che modo si vogliono creare le chat? Il server Chat persistente offre una funzionalità basata sul Web per la creazione e la gestione delle sale. Questa operazione può essere avviata dal client Skype for business. È possibile scegliere di definire una soluzione clienti che implementi i flussi di lavoro e i requisiti aziendali e configura il server Chat persistente per indirizzare gli utenti alla soluzione personalizzata.
    
- Di che tipo di componenti aggiuntivi si vuole effettuare il provisioning? I componenti aggiuntivi consentono di migliorare l'esperienza in sala utilizzando il riquadro Extensibility nel client Skype for business per fornire un contesto pertinente per la sala. È possibile scegliere i componenti aggiuntivi generici che si ritengono più utili, ad esempio il sito Web aziendale, i documenti di collaborazione interni e così via. I responsabili di chat room, se vogliono, possono scegliere uno dei componenti aggiuntivi registrati e associarlo alla propria chat. 
    
- Quali sono i requisiti di disponibilità elevata e di ripristino di emergenza? Il server Chat persistente supporta il mirroring di SQL Server e il clustering di SQL Server per la disponibilità elevata. Per il ripristino di emergenza, il server Chat persistente supporta fino a 8 Server (4 attivi e 4 in standby) in un pool esteso con log shipping di SQL Server. 
    
- Ci sono requisiti normativi da rispettare? Se l'azienda si trova in un paese o in un'area geografica in cui i dati devono essere conservati all'interno del paese, potrebbe essere necessario distribuire più pool di server di chat persistente, ognuno locale a una specifica geografia. Una sala, una categoria o un componente aggiuntivo non si estende su pool: appartiene solo a un pool di server Chat persistente. 
    
    > [!NOTE]
    > Se si dispone di più pool di server di chat persistente, non è possibile aumentare la scalabilità (sono ancora disponibili solo 80.000 utenti simultanei in tutti i pool di server Chat persistente). Il motivo principale del supporto di più pool di server di chat persistente è il supporto di problemi normativi. 
  
## <a name="for-more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sull'installazione e sulla configurazione del server Chat persistente, vedere i seguenti argomenti:
  
- Per informazioni dettagliate su come distribuire il server Chat persistente, vedere [deploy Persistent Chat Server in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Per informazioni dettagliate su come configurare le impostazioni per la distribuzione del server Chat persistente, vedere [Manage Persistent Chat Server in Skype for Business server 2015](../../manage/persistent-chat/persistent-chat.md).
    

