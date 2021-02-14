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
localization_priority: Normal
description: Dopo aver migrato a Skype for Business Server 2019, è necessario spostare il server di gestione centrale nel Front End Server o nel pool di Skype for Business Server 2019, prima di poter rimuovere il server legacy.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752468"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Spostare il server di gestione centrale legacy in Skype for Business Server 2019

Dopo la migrazione a Skype for Business Server 2019 e prima di rimuovere il server legacy, è necessario spostare il server di gestione centrale nel Front End Server o nel pool di Skype for Business Server 2019. 
  
Il server di gestione centrale è un singolo sistema di replica master/multiple, in cui la copia di lettura/scrittura del database è contenuta nel Front End Server contenente il server di gestione centrale. Ogni computer della topologia, incluso il Front End Server contenente il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server (denominato RTCLOCAL per impostazione predefinita) installato nel computer durante l'installazione e la distribuzione. Il database locale riceve gli aggiornamenti delle repliche tramite l'agente ReplicaTor di Skype for Business Server che viene eseguito come servizio in tutti i computer. Il nome del database effettivo nel server di gestione centrale e nella replica locale è XDS, costituito da file xds.mdf e xds.ldf. Al percorso del database master viene fatto riferimento da un punto di controllo del servizio (SCP) in Servizi di dominio Active Directory. Tutti gli strumenti che utilizzano il server di gestione centrale per gestire e configurare Skype for Business Server utilizzano il pannello di controllo del servizio per individuare l'archivio di gestione centrale.
  
Dopo aver spostato correttamente il server di gestione centrale, è necessario rimuovere i database del server di gestione centrale dal Front End Server originale. Per informazioni sulla rimozione dei database del server di gestione centrale, vedere [Remove the SQL Server database for a Front End pool.](remove-the-sql-server-database-for-a-front-end-pool.md)
  
Utilizzare il cmdlet Windows PowerShell **Move-CsManagementServer** in Skype for Business Server Management Shell per spostare il database dal database di SQL Server di installazione legacy al database SQL Server di Skype for Business Server 2019 e quindi aggiornare il punto SCP in modo che punti al percorso del server di gestione centrale di Skype for Business Server 2019. 
  
Utilizzare le procedure descritte in questa sezione per preparare i Front End Server di Skype for Business Server 2019 prima di spostare il server di gestione centrale.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Per preparare un pool Enterprise Edition Front End

1. Nel pool Front End di Skype for Business Server 2019 Enterprise Edition in cui si desidera spostare il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins.** È inoltre necessario disporre SQL Server autorizzazioni utente sysadmin del database nel database in cui si desidera installare l'archivio di gestione centrale. 
    
2. Aprire Skype for Business Server Management Shell.
    
3. Per creare il nuovo archivio di gestione centrale nel database di SQL Server di Skype for Business Server 2019, in Skype for Business Server Management Shell digitare:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Verificare che lo stato del servizio **Front-End** di Skype for Business Server sia **Avviato.**
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Per preparare un Front End Server Standard Edition

1. In Skype for Business Server 2019 Standard Edition Front End Server in cui si desidera spostare il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins.** 
    
2. Aprire la Distribuzione guidata di Skype for Business Server.
    
3. Nella Distribuzione guidata di Skype for Business Server, fare clic **su Prepara il primo server Standard Edition.**
    
4. Nella pagina **Esecuzione comandi in** corso, SQL Server Express viene installato come server di gestione centrale. Vengono create le regole firewall necessarie. Al termine dell'installazione del database e dei prerequisiti software, fare clic su **Fine**.
    
    > [!NOTE]
    > L'installazione iniziale può richiedere tempo senza che vengano visualizzati aggiornamenti visibili nella schermata riepilogativa di output dei comandi. Ciò è dovuto all'installazione di SQL Server Express. Se si desidera monitorare l'installazione del database, usare Gestione attività. 
  
5. Per creare il nuovo archivio di gestione centrale in Skype for Business Server 2019 Standard Edition Front End Server, in Skype for Business Server Management Shell digitare: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Verificare che lo stato del servizio **Front-End** di Skype for Business Server sia **Avviato.**
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Per spostare le installazioni legacy del server di gestione centrale in Skype for Business Server 2019

1. Nel server Skype for Business Server 2019 che sarà il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins.** È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server. 
    
2. Aprire Skype for Business Server Management Shell (esegui come amministratore).
    
3. In Skype for Business Server Management Shell digitare: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > In `Enable-CsTopology` caso contrario, risolvere il problema impedendo il completamento del comando prima di continuare. Se **Enable-CsTopology** non riesce, lo spostamento avrà esito negativo e potrebbe lasciare la topologia in uno stato in cui non è presente alcun archivio di gestione centrale. 
  
4. Nel Front End Server o nel pool Front End Server di Skype for Business Server 2019, in Skype for Business Server Management Shell, digitare: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype for Business Server Management Shell visualizza i server, gli archivi file, gli archivi database e i punti di connessione del servizio dello stato corrente e dello stato proposto. Leggere attentamente le informazioni e verificare che l'origine e la destinazione siano corrette. Digitare **S** per continuare o **N** per interrompere lo spostamento. 
    
6. Esaminare eventuali avvisi o errori generati dal comando **Move-CsManagementServer** e risolverli. 
    
7. Nel server Skype for Business Server 2019 apri la Distribuzione guidata di Skype for Business Server. 
    
8. In Skype for Business Server Deployment Wizard, fare clic su **Install or Update Skype for Business Server System,** click Step **2: Setup or Remove Skype for Business Server Components,** click **Next,** review the summary, and then click **Finish**. 
    
9. Nel server di installazione legacy aprire la Distribuzione guidata. 
    
10. In Skype for Business Server Deployment Wizard, fare clic su **Install or Update Skype for Business Server System,** click Step **2: Setup or Remove Skype for Business Server Components,** click **Next,** review the summary, and then click **Finish**. 
    
11. Riavviare il server Skype for Business Server 2019. Questa operazione è necessaria a causa di una modifica dell'appartenenza a un gruppo per accedere al database del server di gestione centrale.
    
12. Per verificare che sia in corso la replica con il nuovo archivio di gestione centrale, in Skype for Business Server Management Shell digitare: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > Il processo di replica può richiedere tempo per aggiornare tutte le repliche correnti. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Per rimuovere i file dell'archivio di gestione centrale dell'installazione legacy dopo uno spostamento

1. Nel server di installazione legacy, accedere al computer in cui è installata Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins.** È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server. 
    
2. Aprire Skype for Business Server Management Shell
    
    > [!CAUTION]
    > Non procedere con la rimozione dei file di database precedenti prima del completamento e della stabilizzazione della replica. Se si rimuovono i file prima di completare la replica, il processo di replica verrà interrotto e il server di gestione centrale appena spostato verrà lasciato in uno stato sconosciuto. Usare il cmdlet **Get-CsManagementStoreReplicationStatus** per verificare lo stato della replica. 
  
3. Per rimuovere i file di database dell'archivio di gestione centrale dal server di gestione centrale dell'installazione legacy, digitare:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Ad esempio:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Dove il server back-end di installazione legacy è in una distribuzione Enterprise Edition o il  _\<FQDN of SQL Server\>_ nome di dominio completo del server Standard Edition. 
    

