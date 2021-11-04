---
title: Modificare le opzioni del database di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Riepilogo: informazioni su come modificare le opzioni del database di archiviazione per Skype for Business Server.'
ms.openlocfilehash: 240d590b7f22e4756351939be6ecab55ea108b79
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767934"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>Modificare le opzioni del database di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come modificare le opzioni del database di archiviazione per Skype for Business Server.
  
Se si distribuisce l'archiviazione SQL Server per l'archiviazione per qualsiasi utente, è possibile apportare le modifiche seguenti all'archiviazione del database:
  
- Utilizzare un database di SQL Server diverso per l'archiviazione. Sono inclusi il database di archiviazione primario e qualsiasi database utilizzato per SQL Server mirroring.
    
- Passare all'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione Exchange server. Se tutti gli utenti sono ospitati nei server Exchange e si desidera utilizzare l'archiviazione di Microsoft Exchange per tutti gli utenti della distribuzione, è consigliabile rimuovere i database dell'archivio SQL Server dalla topologia. 
    
Per apportare una di queste modifiche, è necessario eseguire Generatore di topologie, apportare le modifiche e quindi pubblicare di nuovo la topologia. Non specificare Archivio **SQL Server** archiviazione o Abilita SQL Server archiviare le informazioni di **mirroring, a** meno che non siano presenti utenti Skype for Business non ospitati in Exchange server.
  
## <a name="change-archiving-database-options"></a>Modificare le opzioni dei database di archiviazione

1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere utilizzando un account membro del gruppo Users locale (o un account con diritti utente equivalenti).
    
    > [!NOTE]
    > È possibile definire una topologia utilizzando un account membro del gruppo Users locale, ma per pubblicare una topologia, necessaria per aggiungere un componente alla topologia, è necessario utilizzare un account membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** e che dispone delle autorizzazioni di controllo completo, ovvero  lettura, scrittura e modifica) nella condivisione file in uso per l'archivio file di Skype for Business Server, ovvero in modo che Generatore di topologie possa configurare gli elenchi di controllo di accesso discrezionale (DACL) necessari o un account con diritti equivalenti.
  
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
    
     - Per specificare un nuovo SQL Server store, fare clic su **Nuovo** e quindi nella finestra di dialogo Definisci nuovo **SQL Server Store** eseguire le operazioni seguenti:
    
       - In **SQL Server FQDN** specificare il nome di dominio completo del server in cui si desidera creare il nuovo SQL Server archivio.
    
       - Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.
    
       - Se l'istanza SQL Server specificata si trova in una relazione di mirroring, selezionare la casella di controllo Questa istanza di SQL è in relazione **di mirroring** e quindi, in **Numero** porta mirror, specificare il numero di porta.
    
   - Per aggiungere l'archivio SQL Server per il mirroring o passare a un archivio SQL Server esistente diverso per il mirroring dell'archivio SQL Server, selezionare **Abilita mirroring dell'archivio SQL Server**, quindi procedere come segue:
    
     - Per utilizzare un archivio SQL Server esistente per il mirroring, nella casella di riepilogo a discesa Mirror archivio **SQL Server** archiviazione fare clic sul nome dell'archivio SQL Server che si desidera utilizzare per il mirroring.
    
     - Per specificare un nuovo archivio SQL Server per il mirroring, fare clic su **Nuovo** e quindi nella finestra di dialogo Definisci nuovo **SQL Server Store** eseguire una delle operazioni seguenti:
    
       a. In **SQL Server FQDN** specificare il nome di dominio completo del SQL Server in cui si desidera creare il nuovo SQL Server archivio.
    
       b. Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.
    
       c. Se l'istanza SQL Server specificata si trova in una relazione di mirroring, selezionare la casella di controllo Questa istanza di SQL è in relazione **di mirroring** e quindi, in **Numero** porta mirror, specificare il numero di porta.
    
   - Se si abilita il mirroring SQL Server e si desidera aggiungere o modificare un controllo del mirroring di SQL Server (una terza istanza separata di SQL Server in grado di rilevare l'integrità del server SQL Server primario e delle istanze mirror), selezionare la casella di controllo Usa **controllo del mirroring** di SQL Server per abilitare il failover automatico e quindi  eseguire una delle operazioni seguenti:
    
      a. In **SQL Server FQDN** specificare il nome di dominio completo del server in cui si desidera creare il nuovo SQL Server di mirroring.
    
      b. Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare per il controllo di mirroring.
    
      c. Se l'istanza SQL Server specificata si trova in una relazione di mirroring, selezionare la casella di controllo Questa istanza di SQL è in relazione **di mirroring** e quindi, in **Numero** porta mirror, specificare il numero di porta.
    
   - Per passare all'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server Exchange (se tutti gli utenti della distribuzione sono ospitati nei server Exchange), eliminare tutte le informazioni per i database di archiviazione.
    
     > [!IMPORTANT]
     > Se sono presenti utenti Skype for Business non ospitati nei server Exchange, non eliminare le informazioni SQL Server archivio. 
  
8. Per salvare la configurazione, fare clic su **OK**.
    
    > [!IMPORTANT]
    > Le modifiche apportate in Generatore di topologie non vengono applicate fino a quando non si pubblica la nuova topologia. Per informazioni dettagliate, vedere [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md). 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>Modificare il percorso del database di archiviazione utilizzando Windows PowerShell

Nella maggior parte dei casi non è necessario modificare il percorso del database di archiviazione, specificato quando si installa il server di archiviazione. Tuttavia, se si verifica un errore hardware o un altro problema, è possibile puntare il server di archiviazione a un nuovo database utilizzando il cmdlet **Set-CsArchivingServer.**
  
Nell'esempio seguente viene modificato il percorso del database di archiviazione per il server di archiviazione ArchivingServer:atl-cs-001.contoso.com Archiving Server. In questo esempio il nuovo database si trova in ArchivingDatabase:atl-sql-001.contoso.com:
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


