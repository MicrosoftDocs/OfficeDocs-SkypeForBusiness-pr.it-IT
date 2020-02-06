---
title: Disponibilità elevata del server back-end in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: a0aeb53aea0ee2eab25875de0fddbfd0fc26d90a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815954"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Disponibilità elevata del server back-end in Skype for Business Server
 
Informazioni sulle opzioni di disponibilità elevata del server back-end supportate in Skype for Business Server, inclusi i gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn, il mirroring del database e il clustering di failover SQL.
  
Per migliorare la disponibilità elevata per i server back-end, sono disponibili quattro opzioni:
  
- Mirroring del database
    
- Gruppi di disponibilità AlwaysOn
    
- Istanze del cluster di failover AlwaysOn (FCI)
    
- Clustering di failover SQL
    
L'uso di una di queste soluzioni è facoltativo, ma è consigliabile mantenere la continuità aziendale dell'organizzazione. In caso contrario, l'esecuzione di un singolo server di database può causare la perdita di dati significativi di Skype for Business Server. 
  
Puoi configurare il mirroring del database usando solo generatore di topologie. Per i gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn o il clustering di failover SQL, è possibile usare SQL Server per creare la soluzione di disponibilità elevata, quindi usare generatore di topologia per associarlo a un pool di front-end.
  
Se si usa la disponibilità elevata del server back-end su un pool Front-end che è associato a un altro pool Front-end per il ripristino di emergenza, è consigliabile usare la stessa soluzione di disponibilità elevata di back-end in entrambi i pool. 
  
## <a name="database-mirroring"></a>Mirroring del database

Skype for Business Server supporta il mirroring con il software di database seguente:
  
- SQL Server 2019, sia Enterprise Edition che Standard Edition

- SQL Server 2017, sia Enterprise Edition che Standard Edition

- SQL Server 2016, sia Enterprise Edition che Standard Edition

- SQL Server 2014, sia Enterprise Edition che Standard Edition
    
- SQL Server 2012 SP2 e CU2, sia Enterprise Edition che Standard Edition
    

> [!NOTE]
> Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.
    
Il mirroring asincrono del database non è supportato per la disponibilità elevata del server back-end in Skype for Business Server. Nel resto del documento, il mirroring del database indica il mirroring sincrono del database, a meno che non sia specificato diversamente esplicitamente. 
  
Quando si distribuisce il mirroring del database in un pool Front-End, tutti i database di Skype for Business Server nel pool sono speculari, incluso l'Central Management store, se si trova in questo pool, nonché il database dell'applicazione Response Group e il parcheggio delle chiamate database dell'applicazione, se tali applicazioni sono in uso nel pool. 
  
Con il mirroring del database, non è necessario usare lo spazio di archiviazione condiviso per i server. Ogni server mantiene la copia dei database in uno spazio di archiviazione locale. 
  
È possibile scegliere di distribuire il mirroring del database con o senza un testimone. È consigliabile usare un testimone perché consente il failover del server back-end come automatico. In caso contrario, un amministratore deve richiamare manualmente il failover. Tieni presente che anche se viene distribuito un testimone, un amministratore può richiamare manualmente il failover del server di back-end, se necessario.
  
Se si usa un testimone, è possibile usare un solo testimone per più coppie di server back-end. Non esiste una stretta corrispondenza di 1:1 tra i testimoni e le coppie di server back-end. Le distribuzioni che usano un singolo Witness per più coppie di server back-end non sono abbastanza resilienti come le topologie con un testimone separato per ogni coppia di server back-end. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Linee guida per la pianificazione del mirroring del server back-end

In generale, la configurazione del mirroring SQL tra i due server back-end con un testimone richiede quanto segue:
  
- La versione del server primario di SQL Server deve supportare il mirroring SQL.
    
- Il principale, il mirror e il Witness (se distribuiti) devono avere la stessa versione di SQL Server. 
    
- Il principale e lo specchio devono avere la stessa edizione di SQL Server. Il testimone può avere una versione diversa.
    
Per le procedure consigliate SQL in termini di supporto delle versioni SQL per un ruolo di testimone, vedere ["mirroring del database"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in MSDN Library.
  
Prima di configurare il mirroring del server, è prima necessario configurare le autorizzazioni di database SQL in modo corretto. Per informazioni dettagliate, vedere ["configurare gli account di accesso per il mirroring del database o i gruppi di disponibilità AlwaysOn (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Con il mirroring SQL, la modalità di ripristino del database è sempre impostata su **completo**, pertanto è necessario monitorare in modo regolare le dimensioni del log delle transazioni e il backup dei log delle transazioni per evitare di esaurire lo spazio su disco nei server back-end. La frequenza dei backup del log delle transazioni dipende dalla velocità di crescita del log, che a sua volta dipende dalle transazioni di database sostenute dalle attività degli utenti nel pool Front-end. È consigliabile determinare la quantità di crescita del log delle transazioni prevista per il carico di lavoro di distribuzione di Lync in modo da poter eseguire la pianificazione di conseguenza. Gli articoli seguenti contengono informazioni aggiuntive su backup e gestione dei log di SQL:
  
> [!IMPORTANT]
> L'uso di generatore di topologie o cmdlet per configurare e rimuovere il mirroring SQL è supportato solo quando i server primari, mirror e Witness (se necessario) appartengono tutti allo stesso dominio. Se si vuole configurare il mirroring SQL tra server in diversi domini, vedere la documentazione di SQL Server. 

> [!NOTE]
> Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Tempo di recupero per il failover automatico del server back-end con il mirroring del database

Per il failover automatico del back-end con il mirroring del database, la destinazione ingegneristica per l'obiettivo del tempo di recupero (RTO) è di 5 minuti. A causa del mirroring sincrono del database, non anticipiamo la perdita di dati durante gli errori del server back-end, tranne in rare occasioni in cui entrambi i server front-end e il server back-end scendono contemporaneamente mentre i dati vengono spostati tra i server. La destinazione ingegneristica per l'obiettivo del punto di ripristino (RPO) è di 5 minuti.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Esperienza utente durante l'errore del server back-end con il mirroring del database

L'esperienza utente durante un errore dipende dalla natura dell'errore e dalla topologia.
  
Se si usa il mirroring del database e si configura un testimone e l'entità non riesce, il failover del server di back-end avviene automaticamente e rapidamente. Gli utenti attivi non dovrebbero notare molte interruzioni delle sessioni in corso.
  
Se non sono configurati i testimoni, sarà necessario un po' di tempo prima che l'amministratore richiami manualmente il failover. Durante tale periodo gli utenti attivi potrebbero essere interessati. Continueranno le loro sessioni normalmente per circa 30 minuti. Se il principale non è ancora stato ripristinato o un amministratore non ha eseguito il failover del backup, gli utenti vengono convertiti in modalità resilienza, pertanto non sono in grado di eseguire attività che richiedono una modifica persistente in Lync Server, ad esempio l'aggiunta di un contatto.
  
Se i server di back-end di Principal e mirror non riescono o se uno di questi server e il witness non riescono, il server back-end diventerà non disponibile (anche se è l'entità che sta ancora lavorando). In questo caso, dopo qualche tempo, gli utenti attivi vengono convertiti in modalità resilienza.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Gruppi di disponibilità AlwaysOn e istanze di cluster di failover AlwaysOn

Skype for Business Server supporta i gruppi di disponibilità AlwaysOn solo come attivi/passivi, non attivi/attivi. 
  
Per usare gruppi di disponibilità AlwaysOn o istanze di cluster di failover AlwaysOn, è necessario prima di tutto usare SQL Server per impostare e configurare la soluzione per la disponibilità elevata. Puoi quindi usare generatore di topologia per associarlo a un pool Front-end.

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
> SQL Server 2019, 2017 e 2016 sono le sole versioni supportate da Skype for Business Server 2019.

> [!NOTE]
> Sempre in gruppi di disponibilità **non** è supportata nelle edizioni Standard SQL 2016, 2017 e 2019, ma è possibile usare sempre le istanze del cluster di failover. Per altre informazioni, vedere [edizioni e funzionalità supportate di SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) .
  
> [!IMPORTANT]
> I nomi di istanza per più istanze di gruppi di disponibilità AlwaysOn devono essere uguali. 
  
Per i passaggi per la distribuzione di gruppi di disponibilità AlwaysOn, vedere [distribuire un gruppo di disponibilità AlwaysOn in un server back-end in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>Clustering di failover di SQL Server

Skype for Business Server supporta il clustering di failover di SQL Server con il software di database seguente:
  
- SQL Server 2019, sia Enterprise Edition che Standard Edition

- SQL Server 2017, sia Enterprise Edition che Standard Edition

- SQL Server 2016, sia Enterprise Edition che Standard Edition

- SQL Server 2014, sia Enterprise Edition che Standard Edition
    
- SQL Server 2012 SP2 e CU2, sia Enterprise Edition che Standard Edition

Per usare il clustering di failover SQL, prima di distribuire il pool di front-end è consigliabile configurare il cluster di SQL Server e configurarlo prima di tutto. Per le procedure consigliate e le istruzioni di configurazione per il clustering di failover [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)in SQL Server 2012, vedere.

> [!NOTE]
> SQL Server 2019, 2017 e SQL Server 2016 sono le sole versioni supportate da Skype for Business Server 2019.
    
Per usare il clustering di failover SQL, prima di distribuire il pool di front-end è consigliabile configurare il cluster di SQL Server e configurarlo prima di tutto. Per le procedure consigliate e le istruzioni di configurazione per il clustering di failover in SQL [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)Server 2014 e 2016, vedere. Per il clustering di failover in SQL Server 2008 [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx), vedere.
  
Quando si installa SQL Server, è necessario installare SQL Server Management Studio per gestire le posizioni per i percorsi dei file di database e di log. SQL Server Management Studio viene installato come componente facoltativo durante l'installazione di SQL Server.
  
