---
title: Pianificare la topologia del server Chat persistente
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Riepilogo: leggere questo argomento per informazioni sui componenti e le topologie del server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 1b57d9d9ace6e51001acfa39101eb185a8e00939
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862073"
---
# <a name="plan-persistent-chat-server-topology"></a>Pianificare la topologia del server Chat persistente
 
**Riepilogo:** Leggere questo argomento per informazioni sui componenti e le topologie del server Chat persistente in Skype for Business Server 2015.
  
Il server Chat persistente supporta configurazioni sia a server singolo che a server multiplo. È possibile installare il server Chat persistente in un Skype for Business Server 2015 edizione Enterprise o edizione Standard Server. 

> [!NOTE] 
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015. 
  
## <a name="persistent-chat-server-components"></a>Componenti del server Chat persistente

Il server Chat persistente è costituito dai componenti seguenti:
  
- Uno o più computer che eseguono il server Chat persistente e forniscono i servizi seguenti:
    
  - Servizio Persistent Chat
    
  - Servizio di conformità, attivato se la conformità è abilitata
    
- Uno o più server (più di uno se viene utilizzato il mirroring) che eseguono il database back-end di SQL Server per ospitare il database del contenuto di Persistent Chat in cui sono archiviati il contenuto, le chat room e le categorie.
    
    > [!NOTE]
    > Nel database back-end vengono archiviati i dati della cronologia delle chat, incluse le informazioni sulle categorie e sulle chat chat persistenti create. 
  
- Se la conformità è abilitata, uno o più server (più di uno se viene utilizzato il mirroring) che eseguono il database back-end di SQL Server per ospitare il database di conformità di Persistent Chat, in cui vengono archiviati gli eventi di conformità e il contenuto della chat ai fini della conformità.
    
Per informazioni dettagliate sui requisiti hardware e software per il server Chat persistente, vedere [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e Hardware and software requirements for Persistent Chat Server in Skype for Business Server [2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Topologie del server Chat persistente

È possibile distribuire il server Chat persistente in pool a server singolo o a più server e con topologia a pool singolo o a più pool. Il server Chat persistente supporta le topologie seguenti:
  
-  edizione Standard Server con server Chat persistente collocato nel Front End Server
    
-  edizione Standard Server con server Chat persistente in un server separato
    
-  edizione Enterprise Server con un singolo server Chat persistente in un server separato
    
-  edizione Enterprise Server con più di un server Chat persistente in server separati
    
Anche se è possibile distribuire il server Chat persistente in un edizione Standard Server, tenere presente che le prestazioni e la scalabilità saranno influenzate e la disponibilità elevata non è un'opzione. È pertanto consigliabile distribuire Persistent Chat in un edizione Standard Server principalmente a scopo di prova e valutazione. 
  
Skype for Business Server 2015 supporta una vasta gamma di scenari di collocazione, offrendo la flessibilità necessaria per risparmiare sui costi hardware eseguendo più componenti in un server (se si dispone di un'organizzazione di piccole dimensioni) o per eseguire singoli componenti in server diversi (se si dispone di un'organizzazione più grande che necessita di scalabilità e prestazioni). È consigliabile considerare i fattori di scalabilità prima di decidere se collocare i componenti. Gli scenari di collocazione differiscono Skype for Business Server server edizione Enterprise 2015 edizione Standard server. 
  
Nelle sezioni seguenti vengono descritte in modo più dettagliato le topologie, inclusi gli scenari di collocazione e le opzioni per i server di database back-end. Per informazioni dettagliate sulla collocazione di tutti i ruoli e i database del server, vedere [Topology Basics for Skype for Business Server 2015.](../../plan-your-deployment/topology-basics/topology-basics.md)
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>edizione Standard Server con server Chat persistente collocato nel Front End Server

Con edizione Standard, è possibile collocare Persistent Chat nel Front End Server. Questa è la configurazione più semplice e di base. È necessario verificare che il Front End Server esistente abbia una capacità sufficiente in termini di risorse fisiche: CPU, memoria, spazio su disco e così via.
  
È inoltre possibile collocare il server back-end del server Chat persistente e il database di conformità di Persistent Chat (se abilitato) nel server back-end SQL Server Express locale. Puoi anche scegliere di usare un'SQL Server separata con un'istanza dedicata. 
  
> [!IMPORTANT]
> Non è possibile aggiungere ulteriori server a un pool di server Chat persistente se il primo server Chat persistente è collocato con edizione Standard Front End Server. È consigliabile installare il primo server come istanza autonoma in modo da poter aggiungere altri server in un secondo momento, se necessario. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>edizione Standard Server con server Chat persistente installato in un server separato

Con edizione Standard, è possibile installare il server Chat persistente come istanza autonoma e aggiungere altri server in un secondo momento, se necessario. 
  
È possibile collocare il server back-end del server Chat persistente e il database di conformità di Persistent Chat (se abilitato) nel server back-end locale SQL Server Express server back-end. Puoi anche scegliere di usare un'SQL Server separata con un'istanza dedicata. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>edizione Enterprise Server con un singolo server Chat persistente

Con edizione Enterprise, è necessario installare il server Chat persistente in un computer separato. Ciò significa che non è possibile collocare il server Chat persistente edizione Enterprise Front End Server. Questa distribuzione richiede un server separato che esegue il server Chat persistente e il servizio di conformità (se abilitato).
  
È tuttavia possibile collocare il database SQL Server per il server Chat persistente nel database back-end di un pool front-end edizione Enterprise server.
  
> [!NOTE]
> Se si prevede di utilizzare SQL disponibilità AlwaysOn per il ripristino di emergenza, tenere presente che non è supportato per i database del server Chat persistente. 
  
Se si colloca il database di Persistent Chat con il database back-end, è possibile utilizzare una singola istanza di SQL Server per uno o per tutti i database oppure è possibile utilizzare un'istanza separata di SQL Server per ogni database.
  
> [!IMPORTANT]
> Il server che ospita il database di Persistent Chat può ospitare altri database. Tuttavia, quando si considera di collocare il database di Persistent Chat con altri database, tenere presente che se si archiviano i messaggi di più di pochi utenti, lo spazio su disco necessario per il database di Persistent Chat può aumentare molto. Per questo motivo, non è consigliabile collocare il database di Persistent Chat con il database back-end. 
  
Nella figura seguente vengono illustrati tutti i componenti di una topologia per un singolo server Chat persistente con conformità abilitata (facoltativo).
  
**Topologia a un server**

![Server Chat persistente - Topologia a server singolo.](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>edizione Enterprise Server con più server Chat persistente

Con edizione Enterprise, è possibile distribuire una topologia a più server per una maggiore capacità e affidabilità. Una topologia a più server è la stessa della topologia a server singolo, ad eccezione del fatto che più server ospitano il server Chat persistente e possono essere scalati più in alto. La topologia a più server può includere fino a quattro computer attivi che eseguono il server Chat persistente (le configurazioni di disponibilità elevata e ripristino di emergenza ne consentono fino a otto, ma solo quattro possono essere attive e le restanti quattro in standby). Ogni server può supportare fino a 20.000 utenti simultanei, per un totale di 80.000 utenti simultanei connessi a un pool di server Chat persistente con 4 server. Più computer che eseguono il server Chat persistente devono risiedere nello stesso dominio di Servizi di dominio Active Directory Skype for Business Server e del servizio di conformità.
  
Nella figura seguente vengono mostrati tutti i componenti di una topologia a più server con più computer che eseguono il server Chat persistente, il servizio di conformità facoltativo e un database di conformità separato.
  
**Topologia a più server**

![Server Chat persistente - Topologia a più server.](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Le topologie a più server consentono di creare pool delle funzionalità dei server. In un pool di server, i servizi Chat persistente comunicano e condividono i dati. Ad esempio, la cronologia chat originariamente pubblicata in un servizio Persistent Chat è disponibile da qualsiasi servizio Chat persistente nel sistema. È possibile accedere a un file caricato tramite un servizio Chat persistente da qualsiasi servizio Persistent Chat. Gli utenti possono essere connessi a diversi Front End Server del server Chat persistente e comunicare tra loro. La porta predefinita di TCP 8011 connette un server a un pool di server e viene utilizzata dai servizi Persistent Chat per comunicare tra loro o per scopi amministrativi.
  
Ad esempio, in una distribuzione del server Chat persistente a quattro server, in cui 80.000 utenti possono accedere contemporaneamente a Persistent Chat, il carico viene distribuito uniformemente a 20.000 utenti per server. Se un server non è più disponibile, gli utenti connessi a tale server perderanno l'accesso al server Chat persistente. Gli utenti disconnessi vengono automaticamente trasferiti ai server rimanenti fino a quando il server non disponibile non viene ripristinato. 
  

