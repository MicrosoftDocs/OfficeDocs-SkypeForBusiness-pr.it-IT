---
title: Pianificazione della topologia del server Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Riepilogo: leggere questo argomento per informazioni sui componenti e le topologie dei server di chat persistenti in Skype for Business Server 2015.'
ms.openlocfilehash: c31cb8b0ada280b52d902e975f1bacf947fd19e7
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36195961"
---
# <a name="plan-persistent-chat-server-topology"></a>Pianificazione della topologia del server Chat persistente
 
**Riepilogo:** Leggere questo argomento per informazioni sui componenti e le topologie dei server di chat persistenti in Skype for Business Server 2015.
  
Il server di chat persistente supporta sia configurazioni a server singolo che a server multiplo. È possibile installare il server di chat persistente in un server Skype for Business Server 2015 Enterprise Edition o Standard Edition. 

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 
  
## <a name="persistent-chat-server-components"></a>Componenti del server di chat persistente

Il server di chat persistente è costituito dai componenti seguenti:
  
- Uno o più computer che eseguono il server di chat persistente e forniscono i servizi seguenti:
    
  - Servizio chat persistente
    
  - Servizio conformità, attivato se è abilitata la conformità
    
- Uno o più server (più di uno se viene usato il mirroring) in cui viene eseguito il database back-end di SQL Server per l'hosting del database del contenuto della chat persistente in cui sono archiviati il contenuto della chat room, le camere e le categorie.
    
    > [!NOTE]
    > Il database back-end archivia i dati della cronologia delle chat, incluse le informazioni sulle categorie e le chat room persistenti create. 
  
- Se è abilitata la conformità, uno o più server (più di uno se viene usato il mirroring) esegue il database back-end di SQL Server per l'hosting del database di conformità della chat persistente, in cui vengono archiviati gli eventi di conformità e il contenuto della chat per lo scopo della conformità.
    
Per informazioni dettagliate sui requisiti hardware e software per il server di chat persistente, vedere [requisiti del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [requisiti hardware e software per il server di chat persistente in Skype for Business Server 2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Topologie del server di chat persistente

È possibile distribuire il server di chat persistente in pool a server singolo o a più server e con una topologia a pool singolo o multiplo. Il server di chat persistente supporta le topologie seguenti:
  
-  Server Standard Edition con il server di chat persistente collocato nel server front-end
    
-  Server Standard Edition con il server di chat persistente in un server separato
    
-  Server Enterprise Edition con un singolo server di chat persistente in un server separato
    
-  Server Enterprise Edition con più di un server di chat persistente in server distinti
    
Anche se è possibile distribuire il server di chat persistente in un server Standard Edition, tenere presente che le prestazioni e la scala saranno interessate e che la disponibilità elevata non è un'opzione. Si consiglia pertanto di distribuire la chat persistente in un server Standard Edition principalmente per la prova degli scopi concettuali e di valutazione. 
  
Skype for Business Server 2015 supporta diversi scenari di collocazione, offrendo la flessibilità necessaria per salvare i costi hardware eseguendo più componenti in un server (se si ha una piccola organizzazione) o per eseguire singoli componenti in server diversi ( Se si dispone di un'organizzazione più grande che richiede scalabilità e prestazioni). È consigliabile considerare i fattori di scalabilità prima di decidere se collocare i componenti. Gli scenari di collocazione sono diversi per i server Skype for Business Server 2015 Enterprise Edition e Standard Edition. 
  
Le sezioni seguenti descrivono le topologie in modo più dettagliato, inclusi scenari di collocazione e opzioni per i server di database back-end. Per informazioni dettagliate sulla collocazione di tutti i ruoli e i database del server, vedere Nozioni di base sulla topologia di [Skype for Business server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Server Standard Edition con il server di chat persistente collocato nel server front-end

Con Standard Edition è possibile collocare la chat persistente nel server front-end. Questa è la configurazione più semplice e basilare. È necessario assicurarsi che il server front-end esistente disponga di una capacità sufficiente in termini di risorse fisiche: CPU, memoria, spazio su disco e così via.
  
È inoltre possibile collocare il server back-end del server di chat persistente e il database di conformità della chat persistente (se abilitato) nel server back-end di SQL Server Express locale. Puoi anche scegliere di usare un server SQL separato con un'istanza dedicata. 
  
> [!IMPORTANT]
> Non è possibile aggiungere altri server a un pool di server di chat persistente se il primo server di chat persistente è collocato con un server front-end Standard Edition. È consigliabile installare il primo server come istanza autonoma in modo da poter aggiungere più server in un secondo momento, se necessario. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Server Standard Edition con il server di chat persistente installato in un server separato

Con Standard Edition è possibile installare il server di chat persistente come istanza autonoma e aggiungere altri server in un secondo momento, se necessario. 
  
È possibile collocare il server back-end del server di chat persistente e il database di conformità della chat persistente (se abilitato) nel server back-end di SQL Server Express locale. Puoi anche scegliere di usare un server SQL separato con un'istanza dedicata. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Server Enterprise Edition con un singolo server di chat persistente

Con Enterprise Edition è necessario installare il server di chat persistente in un computer separato. Non è quindi possibile collocare il server di chat persistente nel server front-end Enterprise Edition. Questa distribuzione richiede un server separato che esegue il server di chat persistente e il servizio di conformità (se abilitato).
  
È tuttavia possibile collocare il database di SQL Server per il server di chat persistente nel database back-end di un pool di front-end Enterprise Edition.
  
> [!NOTE]
> Se si prevede di usare gruppi di disponibilità SQL AlwaysOn per HA DR, tenere presente che non è supportato per i database del server di chat persistente. 
  
Se si colloca il database di chat persistente con il database back-end, è possibile usare una singola istanza di SQL Server per uno o tutti i database oppure è possibile usare un'istanza distinta di SQL Server per ogni database.
  
> [!IMPORTANT]
> Il server che ospita il database di chat persistente può ospitare altri database. Tuttavia, se si considera la possibilità di collocare il database di chat persistente con altri database, tenere presente che, se si archiviano i messaggi di più utenti, lo spazio su disco necessario per il database della chat persistente può diventare molto elevato. Per questo motivo, non è consigliabile collocare il database di chat persistente con il database back-end. 
  
La figura seguente mostra tutti i componenti di una topologia per un singolo server di chat persistente con conformità abilitata (facoltativo).
  
**Topologia a server singolo**

![Server di chat persistente-topologia a server singolo](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Server Enterprise con più server di chat persistenti

Con Enterprise Edition è possibile distribuire una topologia a più server per una maggiore capacità e affidabilità. Una topologia a più server è uguale alla topologia a server singolo, ad eccezione del fatto che più server ospitano il server di chat persistente e possono essere ridimensionati in modo più elevato. La topologia a più server può includere fino a quattro computer attivi che eseguono il server di chat persistente (le configurazioni ad alta disponibilità e ripristino di emergenza consentiranno fino a otto, ma solo quattro possono essere attive e le rimanenti quattro in standby). Ogni server può supportare tutti gli utenti simultanei di 20.000, per un totale di 80.000 utenti simultanei connessi a un pool di server di chat persistente con 4 server. Più computer che eseguono il server di chat persistente devono risiedere nello stesso dominio di servizi di dominio Active Directory di Skype for Business Server e nel servizio conformità.
  
La figura seguente mostra tutti i componenti di una topologia a più server con più computer che eseguono il server di chat persistente, il servizio di conformità facoltativo e un database di conformità separato.
  
**Topologia a più server**

![Server di chat persistente-topologia a più server](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Le topologie con più server consentono di creare pool di funzionalità del server. In un pool di server i servizi di chat persistenti comunicano e condividono i dati. Ad esempio, la cronologia delle chat pubblicata in origine in un servizio di chat persistente è disponibile presso qualsiasi servizio di chat persistente nel sistema. Un file caricato tramite un servizio di chat persistente può essere accessibile da qualsiasi servizio di chat persistente. Gli utenti possono essere connessi a diversi server front end del server di chat persistente e possono essere comunicanti tra loro. La porta predefinita di TCP 8011 connette un server a un pool di server e viene usata dai servizi di chat persistenti per comunicare tra loro o per scopi amministrativi.
  
Ad esempio, in una distribuzione di server di chat persistente con quattro server, in cui gli utenti di 80.000 possono essere connessi simultaneamente a una chat persistente, il carico viene distribuito uniformemente in 20.000 utenti per server. Se un server non è disponibile, gli utenti connessi al server perderanno l'accesso al server di chat persistente. Gli utenti disconnessi verranno trasferiti automaticamente ai server rimanenti finché non viene ripristinato il server non disponibile. 
  

