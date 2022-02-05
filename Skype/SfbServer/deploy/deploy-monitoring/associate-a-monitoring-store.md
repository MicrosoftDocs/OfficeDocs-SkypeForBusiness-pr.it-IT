---
title: Associare un archivio di monitoraggio a un pool Front End in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Riepilogo: informazioni su come associare pool Front End a un archivio di monitoraggio utilizzato da Skype for Business Server.'
---

# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Associare un archivio di monitoraggio a un pool Front End in Skype for Business Server 
**Riepilogo:** Informazioni su come associare pool Front End a un archivio di monitoraggio utilizzato da Skype for Business Server.
  
In Skype for Business Server, i dati di monitoraggio possono essere raccolti solo nei pool Front End associati a un archivio di monitoraggio, un'attività in genere eseguita quando si definisce un pool Front End in Generatore di topologie.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Associare un archivio di monitoraggio a un pool Front End

 Per associare un archivio di monitoraggio a un nuovo pool Front End, selezionare l'opzione Monitoraggio **(** registrazione dettagli chiamata e registrazione delle metriche di qualità dell'esperienza) nella  pagina Selezione funzionalità della procedura guidata Definisci nuovo pool Front End. Si noti che, se si seleziona questa opzione, è necessario specificare anche un archivio di SQL per completare la procedura guidata. Tuttavia, questo archivio non deve esistere al momento dell'esecuzione della procedura guidata. Ciò significa che è possibile prima associare un pool a un archivio di monitoraggio, quindi configurare e configurare l'archivio in un secondo momento.
  
In alternativa, è possibile associare un pool Front End esistente a un archivio di monitoraggio nuovo o diverso eseguendo la procedura seguente:
  
1. Fare **clic sul pulsante Start**, **scegliere** Tutti i programmi, **Skype for Business Server 2015** e quindi fare clic Skype for Business Server **Generatore di topologie**.
    
2. Nella finestra di dialogo **Generatore di topologie** selezionare **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **OK**.
    
3. Nella finestra di dialogo **Salva con nome** immettere un nome file per la topologia corrente e quindi fare clic su **Salva**. La topologia salvata può essere successivamente recuperata e ripubblicata in caso di problemi con la nuova topologia.
    
4. In Generatore di topologie espandere **Skype for Business Server**, espandere il nome del sito contenente il pool Front End, quindi fare clic su edizione Enterprise **pool Front End**.
    
5. Fare clic con il pulsante destro del mouse sul nome del pool da associare all'archivio di monitoraggio e quindi scegliere **Modifica proprietà**.
    
6. Nella finestra di dialogo **Modifica proprietà** nella scheda **Generale** selezionare l'opzione **Monitoraggio (registrazione dettagli chiamata e registrazione metrica QoE** e quindi selezionare un database di SQL Server esistente nell'elenco a discesa **Archivio SQL Server monitoraggio**. In alternativa, fare clic su **Nuovo** per associare il pool a un nuovo archivio database. Se si sceglie di utilizzare il nuovo archivio database, nella finestra di dialogo **Definisci nuovo archivio SQL** immettere il nome di dominio completo del computer SQL Server nella casella **FQDN SQL Server**. Se si desidera utilizzare l'istanza di SQL Server predefinita per l'archivio, selezionare **Istanza predefinita**, altrimenti selezionare **Istanza denominata** e immettere il nome dell'istanza nella casella **Istanza denominata**.
    
    La  finestra di dialogo Modifica proprietà consente inoltre di creare un mirror di SQL per il database di monitoraggio(un mirror SQL consente di gestire due copie del database di monitoraggio, una copia archiviata nel computer dell'archivio di monitoraggio e l'altra nel computer mirror di SQL). Per abilitare il mirroring, selezionare T **la sua SQL è in relazione di mirroring** e immettere il numero di porta per il server mirror nella casella **Numero porta mirroring**.
    
7. Nella finestra di dialogo **Modifica proprietà** fare clic su **OK**.
    
Dopo aver associato l'archivio di monitoraggio a un pool Front End, è necessario pubblicare la nuova topologia per rendere effettive le modifiche. A tale scopo, eseguire le operazioni seguenti in Generatore di topologie:
  
1. Fare clic su **Azione**, scegliere **Topologia** e quindi **Pubblica**.
    
2. Nella pagina **Pubblicare la topologia** della procedura guidata Pubblica topologia fare clic su **Avanti**.
    
3. Nella pagina **Pubblicazione guidata completata** fare clic su **Fine**.
    
Dopo la pubblicazione della topologia, è possibile installare il database di monitoraggio nel computer che ospiterà l'archivio di monitoraggio. Il database di monitoraggio può essere installato utilizzando Skype for Business Server Management Shell e Windows PowerShell. Per installare il database in locale, ovvero per installare il database nello stesso computer in cui si esegue Skype for Business Server Management Shell, avviare Management Shell nel computer appropriato, quindi digitare il comando seguente e premere INVIO:
  
```powershell
Install-CsDatabase -LocalDatabases
```

Quando si esegue il comando precedente, Install-CsDatabase leggerà la topologia Skype for Business Server corrente, determinerà quali database devono essere installati nel computer locale e quindi installerà e configurerà automaticamente ognuno di questi database.
  
Per installare il database in un computer remoto, ovvero un computer diverso da quello in cui è in esecuzione Management Shell, è necessario includere almeno due parametri: ConfiguredDatabases e SqlServerFqdn. Questi parametri specificano al cmdlet Install-CsDatabase di recuperare la topologia Skype for Business Server e quindi installare e configurare i database necessari nel computer specificato dal parametro SqlServerFqdn. Il parametro SqlServerFqdn deve utilizzare un valore di parametro che rappresenta il nome di dominio completo del computer in cui devono essere installati i database.
  
Con il comando seguente ad esempio il database di monitoraggio viene installato nel computer atl-sql-001.litwareinc.com:
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

In alternativa, è possibile installare il database di monitoraggio eseguendo Skype for Business Server distribuzione guidata nel computer che ospiterà l'archivio di monitoraggio. A tale scopo, accedere al computer appropriato ed eseguire la procedura seguente:
  
1. Fare **clic sul pulsante Start**, **scegliere** Tutti i programmi, **Skype for Business Server 2015** e quindi fare clic Skype for Business Server **distribuzione guidata**.
    
2. Nella Distribuzione guidata fare clic **su Installa o aggiorna Skype for Business Server sistema**.
    
3. Nella pagina **Distribuisci**, in **Passaggio 2:** Installazione o rimozione Skype for Business Server componenti, fare clic su **Esegui di nuovo**.
    
4. Nella pagina Installazione Skype for Business Server componenti del programma di installazione fare clic su **Avanti** nella pagina Installazione **Skype for Business Server componenti**.
    
5. Nella pagina **Specificare il percorso degli elementi MSI digitare** il percorso del file Ocscore.msi (un file incluso nel supporto di installazione Skype for Business Server) e quindi fare clic su **Avanti**.
    
6. Nella pagina **Esecuzione comandi in corso** fare clic su **Fine**.
    
Per verificare che tutti i servizi Skype for Business Server necessari siano stati avviati, fare clic su **Esegui** sotto l'intestazione **Passaggio 4: Avviare** i servizi nella **pagina** Distribuisci
  

