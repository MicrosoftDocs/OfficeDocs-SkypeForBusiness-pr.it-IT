---
title: Associare un archivio di monitoraggio a un pool di front-end in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Riepilogo: informazioni su come associare i pool Front-end a un archivio di monitoraggio usato da Skype for Business Server.'
ms.openlocfilehash: 26d846ad533c5ea49fa371cfa4fedab24bf56307
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790044"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Associare un archivio di monitoraggio a un pool di front-end in Skype for Business Server 
**Riepilogo:** Informazioni su come associare i pool Front-end a un archivio di monitoraggio usato da Skype for Business Server.
  
In Skype for Business Server i dati di monitoraggio possono essere raccolti solo nei pool Front-End associati a un archivio di monitoraggio, un'attività eseguita in genere quando si definisce un pool Front-end in Generatore di topologie.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Associare un archivio di monitoraggio a un pool Front-End

 Per associare un archivio di monitoraggio a un nuovo pool Front-End, verificare di aver selezionato il **monitoraggio delle opzioni (registrazione dei dettagli delle chiamate e registrazione delle metriche di qualità delle esperienze)** nella pagina **selezionare le caratteristiche** della procedura guidata per definire il nuovo pool Front-end. Si noti che, se si seleziona questa opzione, è necessario specificare anche un archivio SQL per completare la procedura guidata. Tuttavia, questo archivio non deve esistere quando si esegue la procedura guidata. Questo significa che puoi prima associare un pool a un archivio di monitoraggio, quindi installarlo e configurarlo in seguito.
  
In alternativa, è possibile associare un pool Front end esistente a un archivio di monitoraggio nuovo o diverso completando la procedura seguente:
  
1. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi fare clic su **Generatore di topologia di Skype for Business Server**.
    
2. Nella finestra di dialogo **Generatore di topologia** selezionare **Scarica topologia da distribuzione esistente** e quindi fare clic su **OK**.
    
3. Nella finestra di dialogo **Salva con** nome immettere un file per la topologia corrente e quindi fare clic su **Salva**. La topologia salvata può in seguito essere recuperata e ripubblicata in caso di problemi con la nuova topologia.
    
4. In Generatore di topologie espandere **Skype for Business Server**, espandere il nome del sito contenente il pool Front-End, quindi fare clic su Espandi **pool di front-end Enterprise Edition**.
    
5. Fare clic con il pulsante destro del mouse sul nome del pool da associare all'archivio di monitoraggio e quindi scegliere **modifica proprietà**.
    
6. Nella scheda **generale** della finestra di dialogo **modifica proprietà** selezionare l'opzione **monitoraggio (CdR e QoE Metrics)** e quindi selezionare un database di SQL Server esistente nell'elenco a discesa **monitoraggio di SQL Server Store** . In alternativa, fare clic su **nuovo** per associare il pool a un nuovo archivio di database. Se si sceglie di usare un nuovo archivio di database, nella finestra di dialogo **Definisci nuovo archivio SQL** immettere il nome di dominio completo del computer SQL Server nella casella **FQDN di SQL Server** . Se si vuole usare l'istanza predefinita di SQL Server per lo Store, selezionare **istanza predefinita**. in caso contrario, seleziona **istanza denominata** e immetti il nome dell'istanza nella casella **istanza denominata** .
    
    La finestra di dialogo **modifica proprietà** offre anche la possibilità di creare un mirror SQL per il database di monitoraggio (un mirror SQL consente di gestire due copie del database di monitoraggio, una copia archiviata nel computer dell'archivio di monitoraggio e l'altra nel computer SQL mirror). Per abilitare il mirroring, selezionare T **la relativa istanza SQL è in relazione di mirroring** e immettere il numero di porta per il server mirror nella casella **numero porta di mirroring** .
    
7. Nella finestra di dialogo **modifica proprietà** fare clic su **OK**.
    
Dopo aver associato l'archivio di monitoraggio con un pool Front-End, è necessario pubblicare la nuova topologia prima che le modifiche abbiano effetto. Per pubblicare la nuova topologia, completare i passaggi seguenti in Generatore di topologie:
  
1. Fare clic su **azione**, scegliere **topologia**e quindi fare clic su **pubblica**.
    
2. Nella pagina **Pubblica topologia** della procedura guidata Pubblica topologia fare clic su **Avanti**.
    
3. Nella pagina **completamento pubblicazione guidata** fare clic su **fine**.
    
Una volta pubblicata la topologia, è possibile installare il database di monitoraggio nel computer che ospiterà l'archivio di monitoraggio. Il database di monitoraggio può essere installato usando Skype for Business Server Management Shell e Windows PowerShell. Per installare il database in locale (ovvero, per installare il database nello stesso computer in cui è in uso Skype for Business Server Management Shell), avviare Gestione Shell nel computer appropriato, quindi digitare il comando seguente e premere INVIO:
  
```powershell
Install-CsDatabase -LocalDatabases
```

Quando si esegue il comando precedente, Install-CsDatabase leggerà la topologia di Skype for Business Server corrente, determina quali database devono essere installati nel computer locale e quindi installa e configura automaticamente ognuno di questi database.
  
Per installare il database in un computer remoto, ovvero un computer diverso dal computer in cui è in uso la shell di gestione, è necessario includere almeno due parametri: il parametro ConfiguredDatabases e il parametro SqlServerFqdn. Questi parametri indicano al cmdlet Install-CsDatabase di recuperare la topologia di Skype for Business Server e quindi installare e configurare i database necessari nel computer specificato dal parametro SqlServerFqdn. Il parametro SqlServerFqdn deve usare un valore di parametro che rappresenta il nome di dominio completo del computer in cui devono essere installati i database.
  
Questo comando, ad esempio, installa il database di monitoraggio nel computer atl-sql-001.litwareinc.com:
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

In alternativa, puoi installare il database di monitoraggio eseguendo la distribuzione guidata di Skype for Business Server nel computer che ospiterà l'archivio di monitoraggio. A questo scopo, accedere al computer appropriato e completare la procedura seguente:
  
1. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi fare clic su **Skype for Business Server Deployment Wizard**.
    
2. Nella distribuzione guidata fare clic su **Installa o Aggiorna sistema di Skype for Business Server**.
    
3. Nella pagina **Distribuisci** , in **passaggio 2: configurare o rimuovere i componenti di Skype for Business Server**, fare di nuovo clic su **Esegui**.
    
4. Nella pagina Configurazione dei componenti di Skype for Business Server fare clic su **Avanti**nella pagina **Configurazione componenti di Skype for Business Server** .
    
5. Nella pagina **specifica il percorso di MSI** Digitare il percorso del file OCSCore. msi (un file incluso nel supporto di installazione di Skype for Business Server) e quindi fare clic su **Avanti**.
    
6. Nella pagina **esecuzione dei comandi** fare clic su **fine**.
    
Per assicurarsi che tutti i servizi richiesti di Skype for Business Server siano già stati avviati, fare clic su **Esegui** sotto il titolo **passaggio 4: avviare i servizi** nella pagina **Distribuisci**
  

