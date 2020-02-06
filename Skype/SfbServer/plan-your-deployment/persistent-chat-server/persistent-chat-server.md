---
title: Pianificare il server Chat persistente in Skype per Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Riepilogo: leggere questo argomento per informazioni su come pianificare il server di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: f2adc5bc9ed23f4ca02843e8c6136c44fca92d6d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815734"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Pianificare il server Chat persistente in Skype per Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come pianificare il server di chat persistente in Skype for Business Server 2015.
  
Il server di chat persistente è un ruolo facoltativo che consente a più utenti dell'organizzazione di partecipare alle conversazioni delle chat room che persistono nel tempo. Anche se gli utenti possono comunicare in tempo reale durante una sessione di chat, il contenuto di ogni sessione, inclusi testo, collegamenti e file, è persistente, quindi gli utenti possono visualizzare e cercare tutto il contenuto della sessione in qualsiasi momento.
  
Il server di chat persistente può contribuire a migliorare la comunicazione all'interno dell'organizzazione:
  
- Ampliare la conoscenza e la partecipazione delle informazioni in tutta l'organizzazione
    
- Abilitazione della condivisione efficiente delle informazioni 
    
- Migliorare la comunicazione tra team, inclusi i team geograficamente dispersivi e interfunzionali
    
- Riduzione del sovraccarico di informazioni
    
- Seguire le regole di conformità distribuendo facoltativamente il servizio di conformità della chat persistente

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Architettura di alto livello del server di chat persistente

Il diagramma seguente mostra una visualizzazione di alto livello dell'architettura del server di chat persistente. 
  
![Architettura di alto livello del server di chat persistente](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
La chat persistente è costituita da un ruolo del server front-end che fornisce i servizi di chat persistenti e un componente database SQL di back-end. I componenti front-end e back-end sono inclusi in un pool di chat persistente dedicato. Ogni computer che ospita il server di chat persistente deve avere accesso a una topologia di 2015 di Skype for Business Server esistente. In questo diagramma esiste un pool di server di chat persistente (A), che dipende dal pool di Skype for Business Server a per instradare i messaggi.
  
È possibile distribuire uno o più pool di server di chat permanenti, ognuno con un massimo di quattro server di chat persistenti attivi che supportano fino a 80K utenti simultanei.
  
Skype for Business Server 2015 comunica con il servizio di chat persistente usando il protocollo SIP (Session Initiation Protocol) per la registrazione e l'Extensible chat Communication over SIP Protocol (XCCOS) per la chat. 
  
## <a name="persistent-chat-services"></a>Servizi di chat persistenti

Il diagramma seguente mostra i servizi front-end del server di chat persistente e il modo in cui questi servizi comunicano con i componenti di database back-end. I componenti front-end includono i servizi di chat persistenti e il servizio conformità. I componenti di back-end includono l'Archivio Chat persistente e lo Store di conformità della chat persistente.
  
![Servizi di alto livello del server Chat persistente](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Servizio chat

Il servizio di chat, detto anche servizio canale, è il servizio principale responsabile per il server di chat persistente. Il servizio chat offre le funzioni seguenti:
  
- Accetta i messaggi in arrivo
    
- Registra ed elenca i partecipanti online in una chat room persistente
    
- Ritrasmette i messaggi ad altri abbonati al canale
    
- Implementa la logica per la gestione dei canali, gli inviti alle chat room, la ricerca e le nuove notifiche di contenuto
    
Il servizio di chat persistente archivia e accede al contenuto della chat room e ad altri metadati di sistema (regole di autorizzazione e così via) usando lo Store di chat persistente. Il servizio archivia i file caricati nelle chat room nell'archivio di file della chat persistente.
  
### <a name="compliance-service"></a>Servizio conformità

Se l'organizzazione dispone di regole che richiedono l'archiviazione di attività della chat persistente, è possibile distribuire il servizio di conformità delle chat permanenti facoltative. Il servizio di conformità è responsabile dell'archiviazione di contenuto e eventi della chat, ad esempio l'Unione e l'uscita di sale, all'archivio file di conformità della chat persistente. Il servizio conformità viene installato in ogni server di chat persistente in un pool di chat persistente. 
  
### <a name="web-services"></a>Servizi Web

I servizi Web di chat persistenti vengono eseguiti nei server front-end Skype for business. I servizi Web dipendono da Internet Information Services (IIS) e vengono implementati come componenti Web:
  
- I servizi Web di chat persistenti per caricare e scaricare file sono responsabili della registrazione e del recupero di file dalle chat room.
    
- I servizi Web di chat persistenti per la gestione delle chat room sono responsabili per offrire agli utenti la possibilità di gestire le chat room e creare nuove chat room.
    
## <a name="defining-requirements-for-your-organization"></a>Definizione dei requisiti per l'organizzazione

Se si decide di distribuire il server di chat persistente, è necessario determinare i requisiti aziendali della propria organizzazione, definire la topologia, l'infrastruttura e i requisiti tecnici per supportare le esigenze aziendali. Per ottimizzare la distribuzione, è necessario rispondere alle domande seguenti:
  
- Si esegue la migrazione da una versione precedente di Group Chat Server o da una versione precedente di Persistent Chat Server o si sta distribuendo il server di chat persistente per la prima volta?
    
- Chi può usare il server di chat persistente? Devi specificare i criteri per la chat persistente per determinare l'accesso degli utenti a livello globale, del sito o dell'utente.
    
- Il numero di utenti richiede l'accesso al server di chat persistente? Il server di chat persistente supporta gli utenti con provisioning di 150.000 (abilitati per criterio) e un massimo di 80.000 utenti simultanei. Un singolo server di chat persistente può supportare gli utenti connessi di 20.000 e un singolo pool di server di chat persistente può avere fino a 4 server attivi per un totale di 80.000 utenti connessi contemporaneamente.
    
- Come si vogliono controllare gli ambiti, i confini etici e l'accesso? Puoi definire categorie per separare questi limiti e scegliere chi può essere nelle sale create in ognuna di queste categorie.
    
- Come si vuole controllare chi può creare sale? Puoi definire creatori che possono creare sale. I creatori possono assegnare ad altri membri i responsabili delle chat room per la gestione continua delle sale.
    
- Come si vogliono creare le sale? Persistent Chat Server offre una funzionalità basata sul Web per la creazione e la gestione di sale. Questa operazione può essere avviata dal client Skype for business. È possibile scegliere di definire una soluzione Customer che implementa i flussi di lavoro e i requisiti aziendali e configura il server di chat persistente per indirizzare gli utenti alla soluzione personalizzata.
    
- Quali tipi di componenti aggiuntivi si desidera eseguire il provisioning? I componenti aggiuntivi migliorano l'esperienza in camera sfruttando il riquadro estensibilità nel client Skype for business per offrire un contesto rilevante per la chat room. È possibile scegliere quali componenti aggiuntivi generali potrebbero essere più utili, ad esempio il sito Web aziendale, i documenti di collaborazione interni e così via. I responsabili della chat room possono scegliere uno dei componenti aggiuntivi registrati e associarli alle rispettive sale, se necessario. 
    
- Quali sono i requisiti per l'elevata disponibilità e il ripristino di emergenza? Il server di chat persistente supporta il mirroring di SQL Server e il clustering di SQL Server per una disponibilità elevata. Per il ripristino di emergenza, il server di chat persistente supporta fino a 8 Server (4 attiva e 4 in standby) in un pool allungato con il log shipping di SQL Server. 
    
- Esistono requisiti normativi? Se l'azienda si trova in un paese o in un'area geografica in cui i dati devono essere conservati all'interno del paese, potrebbe essere necessario distribuire più pool di server di chat permanenti, ognuno locale in uno specifico percorso geografico. Una sala, una categoria o un componente aggiuntivo non si estende ai pool, ma appartiene a un solo pool di server di chat persistente. 
    
    > [!NOTE]
    > La presenza di più pool di server di chat persistenti non offre più scala (è comunque possibile avere solo utenti simultanei di 80.000 in tutti i pool di server di chat persistenti). Il motivo principale per il supporto di più pool di server di chat persistenti consiste nel supportare i problemi normativi. 
  
## <a name="for-more-information"></a>Per altre informazioni

Per altre informazioni sull'installazione e la configurazione del server di chat persistente, vedere gli argomenti seguenti:
  
- Per informazioni dettagliate su come distribuire il server di chat persistente, vedere [distribuire il server di chat persistente in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Per informazioni dettagliate su come configurare le impostazioni nella distribuzione del server di chat persistente, vedere [gestire il server di chat persistente in Skype for Business server 2015](../../manage/persistent-chat/persistent-chat.md).
    

