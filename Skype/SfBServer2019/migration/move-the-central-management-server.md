---
title: Trasferire il server di gestione centrale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo aver eseguito la migrazione a Skype for Business Server 2019, è necessario trasferire il server di gestione centrale nel server o nel pool di Skype for Business Server 2019 front end, prima di poter rimuovere il server legacy.
ms.openlocfilehash: b6a2dd08949b5b15370f27e1da936009048982f6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990931"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Trasferire il server di gestione centrale legacy in Skype for Business Server 2019

Dopo aver eseguito la migrazione a Skype for Business Server 2019 e prima di poter rimuovere il server legacy, è necessario trasferire il server di gestione centrale nel server o nel pool di front end di Skype for Business Server 2019. 
  
Il server di gestione centrale è un singolo sistema master/replica multipla, in cui la copia di lettura/scrittura del database è tenuta dal server front-end che contiene il server di gestione centrale. Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, ha una copia di sola lettura dei dati di Central Management store nel database di SQL Server (denominata RTCLOCAL per impostazione predefinita) installati nel computer durante l'installazione e distribuzione. Il database locale riceve gli aggiornamenti delle repliche tramite l'agente di replica Replicator di Skype for Business Server che viene eseguito come servizio in tutti i computer. Il nome del database effettivo nel server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf. Il percorso del database master viene fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory. Tutti gli strumenti che usano il server di gestione centralizzato per gestire e configurare Skype for Business Server usano l'SCP per individuare l'Central Management store.
  
Dopo aver spostato correttamente il server di gestione centrale, è necessario rimuovere i database di Central Management Server dal server front-end originale. Per informazioni sulla rimozione dei database di Central Management Server, vedere [rimuovere il database di SQL Server per un pool Front-End](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Puoi usare il cmdlet **Move-csmanagementserver** di Windows PowerShell in Skype for Business Server Management Shell per spostare il database dal database di SQL Server di installazione legacy al database di SQL Server di Skype for business server 2019 e quindi aggiornare il SCP in modo che punti al percorso del server di gestione centrale di Skype for business server 2019. 
  
Usare le procedure descritte in questa sezione per preparare i server front end di Skype for Business Server 2019 prima di trasferire il server di gestione centrale.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Per preparare un pool di front-end Enterprise Edition

1. Nel pool di front end di Skype for Business Server 2019 Enterprise Edition in cui si vuole spostare il server di gestione centralizzato, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . Per il database in cui si vuole installare l'Central Management store, è necessario disporre anche dei diritti utente e delle autorizzazioni di amministratore del database di SQL Server. 
    
2. Aprire Skype for Business Server Management Shell.
    
3. Per creare il nuovo Central Management store nel database di SQL Server di Skype for Business Server 2019, in Skype for Business Server Management Shell digitare:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Verificare che lo stato del servizio **front-end di Skype for Business Server** sia stato **avviato**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Per preparare un server front-end Standard Edition

1. Nel server front-end di Skype for Business Server 2019 Standard Edition in cui si vuole spostare il server di gestione centralizzato, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . 
    
2. Aprire la distribuzione guidata di Skype for Business Server.
    
3. Nella distribuzione guidata di Skype for Business Server fare clic su **prepara primo server Standard Edition**.
    
4. Nella pagina **esecuzione dei comandi** , SQL Server Express viene installato come server di gestione centrale. Vengono create le regole firewall necessarie. Dopo aver completato l'installazione del database e del software prerequisito, fare clic su **fine**.
    
    > [!NOTE]
    > L'installazione iniziale può richiedere del tempo senza aggiornamenti visibili alla schermata di riepilogo dell'output del comando. Ciò è dovuto all'installazione di SQL Server Express. Se è necessario monitorare l'installazione del database, usare Gestione attività per monitorare la configurazione. 
  
5. Per creare il nuovo Central Management store in Skype for Business Server 2019 Standard Edition Front End Server, in Skype for Business Server Management Shell digitare: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Verificare che lo stato del servizio **front-end di Skype for Business Server** sia stato **avviato**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Per trasferire l'eredità, installa il server di gestione centrale in Skype for Business Server 2019

1. Nel server Skype for Business Server 2019, che sarà il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . È inoltre necessario disporre dei diritti e delle autorizzazioni per gli utenti di amministratore del database di SQL Server. 
    
2. Aprire Skype for Business Server Management Shell (Esegui come amministratore).
    
3. In Skype for Business Server Management Shell digitare: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Se `Enable-CsTopology` l'operazione non riesce, risolvere il problema impedendo il completamento del comando prima di continuare. Se **Enable-CsTopology** non riesce, il passaggio non riesce e può lasciare la topologia in uno stato in cui non è presente un Central Management store. 
  
4. In Skype for Business Server 2019 front end server o front end pool, in Skype for Business Server Management Shell digitare: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype for Business Server Management Shell Visualizza i server, gli archivi di file, gli archivi di database e i punti di connessione del servizio dello stato corrente e dello stato proposto. Leggere attentamente le informazioni e verificare che si tratta dell'origine e della destinazione desiderate. Digitare **Y** per continuare o **N** per interrompere lo stato di trasferimento. 
    
6. Esaminare gli avvisi o gli errori generati dal comando **Move-csmanagementserver** e risolverli. 
    
7. Nel server Skype for Business Server 2019 aprire la distribuzione guidata di Skype for Business Server. 
    
8. Nella distribuzione guidata di Skype for Business Server fare clic su **installazione o aggiornamento di Skype for Business Server System**, fare clic su **passaggio 2: configurare o rimuovere i componenti di Skype for Business Server**, fare clic su **Avanti**, rivedere il riepilogo e quindi fare clic su **fine**. 
    
9. Nel server di installazione legacy aprire la distribuzione guidata. 
    
10. Nella distribuzione guidata di Skype for Business Server fare clic su **installazione o aggiornamento di Skype for Business Server System**, fare clic su **passaggio 2: configurare o rimuovere i componenti di Skype for Business Server**, fare clic su **Avanti**, rivedere il riepilogo e quindi fare clic su **fine**. 
    
11. Riavviare il server di Skype for Business Server 2019. Questa operazione è necessaria a causa di una modifica dell'appartenenza al gruppo per accedere al database di Central Management Server.
    
12. Per verificare che la replica con il nuovo Central Management store si verifichi, in Skype for Business Server Management Shell digitare: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > La replica può richiedere del tempo per aggiornare tutte le repliche correnti. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Per rimuovere i file legacy install Central Management store dopo una mossa

1. Nel server di installazione legacy accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . È inoltre necessario disporre dei diritti e delle autorizzazioni per gli utenti di amministratore del database di SQL Server. 
    
2. Aprire Skype for Business Server Management Shell
    
    > [!CAUTION]
    > Non procedere con la rimozione dei file di database precedenti finché la replica non è completa ed è stabile. Se si rimuovono i file prima di completare la replica, si interromperà il processo di replica e si lascerà il server di gestione centralizzato appena spostato in uno stato sconosciuto. Usa il cmdlet **Get-CsManagementStoreReplicationStatus** per confermare lo stato di replica. 
  
3. Per rimuovere i file di database di Central Management Store dal server di gestione centrale legacy install, digitare:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Ad esempio:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Dove il _ \<nome di dominio completo\> di SQL Server_ è l'installazione legacy back end server in una distribuzione di Enterprise Edition o il nome di dominio completo del server Standard Edition. 
    

