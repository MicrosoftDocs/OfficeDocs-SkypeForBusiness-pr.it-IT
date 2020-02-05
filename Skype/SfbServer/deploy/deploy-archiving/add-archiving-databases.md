---
title: Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Riepilogo: leggere questo argomento per informazioni su come aggiungere database di archiviazione alla distribuzione di Skype for Business Server.'
ms.openlocfilehash: 26cdd1befb695fbaf0656611ed65c7afa778af6c
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769049"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come aggiungere database di archiviazione alla distribuzione di Skype for Business Server.
  
È necessario incorporare l'archiviazione nella topologia prima di poter configurare la distribuzione per supportare l'archiviazione. Le informazioni contenute in questo argomento spiegano come usare generatore di topologia per:
  
- Aggiungere un database di archiviazione alla topologia.
    
- Pubblicare la topologia aggiornata per aggiungere il database di archiviazione alla distribuzione di Skype for Business Server.
    
> [!NOTE]
> Se si vuole usare l'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server di Exchange per tutti gli utenti della distribuzione, non specificare l' **archiviazione di SQL Server Store** o usare le informazioni di **mirroring di SQL Server Store** .
  
### <a name="add-an-archiving-database-to-your-topology"></a>Aggiungere un database di archiviazione alla topologia

1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere utilizzando un account membro del gruppo utenti locali o un account con diritti utente equivalenti.
    
2. Avviare Generatore di topologie.
    
3. Nell'albero della console passare al pool Front-end in cui si vuole distribuire l'archiviazione e quindi fare clic sul nome del pool Front end in cui si vuole distribuire l'archiviazione.
    
4. Nel menu **azione** fare clic su **modifica proprietà**. 
    
5. Nella finestra di dialogo **modifica proprietà** fare clic su **generale**.
    
6. Scorrere verso il basso fino all' **archiviazione**.
    
7. Selezionare la casella di controllo **archiviazione** .
    
8. In **archiviazione SQL Server Store** eseguire una delle operazioni seguenti:
    
   - Per usare un archivio di SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio di SQL Server che si vuole usare. Se tutti gli utenti sono ospitati in Microsoft Exchange Server 2013 o versioni successive, è possibile archiviare le comunicazioni Skype for business per tutti gli utenti in Exchange. In questo caso, non è necessario configurare l'archivio di archiviazione di SQL Server.
    
   - Per specificare un nuovo archivio di SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:
    
   - In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo archivio di SQL Server.
    
   - Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.
    
   - Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.
    
9. Se si vuole usare il mirroring di SQL Server Store, selezionare **Abilita mirroring di SQL Server Store**e quindi eseguire le operazioni seguenti:
    
   - Per usare un archivio di SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **archiviazione di SQL Server dell'archivio** , fare clic sul nome dell'archivio di SQL Server che si vuole usare per il mirroring.
    
   - Per specificare un nuovo archivio di SQL Server per il mirroring, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio di SQL Server** eseguire una delle operazioni seguenti:
    
     un. In **FQDN di SQL Server**specificare il nome di dominio completo di SQL Server in cui si vuole creare il nuovo archivio di SQL Server.
    
     b. Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.
    
     c. Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.
    
   - Se si Abilita il mirroring di SQL Server e si vuole includere un witness di mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare lo stato delle istanze principali di SQL Server e mirror), selezionare la casella di controllo **USA mirroring di SQL Server per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:
    
     un. In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo witness di mirroring di SQL Server.
    
     b. Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare per il witness di mirroring.
    
     c. Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.
    
10. Per salvare la configurazione, fare clic su **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Pubblicare la topologia aggiornata per aggiungere un database di archiviazione alla distribuzione

1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere usando un account membro del gruppo utenti locali o un account con diritti utente equivalenti.
    
    > [!NOTE]
    > Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un server alla topologia. è necessario usare un account che sia membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** e che disponga delle autorizzazioni di controllo completo (lettura, scrittura e modifica) nella condivisione file in uso per l'archivio file di Skype for Business Server (in modo che il generatore di topologia possa configurare l'elenco di controllo di accesso discrezionale richiesto o un account con diritti equivalenti.
  
2. Aprire la topologia creata nella sezione precedente usando generatore di topologie.
    
3. Nell'albero della console fare clic con il pulsante destro del mouse su **Skype for Business Server**e quindi scegliere **Pubblica topologia**.
    
4. Nella pagina **pubblica la topologia** fare clic su **Avanti**.
    
5. Nella pagina **Crea database** verificare che il database sia selezionato e quindi fare clic su **Avanti**. 
    
    > [!NOTE]
    > Se non si dispone delle autorizzazioni appropriate per la creazione di database, è possibile annullare la selezione del database e un utente con le autorizzazioni appropriate può creare il database. > solo i database di SQL Server dedicati possono essere installati tramite Generatore di topologie. I database di SQL Server che sono collocati con altri componenti del server devono essere installati eseguendo la configurazione locale nel computer in uso. 
  
6. Nella pagina **completamento pubblicazione guidata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **fine**.
    
    > [!IMPORTANT]
    > Dopo aver pubblicato la topologia, è necessario configurare le opzioni e i criteri per l'archiviazione prima che sia possibile archiviare qualsiasi contenuto. Per informazioni dettagliate, vedere [configurare le opzioni di archiviazione per Skype for Business Server](configure-archiving-options.md) e [configurare i criteri di archiviazione per Skype for Business Server](configure-archiving-policies.md). 
  

