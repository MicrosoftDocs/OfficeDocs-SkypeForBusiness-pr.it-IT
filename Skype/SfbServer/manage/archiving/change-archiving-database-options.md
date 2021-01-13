---
title: Modificare le opzioni del database di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Riepilogo: informazioni su come modificare le opzioni del database di archiviazione per Skype for Business Server.'
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817696"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Modificare le opzioni del database di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come modificare le opzioni del database di archiviazione per Skype for Business Server.
  
Se si distribuisce l'archiviazione utilizzando l'archiviazione di SQL Server per l'archiviazione di un utente, è possibile apportare le modifiche apportate ai database seguenti:
  
- Utilizzare un database di SQL Server diverso per l'archiviazione. Sono inclusi il database di archiviazione principale e qualsiasi database utilizzato per il mirroring di SQL Server.
    
- Passare all'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file nei server di Exchange. Se tutti gli utenti sono ospitati nei server Exchange e si desidera utilizzare lo spazio di archiviazione di Microsoft Exchange per tutti gli utenti nella distribuzione, è necessario rimuovere i database dell'archivio SQL Server dalla topologia. 
    
Per apportare una o più di queste modifiche, è necessario eseguire Generatore di topologie, apportare le modifiche e quindi ripubblicare la topologia. Non specificare l' **Archivio SQL Server di archiviazione** o abilitare le informazioni sul **mirroring dell'archivio SQL Server** , a meno che non si disponga di utenti Skype for business che non sono ospitati nei server Exchange.
  
## <a name="change-archiving-database-options"></a>Modificare le opzioni dei database di archiviazione

1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).
    
    > [!NOTE]
    > È possibile definire una topologia utilizzando un account membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un componente alla topologia, è necessario utilizzare un account membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** . e che dispone di autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) sulla condivisione file utilizzata per l'archivio file di Skype for Business Server (ovvero, in modo che generatore di topologie possa configurare gli elenchi di controllo di accesso discrezionale necessari o un account con diritti equivalenti.
  
2. Avviare Generatore di topologie.
    
3. Nell'albero della console accedere al pool Front End in cui è stata distribuita Archiviazione e fare clic sul nome del pool Front End in cui si vuole modificare le opzioni di database.
    
4. Nel menu **Azione** fare clic su **Modifica proprietà**. 
    
5. Nella finestra di dialogo **Modifica proprietà** fare clic su **Generale**.
    
6. Scorrere verso il basso fino ad **Archiviazione**.
    
7. In **Archiviazione** seguire questa procedura:
    
   - Per passare a un archivio SQL Server esistente diverso, nella casella di riepilogo a discesa in **Archivio SQL Server archiviazione** seguire la procedura seguente:
    
   - Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare.
    
   - Per specificare un nuovo archivio SQL Server, fare clic su **Nuovo**, quindi nella finestra di dialogo **Definire un nuovo archivio SQL Server** seguire questa procedura:
    
     - Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare.
    
     - Per specificare un nuovo archivio SQL Server, fare clic su **nuovo** e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:
    
       - In **FQDN SQL Server** specificare il nome di dominio completo del server in cui si desidera creare il nuovo archivio SQL Server.
    
       - Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.
    
       - Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.
    
   - Per aggiungere l'archivio SQL Server per il mirroring o passare a un archivio SQL Server esistente diverso per il mirroring dell'archivio SQL Server, selezionare **Abilita mirroring dell'archivio SQL Server**, quindi procedere come segue:
    
     - Per utilizzare un archivio SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **mirror archivio SQL Server archiviazione** fare clic sul nome dell'archivio SQL Server che si desidera utilizzare per il mirroring.
    
     - Per specificare un nuovo archivio SQL Server per il mirroring, fare clic su **nuovo** e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire una delle operazioni seguenti:
    
       a. In **FQDN SQL Server** specificare il nome di dominio completo di SQL Server in cui si desidera creare il nuovo archivio SQL Server.
    
       b. Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.
    
       c. Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.
    
   - Se si Abilita il mirroring di SQL Server e si desidera aggiungere o modificare un controllo del mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità del server SQL Server primario e delle istanze di mirroring), selezionare la casella utilizza verifica del **mirroring di SQL Server per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:
    
      a. In **FQDN SQL Server** specificare il nome di dominio completo del server in cui si desidera creare il nuovo controllo del mirroring di SQL Server.
    
      b. Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare per il controllo di mirroring.
    
      c. Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.
    
   - Per passare all'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file nei server di Exchange (se tutti gli utenti della distribuzione sono ospitati nei server Exchange), eliminare tutte le informazioni per i database di archiviazione.
    
     > [!IMPORTANT]
     > Se gli utenti di Skype for business non sono ospitati nei server di Exchange, non eliminare le informazioni sull'archivio SQL Server. 
  
8. Per salvare la configurazione, fare clic su **OK**.
    
    > [!IMPORTANT]
    > Le modifiche apportate in Generatore di topologie non sono effettive finché non si pubblica la nuova topologia. Per ulteriori informazioni, vedere [aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Modificare il percorso del database di archiviazione utilizzando Windows PowerShell

Nella maggior parte dei casi, non è necessario modificare il percorso del database di archiviazione, che viene specificato durante l'installazione del server di archiviazione. Tuttavia, se si verifica un errore hardware o un altro problema, è possibile fare in modo che il server di archiviazione punti a un nuovo database utilizzando il cmdlet **Set-CsArchivingServer** .
  
Nell'esempio seguente viene modificata la posizione del database di archiviazione per il server di archiviazione ArchivingServer: atl-cs-001.contoso.com. In questo esempio, il nuovo database si trova in ArchivingDatabase: ATL-SQL-001.contoso.com:
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


