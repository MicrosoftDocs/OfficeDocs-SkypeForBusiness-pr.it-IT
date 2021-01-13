---
title: Disponibilità elevata del server back-end in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Informazioni sulle opzioni di disponibilità elevata del server back-end supportate in Skype for Business Server, inclusi i gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn, il mirroring del database e il clustering di failover SQL.
ms.openlocfilehash: bbb55ded0d5ce1127f5dcab829907c533cc6316e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802926"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Disponibilità elevata del server back-end in Skype for Business Server
 
Informazioni sulle opzioni di disponibilità elevata del server back-end supportate in Skype for Business Server, inclusi i gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn, il mirroring del database e il clustering di failover SQL.
  
Per migliorare la disponibilità elevata per i server back-end, sono disponibili quattro opzioni:
  
- Mirroring del database
    
- Gruppi di disponibilità AlwaysOn
    
- Istanze del cluster di failover AlwaysOn (FCI)
    
- Clustering di failover SQL
    
L'utilizzo di una di queste soluzioni è facoltativo, ma è consigliabile mantenere la continuità aziendale della propria organizzazione. In caso contrario, l'utilizzo di un singolo server di database potrebbe causare la perdita di dati significativi del server Skype for business. 
  
È possibile configurare il mirroring del database utilizzando solo generatore di topologie. Per i gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn o il clustering di failover SQL, si utilizza SQL Server per creare la soluzione a disponibilità elevata, quindi è possibile utilizzare Generatore di topologie per associarlo a un pool Front end.
  
Se si utilizza la disponibilità elevata del server back-end in un pool Front end che è associato a un altro pool Front end per il ripristino di emergenza, è consigliabile utilizzare la stessa soluzione di disponibilità elevata back-end in entrambi i pool. 
  
## <a name="database-mirroring"></a>Mirroring del database

Skype for Business Server supporta il mirroring con il software di database seguente:
  
- SQL Server 2019, sia Enterprise Edition che Standard Edition

- SQL Server 2017, sia Enterprise Edition che Standard Edition

- SQL Server 2016, sia Enterprise Edition che Standard Edition

- SQL Server 2014, sia Enterprise Edition che Standard Edition
    
- SQL Server 2012 SP2 e CU2, sia Enterprise Edition che Standard Edition
    

> [!NOTE]
> Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono le uniche opzioni supportate con Skype for Business Server 2019.
    
Il mirroring asincrono dei database non è supportato per la disponibilità elevata del server back-end in Skype for Business Server. Nel resto del documento, il mirroring del database indica il mirroring del database sincrono, se non specificato in modo esplicito. 
  
Quando si distribuisce il mirroring del database in un pool Front End, tutti i database di Skype for Business Server nel pool vengono sottoposti a mirroring, incluso l'archivio di gestione centrale, se si trova in questo pool, nonché il database dell'applicazione Response Group e il database dell'applicazione Parcheggio di chiamata, se tali applicazioni sono in esecuzione nel pool. 
  
Con il mirroring del database, non è necessario utilizzare l'archiviazione condivisa per i server. Ogni server mantiene la propria copia dei database nello spazio di archiviazione locale. 
  
È possibile scegliere di distribuire il mirroring del database con o senza un controllo. È consigliabile utilizzare un server di controllo poiché consente il failover automatico del server back-end. In caso contrario, un amministratore deve richiamare manualmente il failover. Se noti che anche se è distribuito un server di controllo, un amministratore può comunque richiamare manualmente il failover del server back-end, se necessario.
  
Se si dispone di un server di controllo, è possibile utilizzare un singolo server di controllo per più coppie di server back-end. Non esiste una corrispondenza esatta tra server di controllo e coppie di server back-end. Le distribuzioni in cui viene utilizzato un singolo server di controllo per più coppie di server back-end non sono resilienti quanto le topologie con un server di controllo separato per ogni coppia di server back-end. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Linee guida per la pianificazione del mirroring dei server back-end

In generale, la configurazione del mirroring SQL tra due server di back-end con un server di controllo richiede che:
  
- La versione del server primario di SQL Server deve supportare il mirroring SQL.
    
- I server primario, mirror e di controllo (se distribuito) abbiano la stessa versione di SQL Server. 
    
- Il server primario e mirror abbiano la stessa edizione di SQL Server. Il server di controllo può avere un'edizione diversa.
    
Per le procedure consigliate SQL in termini di supporto per le versioni di SQL per un ruolo di controllo, vedere  ["database mirroring witness"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in MSDN Library.
  
Prima di configurare il mirroring del server, è necessario innanzitutto impostare le autorizzazioni di database SQL in modo corretto. Per informazioni dettagliate, vedere  ["configurare gli account di accesso per il mirroring del database o i gruppi di disponibilità AlwaysOn (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Con il mirroring SQL, la modalità di recupero del database è impostata sempre su **Completa**. Ciò significa che è necessario monitorare le dimensioni del log delle transizioni ed eseguire regolarmente il backup dei log più grandi, per evitare che la memoria del disco dei server di back-end si riempia. La frequenza dei backup dei log delle transizioni dipende dal tasso di crescita dei log, che a sua volta dipende dalle transazioni del database relative alle attività degli utenti nel pool Front End. Per pianificare correttamente, è consigliabile determinare il tasso di crescita stimato del log delle transazioni per il carico di lavoro della distribuzione di Lync. I seguenti articoli contengono informazioni aggiuntive sul backup SQL e la gestione dei log:
  
> [!IMPORTANT]
> L'utilizzo di generatore di topologie o cmdlet per configurare e rimuovere il mirroring SQL è supportato solo quando i server primari, mirror e Witness (se necessario) appartengono tutti allo stesso dominio. Per configurare il mirroring SQL tra server su domini diversi, vedere la documentazione relativa a SQL Server. 

> [!NOTE]
> Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Tempo di ripristino per il failover automatico del server back-end con il mirroring del database

Per il failover automatico del back-end con il mirroring del database, l'obiettivo ingegneristico per il periodo di tempo di ripristino (RTO) è di 5 minuti. A causa del mirroring del database sincrono, non si prevede la perdita di dati durante gli errori del server back-end, tranne in rare occasioni quando entrambi i Front End Server e il server back-end scendono contemporaneamente mentre i dati vengono spostati tra i server. L'obiettivo in termini di punto di ripristino (RPO, Recovery Point Objective) è 5 minuti.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Esperienza utente durante un errore del server back-end con il mirroring del database

L'esperienza utente durante un errore dipende dalla natura dell'errore e dalla topologia.
  
Se si utilizza il mirroring del database e si dispone di un controllo configurato e l'entità ha esito negativo, il failover del server back-end avviene automaticamente e rapidamente. Gli utenti attivi non dovrebbero osservare un'interruzione delle sessioni in corso.
  
Se invece non è configurato alcun server di controllo, l'amministratore necessiterà del tempo previsto per richiamare manualmente il failover. Durante questo intervallo è possibile che gli utenti attivi subiscano alcuni disagi. Continueranno a utilizzare normalmente le sessioni per circa 30 minuti. Se il principale non è ancora stato ripristinato o un amministratore non ha eseguito il failover del backup, gli utenti vengono passati alla modalità di resilienza, pertanto non sono in grado di eseguire attività che richiedono una modifica permanente su Lync Server, ad esempio l'aggiunta di un contatto.
  
Se si verifica un errore sia del server principale che dei server back-end mirror oppure di uno di questi server e del server di controllo, il server back-end non sarà disponibile (anche se il server principale è ancora in funzione). In questo caso, gli utenti attivi passano alla modalità resilienza dopo un intervallo di tempo.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Gruppi di disponibilità AlwaysOn e istanze del cluster di failover AlwaysOn

Skype for Business Server supporta i gruppi di disponibilità AlwaysOn solo come attivo/passivo, non attivo/attivo. 
  
Per utilizzare i gruppi di disponibilità AlwaysOn o le istanze del cluster di failover AlwaysOn, è innanzitutto necessario utilizzare SQL Server per impostare e configurare la soluzione di disponibilità elevata. È quindi possibile utilizzare il generatore di topologie per associarlo a un pool Front end.

Skype for Business Server supporta AlwaysOn con il software di database seguente:

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition con limitazioni, vedere la nota seguente

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition con limitazioni, vedere la nota seguente

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition con limitazioni, vedere la nota seguente

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 e CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019, 2017 e 2016 sono le uniche versioni supportate da Skype for Business Server 2019.

> [!NOTE]
> Sempre i gruppi di disponibilità **non** sono supportati nelle edizioni standard di SQL 2016, 2017 e 2019, ma è possibile utilizzare sempre le istanze del cluster di failover. Per ulteriori informazioni, vedere [edizioni e funzionalità supportate di SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) .
  
> [!IMPORTANT]
> I nomi di istanza per più istanze del gruppo di disponibilità AlwaysOn devono essere uguali. 
  
Per i passaggi per la distribuzione di gruppi di disponibilità AlwaysOn, vedere [deploy an AlwaysOn Availability Group on a back end server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>Clustering di failover di SQL Server

Skype for Business Server supporta il clustering di failover di SQL Server con il software di database seguente:
  
- SQL Server 2019, sia Enterprise Edition che Standard Edition

- SQL Server 2017, sia Enterprise Edition che Standard Edition

- SQL Server 2016, sia Enterprise Edition che Standard Edition

- SQL Server 2014, sia Enterprise Edition che Standard Edition
    
- SQL Server 2012 SP2 e CU2, sia Enterprise Edition che Standard Edition

Per utilizzare il clustering di failover di SQL Server, è necessario innanzitutto impostare e configurare il cluster di SQL di prima della distribuzione del pool Front end. Per le procedure consigliate e le istruzioni di installazione per il clustering di failover in SQL Server 2012, vedere [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx) .

> [!NOTE]
> SQL Server 2019, 2017 e SQL Server 2016 sono le uniche versioni supportate da Skype for Business Server 2019.
    
Per utilizzare il clustering di failover di SQL Server, è necessario innanzitutto impostare e configurare il cluster di SQL di prima della distribuzione del pool Front end. Per le procedure consigliate e le istruzioni di installazione per il clustering di failover in SQL Server 2014 e 2016, vedere [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx) . Per il clustering di failover in SQL Server 2008, vedere [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx) .
  
Quando si installa SQL Server, è consigliabile installare SQL Server Management Studio per gestire i percorsi dei file di database e di registro. SQL Server Management Studio viene installato come componente facoltativo quando si installa SQL Server.
  
