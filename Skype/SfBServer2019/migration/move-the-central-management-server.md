---
title: Spostare il server di gestione centrale
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Dopo la migrazione a Skype for Business Server 2019, è necessario spostare il server di gestione centrale nel front-end server o nel pool Skype for Business Server 2019 prima di poter rimuovere il server legacy.
ms.openlocfilehash: 5c3d090f762904aa5f076033a68e46139b1e84e4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618282"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Spostare il server di gestione centrale legacy Skype for Business Server 2019

Dopo la migrazione Skype for Business Server 2019 e prima di rimuovere il server legacy, è necessario spostare il server di gestione centrale nel front-end server o nel pool Skype for Business Server 2019. 
  
Il server di gestione centrale è un singolo sistema di replica master/a più repliche, in cui la copia di lettura/scrittura del database viene mantenuta dal Front End Server che contiene il server di gestione centrale. Ogni computer della topologia, incluso il Front End Server contenente il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server (denominato RTCLOCAL per impostazione predefinita) installato nel computer durante l'installazione e la distribuzione. Il database locale riceve gli aggiornamenti delle repliche tramite l Skype for Business Server Replicator Agent che viene eseguito come servizio in tutti i computer. Il nome del database effettivo nel server di gestione centrale e della replica locale è XDS, costituito da file xds.mdf e xds.ldf. Al percorso del database master fa riferimento un punto di controllo del servizio (SCP) in Servizi di dominio Active Directory. Tutti gli strumenti che utilizzano il server di gestione centrale per gestire e configurare Skype for Business Server utilizzare SCP per individuare l'archivio di gestione centrale.
  
Dopo aver spostato correttamente il server di gestione centrale, è necessario rimuovere i database del server di gestione centrale dal Front End Server originale. Per informazioni sulla rimozione dei database del server di gestione centrale, vedere [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Utilizzare il cmdlet Windows PowerShell **Move-CsManagementServer** in Skype for Business Server Management Shell per spostare il database dal database di SQL Server di installazione legacy al database SQL Server di Skype for Business Server 2019 e quindi aggiornare il Server di gestione centrale di Skype for Business Server 2019 in modo che punti al percorso del server di gestione centrale di Skype for Business Server 2019. 
  
Utilizzare le procedure descritte in questa sezione per preparare i Front End Server Skype for Business Server 2019 prima di spostare il server di gestione centrale.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Per preparare un edizione Enterprise Front End

1. Nel pool front-end Skype for Business Server 2019 edizione Enterprise in cui si desidera spostare il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins.** È inoltre necessario disporre SQL Server autorizzazioni utente sysadmin del database nel database in cui si desidera installare l'archivio di gestione centrale. 
    
2. Aprire la Skype for Business Server Management Shell.
    
3. Per creare il nuovo archivio di gestione centrale nel database Skype for Business Server 201 SQL Server 9, in Skype for Business Server Management Shell digitare:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Verificare che lo stato del servizio **Skype for Business Server Front-End** sia **Avviato**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Per preparare un edizione Standard Front End Server

1. Nel Front End Server di Skype for Business Server 2019 edizione Standard in cui si desidera spostare il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins.** 
    
2. Aprire la Skype for Business Server guidata.
    
3. Nella Distribuzione Skype for Business Server guidata fare clic su **Prepara primo edizione Standard server**.
    
4. Nella pagina **Esecuzione comandi in** corso, SQL Server Express viene installato come server di gestione centrale. Vengono create le regole firewall necessarie. Al termine dell'installazione del database e dei prerequisiti software, fare clic su **Fine**.
    
    > [!NOTE]
    > L'installazione iniziale può richiedere tempo senza che vengano visualizzati aggiornamenti visibili nella schermata riepilogativa di output dei comandi. Ciò è dovuto all'installazione di SQL Server Express. Se si desidera monitorare l'installazione del database, usare Gestione attività. 
  
5. Per creare il nuovo archivio di gestione centrale Skype for Business Server 2019 edizione Standard Front End Server, in Skype for Business Server Management Shell digitare: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Verificare che lo stato del servizio **Skype for Business Server Front-End** sia **Avviato**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Per spostare le installazioni legacy del server di gestione centrale Skype for Business Server 2019

1. Nel server Skype for Business Server 2019 che sarà il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins.** È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server. 
    
2. Aprire Skype for Business Server Management Shell (esegui come amministratore).
    
3. In Skype for Business Server Management Shell digitare: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > In caso contrario, risolvere il problema impedendo il completamento `Enable-CsTopology` del comando prima di continuare. Se **Enable-CsTopology** non riesce, lo spostamento avrà esito negativo e potrebbe lasciare la topologia in uno stato in cui non è presente alcun archivio di gestione centrale. 
  
4. Nel Skype for Business Server Front End Server o nel pool Front End 2019, in Skype for Business Server Management Shell digitare: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype for Business Server Management Shell visualizza i server, gli archivi file, gli archivi di database e i punti di connessione del servizio dello stato corrente e dello stato proposto. Leggere attentamente le informazioni e verificare che l'origine e la destinazione siano corrette. Digitare **S** per continuare o **N** per interrompere lo spostamento. 
    
6. Esaminare eventuali avvisi o errori generati dal comando **Move-CsManagementServer** e risolverli. 
    
7. Nel server Skype for Business Server 2019 aprire la Skype for Business Server guidata. 
    
8. In Skype for Business Server distribuzione guidata fare clic su Installa o aggiorna sistema **Skype for Business Server,** fare clic su Passaggio **2:** Installazione o rimozione componenti di Skype for Business Server, fare clic su **Avanti,** esaminare il riepilogo e quindi fare clic su **Fine.** 
    
9. Nel server di installazione legacy aprire la Distribuzione guidata. 
    
10. In Skype for Business Server distribuzione guidata fare clic su Installa o aggiorna sistema **Skype for Business Server,** fare clic su Passaggio **2:** Installazione o rimozione componenti di Skype for Business Server, fare clic su **Avanti,** esaminare il riepilogo e quindi fare clic su **Fine.** 
    
11. Riavviare il Skype for Business Server 2019. Questa operazione è necessaria a causa di una modifica dell'appartenenza a un gruppo per accedere al database del server di gestione centrale.
    
12. Per verificare che sia in corso la replica con il nuovo archivio di gestione centrale, in Skype for Business Server Management Shell digitare: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > Il processo di replica può richiedere tempo per aggiornare tutte le repliche correnti. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Per rimuovere i file dell'archivio di gestione centrale di installazione legacy dopo uno spostamento

1. Nel server di installazione legacy accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins.** È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server. 
    
2. Aprire Skype for Business Server Management Shell
    
    > [!CAUTION]
    > Non procedere con la rimozione dei file di database precedenti prima del completamento e della stabilizzazione della replica. Se si rimuovono i file prima di completare la replica, il processo di replica verrà interrotto e il server di gestione centrale appena spostato verrà lasciato in uno stato sconosciuto. Usare il cmdlet **Get-CsManagementStoreReplicationStatus** per verificare lo stato della replica. 
  
3. Per rimuovere i file di database dell'archivio di gestione centrale dall'installazione legacy del server di gestione centrale, digitare:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Ad esempio:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Dove il server back-end di installazione legacy è in una distribuzione edizione Enterprise o il nome di dominio completo del _\<FQDN of SQL Server\>_ server edizione Standard server. 
    

