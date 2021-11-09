---
title: Disponibilità elevata del server back-end in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Informazioni sulle opzioni di disponibilità elevata del server back-end supportate in Skype for Business Server, inclusi i gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn, il mirroring del database e SQL clustering di failover.
ms.openlocfilehash: 9e7b06fc1894c67d6d4cee1e2ec04bf910181df5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847179"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Disponibilità elevata del server back-end in Skype for Business Server
 
Informazioni sulle opzioni di disponibilità elevata del server back-end supportate in Skype for Business Server, inclusi i gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn, il mirroring del database e SQL clustering di failover.
  
Per migliorare la disponibilità elevata per i server back-end, sono disponibili quattro opzioni:
  
- Mirroring del database
    
- Gruppi di disponibilità AlwaysOn
    
- Istanze del cluster di failover AlwaysOn
    
- SQL clustering di failover
    
L'utilizzo di una di queste soluzioni è facoltativo, ma è consigliabile mantenere la continuità aziendale dell'organizzazione. In caso contrario, la perdita di un singolo server di database potrebbe causare la perdita di dati Skype for Business Server significativi. 
  
È possibile configurare il mirroring del database utilizzando solo Generatore di topologie. Per i gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn o il clustering di failover di SQL, si utilizza SQL Server per creare la soluzione a disponibilità elevata, quindi è possibile utilizzare Generatore di topologie per associarla a un pool Front End.
  
Se si utilizza la disponibilità elevata del server back-end in un pool Front End associato a un altro pool Front End per il ripristino di emergenza, è consigliabile utilizzare la stessa soluzione a disponibilità elevata back-end in entrambi i pool. 
  
## <a name="database-mirroring"></a>Mirroring del database

Skype for Business Server supporta il mirroring con il software di database seguente:
  
- SQL Server 2019, sia edizione Enterprise che edizione Standard

- SQL Server 2017, sia edizione Enterprise che edizione Standard

- SQL Server 2016, sia edizione Enterprise che edizione Standard

- SQL Server 2014, sia edizione Enterprise che edizione Standard
    
- SQL Server 2012 SP2 e CU2, edizione Enterprise e edizione Standard
    

> [!NOTE]
> SQL Il mirroring è disponibile Skype for Business Server 2015, ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn e i metodi di clustering di failover SQL sono le uniche opzioni supportate con Skype for Business Server 2019.
    
Il mirroring asincrono del database non è supportato per la disponibilità elevata del server back-end in Skype for Business Server. Nel resto di questo documento, il mirroring del database significa mirroring sincrono del database, se non diversamente specificato esplicitamente. 
  
Quando si distribuisce il mirroring del database in un pool Front End, viene eseguito il mirroring di tutti i database di Skype for Business Server nel pool, incluso l'archivio di gestione centrale, se si trova nel pool, nonché del database dell'applicazione Response Group e del database dell'applicazione Parcheggio di chiamata, se tali applicazioni sono in esecuzione nel pool. 
  
Con il mirroring del database, non è necessario utilizzare l'archiviazione condivisa per i server. Ogni server mantiene la propria copia dei database nello spazio di archiviazione locale. 
  
È possibile scegliere di distribuire il mirroring del database con o senza un controllo. È consigliabile utilizzare un server di controllo poiché consente il failover automatico del server back-end. In caso contrario, un amministratore deve richiamare manualmente il failover. Se noti che anche se è distribuito un server di controllo, un amministratore può comunque richiamare manualmente il failover del server back-end, se necessario.
  
Se si dispone di un server di controllo, è possibile utilizzare un singolo server di controllo per più coppie di server back-end. Non esiste una corrispondenza esatta tra server di controllo e coppie di server back-end. Le distribuzioni in cui viene utilizzato un singolo server di controllo per più coppie di server back-end non sono resilienti quanto le topologie con un server di controllo separato per ogni coppia di server back-end. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Linee guida per la pianificazione del mirroring del server back-end

In generale, la configurazione del mirroring SQL tra due server di back-end con un server di controllo richiede che:
  
- La versione del server primario di SQL Server deve supportare SQL mirroring.
    
- I server primario, mirror e di controllo (se distribuito) abbiano la stessa versione di SQL Server. 
    
- Il server primario e mirror abbiano la stessa edizione di SQL Server. Il server di controllo può avere un'edizione diversa.
    
Per SQL procedure consigliate in termini di SQL versioni supportate per un ruolo di controllo, vedere ["Database Mirroring Witness"](/sql/database-engine/database-mirroring/database-mirroring-witness) in MSDN Library.
  
Prima di configurare il mirroring del server, è necessario configurare correttamente SQL del database. Per informazioni dettagliate, vedere "Configurare gli account di accesso per il mirroring del database o i gruppi di disponibilità [AlwaysOn (SQL Server)"](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).
  
Con il mirroring SQL, la modalità di recupero del database è impostata sempre su **Completa**. Ciò significa che è necessario monitorare le dimensioni del log delle transizioni ed eseguire regolarmente il backup dei log più grandi, per evitare che la memoria del disco dei server di back-end si riempia. La frequenza dei backup dei log delle transizioni dipende dal tasso di crescita dei log, che a sua volta dipende dalle transazioni del database relative alle attività degli utenti nel pool Front End. Per pianificare correttamente, è consigliabile determinare il tasso di crescita stimato del log delle transazioni per il carico di lavoro della distribuzione di Lync. I seguenti articoli contengono informazioni aggiuntive sul backup SQL e la gestione dei log:
  
> [!IMPORTANT]
> L'utilizzo di Generatore di topologie o cmdlet per configurare e rimuovere il mirroring di SQL è supportato solo quando i server primario, mirror e di controllo (se desiderato) appartengono tutti allo stesso dominio. Per configurare il mirroring SQL tra server su domini diversi, vedere la documentazione relativa a SQL Server. 

> [!NOTE]
> SQL Il mirroring è disponibile Skype for Business Server 2015, ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Tempo di ripristino per il failover automatico del server back-end con mirroring del database

Per il failover back-end automatico con mirroring del database, l'obiettivo di progettazione per l'obiettivo RTO (Recovery Time Objective) è 5 minuti. A causa del mirroring sincrono del database, non prevediamo la perdita di dati durante gli errori del server back-end, tranne in rari casi in cui i Front End Server e il server back-end si verificano contemporaneamente durante lo spostamento dei dati tra i server. L'obiettivo in termini di punto di ripristino (RPO, Recovery Point Objective) è 5 minuti.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Esperienza utente durante un errore del server back-end con mirroring del database

L'esperienza utente durante un errore dipende dalla natura dell'errore e dalla topologia.
  
Se si utilizza il mirroring del database e si dispone di un controllo configurato e l'entità ha esito negativo, il failover del server back-end si verifica automaticamente e rapidamente. Gli utenti attivi non dovrebbero osservare un'interruzione delle sessioni in corso.
  
Se invece non è configurato alcun server di controllo, l'amministratore necessiterà del tempo previsto per richiamare manualmente il failover. Durante questo intervallo è possibile che gli utenti attivi subiscano alcuni disagi. Continueranno a utilizzare normalmente le sessioni per circa 30 minuti. Se il database primario non è ancora stato ripristinato o un amministratore non ha eseguito il backup, gli utenti passano alla modalità resilienza, ovvero non sono in grado di eseguire attività che richiedono una modifica permanente in Lync Server, ad esempio l'aggiunta di un contatto.
  
Se si verifica un errore sia del server principale che dei server back-end mirror oppure di uno di questi server e del server di controllo, il server back-end non sarà disponibile (anche se il server principale è ancora in funzione). In questo caso, gli utenti attivi passano alla modalità resilienza dopo un intervallo di tempo.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Gruppi di disponibilità AlwaysOn e istanze del cluster di failover AlwaysOn

Skype for Business Server supporta i gruppi di disponibilità AlwaysOn solo come attivi/passivi, non attivi/attivi. 
  
Per usare i gruppi di disponibilità AlwaysOn o le istanze del cluster di failover AlwaysOn, è innanzitutto necessario SQL Server per configurare e configurare la soluzione a disponibilità elevata. È quindi possibile utilizzare Generatore di topologie per associarlo a un pool Front End.

Skype for Business Server supporta AlwaysOn con il software di database seguente:

- SQL Server 2019 edizione Enterprise

- SQL Server 2019 edizione Standard con limitazioni, vedere la nota seguente

- SQL Server 2017 edizione Enterprise

- SQL Server 2017 edizione Standard con limitazioni, vedere la nota seguente

- SQL Server 2016 edizione Enterprise

- SQL Server 2016 edizione Standard con limitazioni, vedere la nota seguente

- SQL Server 2014 edizione Enterprise
    
- SQL Server 2012 SP2 e CU2 edizione Enterprise

> [!NOTE]
> SQL Server 2019, 2017 e 2016 sono le uniche versioni supportate da Skype for Business Server 2019.

> [!NOTE]
> I gruppi di  disponibilità Always On non sono supportati SQL 2016, 2017 e 2019 Standard Edition, ma è possibile usare le istanze del cluster di failover Always On. Per [altre informazioni, vedere Edizioni e funzionalità supportate di SQL Server 2016.](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)
  
> [!IMPORTANT]
> I nomi delle istanze per più istanze del gruppo di disponibilità AlwaysOn devono essere uguali. 
  
Per la procedura di distribuzione dei gruppi di disponibilità AlwaysOn, vedere [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>SQL Server Failover Clustering

Skype for Business Server supporta il SQL Server clustering di failover con il software di database seguente:
  
- SQL Server 2019, sia edizione Enterprise che edizione Standard

- SQL Server 2017, sia edizione Enterprise che edizione Standard

- SQL Server 2016, sia edizione Enterprise che edizione Standard

- SQL Server 2014, sia edizione Enterprise che edizione Standard
    
- SQL Server 2012 SP2 e CU2, edizione Enterprise e edizione Standard

Per utilizzare SQL clustering di failover, è necessario innanzitutto configurare il cluster SQL Server prima di distribuire il pool Front End.To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool. Per le procedure consigliate e le istruzioni di installazione per il clustering di failover in SQL Server 2012, vedere [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) .

> [!NOTE]
> SQL Server 2019, 2017 e SQL Server 2016 sono le uniche versioni supportate da Skype for Business Server 2019.
    
Per utilizzare SQL clustering di failover, è necessario innanzitutto configurare il cluster SQL Server prima di distribuire il pool Front End.To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool. Per le procedure consigliate e le istruzioni di installazione per il clustering di failover SQL Server 2014 e 2016, vedere [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) . Per il clustering di failover in SQL Server 2008, vedere [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)) .
  
Quando si installa SQL Server, è consigliabile installare SQL Server Management Studio per gestire i percorsi dei file di database e di registro. SQL Server Management Studio viene installato come componente facoltativo quando si installa SQL Server.
