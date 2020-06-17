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
description: Dopo aver eseguito la migrazione a Skype for Business Server 2019, è necessario spostare il server di gestione centrale nel server o pool Front End di Skype for Business Server 2019, prima di poter rimuovere il server legacy.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752468"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Spostare il server di gestione centrale legacy su Skype for Business Server 2019

Dopo aver eseguito la migrazione a Skype for Business Server 2019 e prima di poter rimuovere il server legacy, è necessario spostare il server di gestione centrale nel server o nel pool Front End di Skype for Business Server 2019. 
  
Il server di gestione centrale è un singolo sistema di replica master/multiple, in cui la copia di lettura/scrittura del database è conservata dal front end server che contiene il server di gestione centrale. Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server, denominata RTCLOCAL per impostazione predefinita, installata nel computer durante l'installazione e la distribuzione. Il database locale riceve gli aggiornamenti delle repliche tramite l'agente replica Replicator di Skype for Business Server che viene eseguito come servizio in tutti i computer. Il nome del database effettivo sul server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf. Il percorso del database master è fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory. Tutti gli strumenti che utilizzano il server di gestione centrale per gestire e configurare Skype for Business Server utilizzano il SCP per individuare l'archivio di gestione centrale.
  
Dopo aver correttamente spostato il server di gestione centrale, è necessario rimuovere i database del server di gestione centrale dal front end server originale. Per informazioni sulla rimozione dei database del server di gestione centrale, vedere [rimuovere il database di SQL Server per un pool Front End](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Utilizzare il cmdlet **Move-csmanagementserver** di Windows PowerShell in Skype for Business Server Management Shell per spostare il database dal database di SQL Server di installazione legacy al database di SQL Server di Skype for business server 2019 e quindi aggiornare il punto SCP in modo che punti al percorso del server di gestione centrale di Skype for business server 2019. 
  
Utilizzare le procedure descritte in questa sezione per preparare i server front end di Skype for Business Server 2019 prima di spostare il server di gestione centrale.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Per preparare un pool Enterprise Edition front end

1. Nel pool di Skype for Business Server 2019 Enterprise Edition front end in cui si desidera spostare il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . È inoltre necessario disporre di autorizzazioni e diritti utente del database di SQL Server per il database in cui si desidera installare l'archivio di gestione centrale. 
    
2. Aprire la shell di gestione di Skype for Business Server.
    
3. Per creare il nuovo archivio di gestione centrale nel database di SQL Server di Skype for Business Server 2019, in Skype for Business Server Management Shell digitare quanto segue:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Verificare che lo stato del servizio **front-end di Skype for Business Server** sia **avviato**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Per preparare un front end server Standard Edition

1. In Skype for Business Server 2019 Standard Edition Front End Server in cui si desidera spostare il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . 
    
2. Aprire la distribuzione guidata di Skype for Business Server.
    
3. Nella distribuzione guidata di Skype for Business Server, fare clic su **prepara primo server Standard Edition**.
    
4. Nella pagina **esecuzione comandi** in corso, SQL Server Express è installato come server di gestione centrale. Vengono create le regole firewall necessarie. Al termine dell'installazione del database e dei prerequisiti software, fare clic su **Fine**.
    
    > [!NOTE]
    > L'installazione iniziale può richiedere tempo senza che vengano visualizzati aggiornamenti visibili nella schermata riepilogativa di output dei comandi. Ciò è dovuto all'installazione di SQL Server Express. Se si desidera monitorare l'installazione del database, usare Gestione attività. 
  
5. Per creare il nuovo archivio di gestione centrale in Skype for Business Server 2019 Standard Edition Front End Server, in Skype for Business Server Management Shell digitare quanto segue: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Verificare che lo stato del servizio **front-end di Skype for Business Server** sia **avviato**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Per spostare l'eredità, installa il server di gestione centrale in Skype for Business Server 2019

1. Sul server Skype for Business Server 2019 che fungerà da server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server. 
    
2. Aprire Skype for Business Server Management Shell (Esegui come amministratore).
    
3. In Skype for Business Server Management Shell, digitare quanto segue: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Se `Enable-CsTopology` l'operazione non è riuscita, risolvere il problema impedendo il completamento del comando prima di continuare. Se **Enable-CsTopology** non ha esito positivo, lo spostamento avrà esito negativo e potrebbe lasciare la topologia in uno stato in cui non è presente un archivio di gestione centrale. 
  
4. In Skype for Business Server 2019 front end server o pool Front End, digitare quanto segue nella shell di gestione di Lync 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype for Business Server Management Shell consente di visualizzare i server, gli archivi di file, gli archivi di database e i punti di connessione del servizio dello stato corrente e dello stato proposto. Leggere attentamente le informazioni e verificare che l'origine e la destinazione siano corrette. Digitare **S** per continuare o **N** per interrompere lo spostamento. 
    
6. Esaminare eventuali avvisi o errori generati dal comando **Move-CsManagementServer** e risolverli. 
    
7. Sul server Skype for Business Server 2019, aprire la distribuzione guidata di Skype for Business Server. 
    
8. Nella distribuzione guidata di Skype for Business Server, fare clic su **Installa o aggiorna il sistema di Skype for Business Server**, fare clic su **passaggio 2: installazione o rimozione dei componenti di Skype for Business Server**, fare clic su **Avanti**, esaminare il riepilogo e quindi fare clic su **fine**. 
    
9. Nel server di installazione legacy aprire la distribuzione guidata. 
    
10. Nella distribuzione guidata di Skype for Business Server, fare clic su **Installa o aggiorna il sistema di Skype for Business Server**, fare clic su **passaggio 2: installazione o rimozione dei componenti di Skype for Business Server**, fare clic su **Avanti**, esaminare il riepilogo e quindi fare clic su **fine**. 
    
11. Riavviare il server Skype for Business Server 2019. Questa operazione è necessaria a causa di una modifica dell'appartenenza a un gruppo al database del server di gestione centrale di Access.
    
12. Per confermare che la replica con il nuovo archivio di gestione centrale si sta verificando, in Skype for Business Server Management Shell digitare quanto segue: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > Il processo di replica può richiedere tempo per aggiornare tutte le repliche correnti. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Per rimuovere i file dell'archivio di gestione centrale di installazione legacy dopo uno spostamento

1. Nel server di installazione legacy, eseguire l'accesso al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server. 
    
2. Aprire la shell di gestione di Skype for Business Server
    
    > [!CAUTION]
    > Non procedere con la rimozione dei file di database precedenti prima del completamento e della stabilizzazione della replica. Se si rimuovono i file prima del completamento della replica, si interrompe il processo di replica e si lascia il server di gestione centrale appena spostato in uno stato sconosciuto. Usare il cmdlet **Get-CsManagementStoreReplicationStatus** per verificare lo stato della replica. 
  
3. Per rimuovere i file di database dell'archivio di gestione centrale dal server di gestione centrale di installazione legacy, digitare quanto segue:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Ad esempio:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Dove _\<FQDN of SQL Server\>_ è il server back-end di installazione legacy in una distribuzione Enterprise Edition o il nome di dominio completo del server Standard Edition. 
    

