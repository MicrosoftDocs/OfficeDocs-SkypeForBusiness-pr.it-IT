---
title: Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Riepilogo: leggere questo argomento per informazioni su come aggiungere database di archiviazione alla distribuzione di Skype for Business Server.'
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820676"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come aggiungere database di archiviazione alla distribuzione di Skype for Business Server.
  
È necessario includere l'archiviazione nella topologia prima di poter configurare la distribuzione in modo che supporti l'archiviazione. Nelle informazioni contenute in questo argomento viene descritto come utilizzare il generatore di topologie per:
  
- Aggiungere un database di archiviazione alla topologia.
    
- Pubblicare la topologia aggiornata per aggiungere il database di archiviazione alla distribuzione di Skype for Business Server.
    
> [!NOTE]
> Se si desidera utilizzare l'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file nei server di Exchange per tutti gli utenti nella distribuzione, non specificare l' **Archivio SQL Server di archiviazione** o utilizzare le informazioni sul **mirroring dell'archivio SQL Server** .
  
### <a name="add-an-archiving-database-to-your-topology"></a>Aggiungere un database di archiviazione alla topologia

1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).
    
2. Avviare Generatore di topologie.
    
3. Nell'albero della console, passare al pool Front end in cui si desidera distribuire l'archiviazione, quindi fare clic sul nome del pool Front end in cui si desidera distribuire l'archiviazione.
    
4. Nel menu **Azione** fare clic su **Modifica proprietà**. 
    
5. Nella finestra di dialogo **Modifica proprietà** fare clic su **Generale**.
    
6. Scorrere verso il basso fino ad **Archiviazione**.
    
7. Selezionare la casella di controllo **archiviazione** .
    
8. In **Archivio SQL Server di archiviazione** eseguire una delle operazioni seguenti:
    
   - Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare. Se tutti gli utenti sono ospitati in Microsoft Exchange Server 2013 o superiori, è possibile archiviare le comunicazioni Skype for business per tutti gli utenti in Exchange. In questo caso, non è necessario configurare l'archivio di archiviazione di SQL Server.
    
   - Per specificare un nuovo archivio SQL Server, fare clic su **nuovo** e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:
    
   - In **FQDN SQL Server** specificare il nome di dominio completo del server in cui si desidera creare il nuovo archivio SQL Server.
    
   - Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.
    
   - Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.
    
9. Se si desidera utilizzare il mirroring dell'archivio SQL Server, selezionare **Abilita mirroring dell'archivio SQL Server** e quindi eseguire le operazioni seguenti:
    
   - Per utilizzare un archivio SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **mirror archivio SQL Server archiviazione** fare clic sul nome dell'archivio SQL Server che si desidera utilizzare per il mirroring.
    
   - Per specificare un nuovo archivio SQL Server per il mirroring, fare clic su **nuovo** e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire una delle operazioni seguenti:
    
     a. In **FQDN SQL Server** specificare il nome di dominio completo di SQL Server in cui si desidera creare il nuovo archivio SQL Server.
    
     b. Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.
    
     c. Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.
    
   - Se si Abilita il mirroring di SQL Server e si desidera includere un controllo del mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità delle istanze di SQL Server e del mirror principale), selezionare la casella di testo **utilizza il server di verifica del mirroring di SQL per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:
    
     a. In **FQDN SQL Server** specificare il nome di dominio completo del server in cui si desidera creare il nuovo controllo del mirroring di SQL Server.
    
     b. Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare per il controllo di mirroring.
    
     c. Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.
    
10. Per salvare la configurazione, fare clic su **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Pubblicare la topologia aggiornata per aggiungere un database di archiviazione alla distribuzione

1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).
    
    > [!NOTE]
    > È possibile definire una topologia utilizzando un account membro del gruppo Users locale, ma per pubblicare una topologia, necessaria per aggiungere un server alla topologia. è necessario utilizzare un account che sia membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** e che disponga di autorizzazioni di controllo completo (lettura, scrittura e modifica) sulla condivisione file utilizzata per l'archivio file di Skype for Business Server, in modo che generatore di topologie possa configurare l'elenco di controllo di accesso discrezionale necessario o un account con diritti equivalenti.
  
2. Aprire la topologia creata nella sezione precedente utilizzando Generatore di topologie.
    
3. Nell'albero della console fare clic con il pulsante destro del mouse su **Skype for Business Server** e quindi scegliere **Pubblica topologia**.
    
4. Nella pagina **Pubblicare la topologia** fare clic su **Avanti**.
    
5. Nella pagina **Crea altri database** verificare che il database sia selezionato e quindi fare clic su **Avanti**. 
    
    > [!NOTE]
    > Se non si dispone delle autorizzazioni appropriate per la creazione di database, è possibile annullare la selezione del database e un utente con le autorizzazioni appropriate può creare il database. > solo i database di SQL Server dedicati possono essere installati tramite Generatore di topologie. I database in computer SQL Server collocati con altri componenti server devono essere installati eseguendo il programma di installazione locale nel computer in questione. 
  
6. Nella pagina **Pubblicazione guidata completata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **Fine**.
    
    > [!IMPORTANT]
    > Dopo aver pubblicato la topologia, è necessario configurare le opzioni e i criteri per l'archiviazione, prima che sia possibile archiviare qualsiasi contenuto. Per ulteriori informazioni, vedere [configurare le opzioni di archiviazione per Skype for Business Server](configure-archiving-options.md) e [configurare i criteri di archiviazione per Skype for Business Server](configure-archiving-policies.md). 
  

