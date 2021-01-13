---
title: Pianificare la topologia del server Chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Riepilogo: leggere questo argomento per informazioni sui componenti e le topologie del server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 548fc5ebecb0f123172ee4733346c03cf44aba7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825506"
---
# <a name="plan-persistent-chat-server-topology"></a>Pianificare la topologia del server Chat persistente
 
**Riepilogo:** Leggere questo argomento per informazioni sui componenti e le topologie di server Chat persistente in Skype for Business Server 2015.
  
Il server Chat persistente supporta configurazioni a server singolo e a più server. È possibile installare il server Chat persistente su un server Skype for Business Server 2015 Enterprise Edition o Standard Edition. 

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 
  
## <a name="persistent-chat-server-components"></a>Componenti del server Chat persistente

Il server Chat persistente è costituito dai componenti seguenti:
  
- Uno o più computer che eseguono il server Chat persistente e offrono i servizi seguenti:
    
  - Servizio chat persistente
    
  - Servizio di conformità, attivato se la conformità è abilitata
    
- Uno o più server (più di uno se viene utilizzato il mirroring) che eseguono il database back-end di SQL Server per ospitare il database del contenuto di chat persistente in cui vengono archiviati il contenuto delle chat room, le sale e le categorie.
    
    > [!NOTE]
    > Nel database back-end sono archiviati i dati della cronologia chat, incluse le informazioni sulle categorie e le chat room persistenti create. 
  
- Se la conformità è abilitata, uno o più server (più di uno se viene utilizzato il mirroring) che eseguono il database back-end di SQL Server per ospitare il database di conformità di Persistent Chat, in cui vengono archiviati gli eventi di conformità e il contenuto della chat ai fini della conformità.
    
Per informazioni dettagliate sui requisiti hardware e software per il server Chat persistente, vedere [requisiti dei server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Topologie del server Chat persistente

È possibile distribuire il server Chat persistente in pool a server singolo o a più server e con topologia a pool singolo o a più pool. Il server Chat persistente supporta le topologie seguenti:
  
-  Server Standard Edition con il server Chat persistente collocato nel front end server
    
-  Server Standard Edition con il server Chat persistente in un server separato
    
-  Server Enterprise Edition con un singolo server Chat persistente in un server separato
    
-  Server Enterprise Edition con più di un server Chat persistente in server distinti
    
Anche se è possibile distribuire il server Chat persistente in un server Standard Edition, tenere presente che le prestazioni e la scala saranno intaccate e la disponibilità elevata non è un'opzione. Pertanto, si consiglia di distribuire la chat persistente in un server Standard Edition principalmente per la prova del concetto e la valutazione degli scopi. 
  
Skype for Business Server 2015 supporta una serie di scenari di collocazione, offrendo la flessibilità necessaria per salvare i costi hardware eseguendo più componenti in un server (se si dispone di una piccola organizzazione) o per eseguire singoli componenti in server diversi (se si dispone di un'organizzazione di dimensioni superiori che richiede scalabilità e prestazioni). Prima di decidere se collocare i componenti, è consigliabile considerare i fattori di scalabilità. Gli scenari di collocazione sono diversi per i server Skype for Business Server 2015 Enterprise Edition e Standard Edition. 
  
Nelle sezioni seguenti vengono descritte le topologie in maggiore dettaglio, inclusi gli scenari di collocazione e le opzioni per i server di database back-end. Per informazioni dettagliate sulla collocazione di tutti i ruoli del server e dei database, vedere [nozioni di base sulla topologia per Skype for Business server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Server Standard Edition con il server Chat persistente collocato nel front end server

Con Standard Edition è possibile collocare la chat persistente sul front end server. Questa è la configurazione più semplice e di base. È necessario assicurarsi che il front end server esistente disponga di una capacità sufficiente in termini di risorse fisiche: CPU, memoria, spazio su disco e così via.
  
Inoltre, è possibile collocare il server back-end del server di chat persistente e il database di conformità di Persistent Chat (se abilitato) nel server back-end SQL Server Express locale. È inoltre possibile scegliere di utilizzare un SQL Server separato con un'istanza dedicata. 
  
> [!IMPORTANT]
> Non è possibile aggiungere altri server a un pool di server Chat persistente se il primo server Chat persistente è collocato con un server Standard Edition front end. Si consiglia di installare il primo server come istanza autonoma in modo da poter aggiungere altri server in un secondo momento, se necessario. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Server Standard Edition con il server Chat persistente installato in un server separato

Con Standard Edition è possibile installare il server Chat persistente come istanza autonoma e aggiungere altri server in un secondo momento, se necessario. 
  
È possibile collocare il server back-end del server di chat persistente e il database di conformità di Persistent Chat (se abilitato) nel server back-end SQL Server Express locale. È inoltre possibile scegliere di utilizzare un SQL Server separato con un'istanza dedicata. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Server Enterprise Edition con un singolo server Chat persistente

Con Enterprise Edition, è necessario installare il server Chat persistente in un computer separato. Non è pertanto possibile collocare il server Chat persistente nel server Enterprise Edition front end. Questa distribuzione richiede un server separato che esegue il server Chat persistente e il servizio di conformità (se abilitato).
  
È tuttavia possibile collocare il database di SQL Server per il server Chat persistente nel database back-end di un pool Enterprise Edition front end.
  
> [!NOTE]
> Se si prevede di utilizzare i gruppi di disponibilità AlwaysOn di SQL per HA DR, tenere presente che non è supportato per i database del server Chat persistente. 
  
Se si colloca il database di chat persistente con il database back-end, è possibile utilizzare una singola istanza di SQL Server per uno o per tutti i database oppure è possibile utilizzare un'istanza separata di SQL Server per ogni database.
  
> [!IMPORTANT]
> Il server che ospita il database di chat persistente può ospitare altri database. Tuttavia, se si considera la collocazione del database di chat persistente con altri database, tenere presente che se si archiviano i messaggi di più utenti, lo spazio su disco necessario per il database di chat persistente può aumentare molto. Per questo motivo, non è consigliabile collocare il database di Persistent Chat con il database back-end. 
  
Nella figura seguente vengono illustrati tutti i componenti di una topologia per un singolo server Chat persistente con conformità abilitata (facoltativo).
  
**Topologia a un server**

![Server Chat persistente-topologia a server singolo](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Server Enterprise Edition con più server Chat persistente

Con Enterprise Edition, è possibile distribuire una topologia a più server per una maggiore capacità e affidabilità. Una topologia a più server è identica alla topologia a server singolo, tranne per il fatto che più server ospitano il server Chat persistente e che possono aumentare la scalabilità verticale. La topologia a più server può includere ben quattro computer attivi che eseguono il server Chat persistente (le configurazioni a disponibilità elevata e ripristino di emergenza consentiranno fino a otto, ma solo quattro possono essere attive e le restanti quattro in standby). Ogni server è in grado di supportare fino a 20.000 utenti simultanei, per un totale di 80.000 utenti simultanei connessi a un pool di server Chat persistente con 4 server. Più computer che eseguono il server Chat persistente devono risiedere nello stesso dominio di servizi di dominio Active Directory come Skype for Business Server e il servizio di conformità.
  
Nella figura seguente vengono illustrati tutti i componenti di una topologia a più server con più computer che eseguono il server Chat persistente, il servizio di conformità facoltativo e un database di conformità distinto.
  
**Topologia a più server**

![Server Chat persistente-topologia a più server](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Le topologie a più server consentono di creare pool delle funzionalità dei server. In un pool di server, i servizi chat persistente comunicano e condividono i dati. Ad esempio, la cronologia delle chat originariamente inviata a un servizio di chat persistente è disponibile da qualsiasi servizio chat persistente nel sistema. È possibile accedere a un file caricato tramite un servizio di chat persistente da qualsiasi servizio chat persistente. Gli utenti possono essere connessi a diversi server front-end di chat persistente e possono comunicare tra loro. La porta predefinita di TCP 8011 connette un server a un pool di server e viene utilizzata dai servizi di chat persistente per comunicare tra loro o a fini amministrativi.
  
Ad esempio, in una distribuzione di quattro server Chat persistente Server, dove 80.000 utenti possono essere contemporaneamente connessi a chat persistente, il carico è distribuito in modo uniforme a 20.000 utenti per server. Se un server non è disponibile, gli utenti che sono connessi a quel server perderanno l'accesso al server Chat persistente. Gli utenti disconnessi vengono automaticamente trasferiti ai server rimanenti fino a quando il server non disponibile non viene ripristinato. 
  

