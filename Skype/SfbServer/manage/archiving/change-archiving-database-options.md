---
title: Modificare le opzioni di archiviazione del database in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Riepilogo: informazioni su come modificare le opzioni di archiviazione del database per Skype for Business Server.'
ms.openlocfilehash: 56aa29ef185176ce3b080572723c566455731dc4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195115"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Modificare le opzioni di archiviazione del database in Skype for Business Server

**Riepilogo:** Informazioni su come modificare le opzioni di archiviazione del database per Skype for Business Server.
  
Se si distribuisce l'archiviazione con l'archiviazione di SQL Server per l'archiviazione dello spazio di archiviazione per tutti gli utenti, è possibile apportare le modifiche seguenti dello spazio di archiviazione del database:
  
- Usare un database SQL Server diverso per l'archiviazione dello spazio di archiviazione. Questo include il database di archiviazione principale e qualsiasi database usato per il mirroring di SQL Server.
    
- Passare all'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server di Exchange. Se tutti gli utenti sono ospitati nei server Exchange e si vuole usare lo spazio di archiviazione di Microsoft Exchange per tutti gli utenti della distribuzione, è consigliabile rimuovere i database di SQL Server Store dalla topologia. 
    
Per apportare una di queste modifiche, è necessario eseguire Generatore di topologie, apportare le modifiche e quindi pubblicare di nuovo la topologia. Non specificare l' **archiviazione di SQL Server Store** o abilitare le informazioni di mirroring di **SQL Server Store** , a meno che tu non abbia utenti di Skype for business non residenti nei server di Exchange.
  
## <a name="change-archiving-database-options"></a>Modificare le opzioni del database di archiviazione

1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere utilizzando un account membro del gruppo utenti locali o un account con diritti utente equivalenti.
    
    > [!NOTE]
    > Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un componente alla topologia, devi usare un account membro del gruppo **Domain Admins** e **RTCUniversalSer gruppo verAdmins** , con autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) nella condivisione file in uso per l'archivio file di Skype for Business Server, in modo che il generatore di topologia possa configurare il controllo di accesso discrezionale richiesto elenchi (DACL) o un account con diritti equivalenti.
  
2. Avviare Generatore di topologie.
    
3. Nell'albero della console passare al pool Front-end in cui è stata distribuita l'archiviazione e quindi fare clic sul nome del pool Front-end in cui si vogliono modificare le opzioni del database.
    
4. Nel menu **azione** fare clic su **modifica proprietà**. 
    
5. Nella finestra di dialogo **modifica proprietà** fare clic su **generale**.
    
6. Scorrere verso il basso fino all' **archiviazione**.
    
7. In **archiviazione**eseguire le operazioni seguenti:
    
   - Per passare a un altro archivio di SQL Server esistente, nella casella di riepilogo a discesa, in **archiviazione SQL Server Store**, eseguire le operazioni seguenti:
    
   - Per usare un archivio di SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio di SQL Server che si vuole usare.
    
   - Per specificare un nuovo archivio di SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:
    
     - Per usare un archivio di SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio di SQL Server che si vuole usare.
    
     - Per specificare un nuovo archivio di SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:
    
       - In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo archivio di SQL Server.
    
       - Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.
    
       - Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.
    
   - Per aggiungere SQL Server Store per il mirroring o passare a un altro archivio di SQL Server esistente per il mirroring di SQL Server Store, selezionare **Abilita mirroring di SQL Server Store**e quindi eseguire le operazioni seguenti:
    
     - Per usare un archivio di SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **archiviazione di SQL Server dell'archivio** , fare clic sul nome dell'archivio di SQL Server che si vuole usare per il mirroring.
    
     - Per specificare un nuovo archivio di SQL Server per il mirroring, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio di SQL Server** eseguire una delle operazioni seguenti:
    
       un. In **FQDN di SQL Server**specificare il nome di dominio completo di SQL Server in cui si vuole creare il nuovo archivio di SQL Server.
    
       b. Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.
    
       c. Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.
    
   - Se si Abilita il mirroring di SQL Server e si vuole aggiungere o modificare un witness di mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità delle istanze di SQL Server e mirror principali), selezionare l' **uso del witness di SQL Server mirroring per abilitare** la casella di controllo failover automatico e quindi eseguire una delle operazioni seguenti:
    
      un. In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo witness di mirroring di SQL Server.
    
      b. Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare per il witness di mirroring.
    
      c. Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.
    
   - Per passare all'integrazione di Microsoft Exchange per archiviare dati e file di archiviazione nei server di Exchange (se tutti gli utenti della distribuzione sono ospitati nei server Exchange), eliminare tutte le informazioni per l'archiviazione dei database.
    
     > [!IMPORTANT]
     > Se gli utenti di Skype for business non sono residenti nei server di Exchange, non eliminare le informazioni di SQL Server Store. 
  
8. Per salvare la configurazione, fare clic su **OK**.
    
    > [!IMPORTANT]
    > Le modifiche apportate in Generatore di topologie non hanno effetto finché non viene pubblicata la nuova topologia. Per informazioni dettagliate, vedere [aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Modificare la posizione del database di archiviazione tramite Windows PowerShell

Nella maggior parte dei casi non è necessario modificare la posizione del database di archiviazione, che viene specificato durante l'installazione del server di archiviazione. Tuttavia, se si verifica un errore hardware o un altro problema, è possibile puntare il server di archiviazione in un nuovo database usando il cmdlet **Set-CsArchivingServer** .
  
Nell'esempio seguente viene modificata la posizione del database di archiviazione per il server di archiviazione ArchivingServer: atl-cs-001.contoso.com. In questo esempio il nuovo database si trova in ArchivingDatabase: ATL-SQL-001.contoso.com:
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


