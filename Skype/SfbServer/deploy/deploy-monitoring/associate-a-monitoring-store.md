---
title: Associare un archivio di monitoraggio a un pool Front end in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Riepilogo: informazioni su come associare pool Front end a un archivio di monitoraggio utilizzato da Skype for Business Server.'
ms.openlocfilehash: 4ec48e99da9a827cdc40d87c42ec764bda66a416
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830546"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Associare un archivio di monitoraggio a un pool Front end in Skype for Business Server 
**Riepilogo:** Informazioni su come associare pool Front end a un archivio di monitoraggio utilizzato da Skype for Business Server.
  
In Skype for Business Server, i dati di monitoraggio possono essere raccolti solo nei pool Front end che sono stati associati a un archivio di monitoraggio, un'attività in genere eseguita quando si definisce un pool Front end in Generatore di topologie.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Associare un archivio di monitoraggio a un pool Front End

 Per associare un archivio di monitoraggio a un nuovo pool Front End, è necessario selezionare l'opzione **monitoraggio (registrazione dettagli chiamata e registrazione delle metriche sulla qualità delle esperienze)** nella pagina **Seleziona funzionalità** della procedura guidata Definisci nuovo pool Front end. Si noti che, se si seleziona questa opzione, è necessario specificare anche un archivio SQL per completare la procedura guidata. Tuttavia, questo archivio non deve esistere nel momento in cui viene eseguita la procedura guidata. Questo significa che è possibile associare un pool a un archivio di monitoraggio, quindi installarlo e configurarlo in un secondo momento.
  
In alternativa, è possibile associare un pool Front End esistente a un archivio di monitoraggio nuovo o diverso eseguendo la procedura seguente:
  
1. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015** e quindi su **Generatore di topologie di Skype for Business Server**.
    
2. Nella finestra di dialogo **Generatore di topologie** selezionare **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **OK**.
    
3. Nella finestra di dialogo **Salva con nome** immettere un nome file per la topologia corrente e quindi fare clic su **Salva**. La topologia salvata può essere successivamente recuperata e ripubblicata in caso di problemi con la nuova topologia.
    
4. In Generatore di topologie espandere **Skype for Business Server**, espandere il nome del sito contenente il pool Front end e quindi fare clic su Espandi **pool Enterprise Edition front end**.
    
5. Fare clic con il pulsante destro del mouse sul nome del pool da associare all'archivio di monitoraggio e quindi scegliere **Modifica proprietà**.
    
6. Nella finestra di dialogo **Modifica proprietà** nella scheda **Generale** selezionare l'opzione **Monitoraggio (registrazione dettagli chiamata e registrazione metrica QoE** e quindi selezionare un database di SQL Server esistente nell'elenco a discesa **Archivio SQL Server monitoraggio**. In alternativa, fare clic su **Nuovo** per associare il pool a un nuovo archivio database. Se si sceglie di utilizzare il nuovo archivio database, nella finestra di dialogo **Definisci nuovo archivio SQL** immettere il nome di dominio completo del computer SQL Server nella casella **FQDN SQL Server**. Se si desidera utilizzare l'istanza di SQL Server predefinita per l'archivio, selezionare **Istanza predefinita**, altrimenti selezionare **Istanza denominata** e immettere il nome dell'istanza nella casella **Istanza denominata**.
    
    Nella finestra di dialogo **modifica proprietà** viene inoltre fornita la possibilità di creare un mirror SQL per il database di monitoraggio (un mirror SQL consente di gestire due copie del database di monitoraggio, una copia archiviata nel computer archivio di monitoraggio e l'altra nel computer mirror SQL). Per abilitare il mirroring, selezionare T **la propria istanza di SQL è in relazione di mirroring** e immettere il numero di porta del server mirror nella casella **numero porta di mirroring** .
    
7. Nella finestra di dialogo **Modifica proprietà** fare clic su **OK**.
    
Dopo aver associato l'archivio di monitoraggio a un pool Front End, è necessario pubblicare la nuova topologia per rendere effettive le modifiche. A tale scopo, eseguire le operazioni seguenti in Generatore di topologie:
  
1. Fare clic su **Azione**, scegliere **Topologia** e quindi **Pubblica**.
    
2. Nella pagina **Pubblicare la topologia** della procedura guidata Pubblica topologia fare clic su **Avanti**.
    
3. Nella pagina **Pubblicazione guidata completata** fare clic su **Fine**.
    
Dopo la pubblicazione della topologia, è possibile installare il database di monitoraggio nel computer che ospiterà l'archivio di monitoraggio. È possibile installare il database di monitoraggio utilizzando Skype for Business Server Management Shell e Windows PowerShell. Per installare il database localmente, ovvero per installare il database nello stesso computer in cui si esegue Skype for Business Server Management Shell, avviare la shell di gestione nel computer appropriato e quindi digitare il comando seguente e premere INVIO:
  
```powershell
Install-CsDatabase -LocalDatabases
```

Quando si esegue il comando precedente, Install-CsDatabase leggerà la topologia di Skype for Business Server corrente, stabilire quali database devono essere installati nel computer locale e quindi installare e configurare automaticamente ognuno di questi database.
  
Per installare il database in un computer remoto, ovvero un computer diverso da quello in cui è in esecuzione Management Shell, è necessario includere almeno due parametri: ConfiguredDatabases e SqlServerFqdn. Questi parametri indicano al cmdlet Install-CsDatabase di recuperare la topologia di Skype for Business Server e quindi installano e configurano i database necessari nel computer specificato dal parametro SqlServerFqdn. Il parametro SqlServerFqdn deve utilizzare un valore di parametro che rappresenta il nome di dominio completo del computer in cui devono essere installati i database.
  
Con il comando seguente ad esempio il database di monitoraggio viene installato nel computer atl-sql-001.litwareinc.com:
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

In alternativa, è possibile installare il database di monitoraggio eseguendo la distribuzione guidata di Skype for Business Server nel computer che ospiterà l'archivio di monitoraggio. A tale scopo, accedere al computer appropriato ed eseguire la procedura seguente:
  
1. Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015** e quindi fare clic su **Skype for Business Server Deployment Wizard**.
    
2. Nella distribuzione guidata, fare clic su **Installa o aggiorna il sistema di Skype for Business Server**.
    
3. Nella pagina **Distribuisci** , in **passaggio 2: installazione o rimozione componenti di Skype for Business Server**, fare clic su **Riesegui**.
    
4. Nell'installazione guidata componenti di Skype for Business Server, nella pagina **Installazione componenti di Skype for Business Server** fare clic su **Avanti**.
    
5. Nella pagina **Specifica percorso di MSI** Digitare il percorso del file Ocscore.msi (un file incluso nel supporto di installazione di Skype for Business Server) e quindi fare clic su **Avanti**.
    
6. Nella pagina **Esecuzione comandi in corso** fare clic su **Fine**.
    
Per assicurarsi che tutti i servizi richiesti di Skype for Business Server siano stati avviati, fare clic su **Esegui** sotto il titolo **passaggio 4: avviare i servizi** nella pagina **Distribuisci** .
  

