---
title: Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Riepilogo: leggere questo argomento per informazioni su come aggiungere database di archiviazione alla Skype for Business Server distribuzione.'
ms.openlocfilehash: d9434ffaf2141ea176b99825571ad2a17d0d5601
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864473"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Aggiungere database di archiviazione a una distribuzione esistente in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come aggiungere database di archiviazione alla Skype for Business Server distribuzione.
  
È necessario incorporare l'archiviazione nella topologia prima di poter configurare la distribuzione per supportare l'archiviazione. Le informazioni contenute in questo argomento spiegano come utilizzare Generatore di topologie per:
  
- Aggiungere un database di archiviazione alla topologia.
    
- Pubblicare la topologia aggiornata per aggiungere il database di archiviazione alla Skype for Business Server distribuzione.
    
> [!NOTE]
> Se si desidera utilizzare l'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server Exchange per tutti gli utenti della distribuzione, non specificare Archivio **SQL Server** archiviazione o Usa informazioni di mirroring di **SQL Server Store.**
  
### <a name="add-an-archiving-database-to-your-topology"></a>Aggiungere un database di archiviazione alla topologia

1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere utilizzando un account membro del gruppo Users locale (o un account con diritti utente equivalenti).
    
2. Avviare Generatore di topologie.
    
3. Nell'albero della console passare al pool Front End in cui si desidera distribuire l'archiviazione e quindi fare clic sul nome del pool Front End in cui si desidera distribuire l'archiviazione.
    
4. Nel menu **Azione** fare clic su **Modifica proprietà**. 
    
5. Nella finestra di dialogo **Modifica proprietà** fare clic su **Generale**.
    
6. Scorrere verso il basso fino ad **Archiviazione**.
    
7. Selezionare la **casella di controllo** Archiviazione.
    
8. In **Archivio SQL Server archiviazione eseguire** una delle operazioni seguenti:
    
   - Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare. Se tutti gli utenti sono ospitati Microsoft Exchange Server 2013 o versioni successive, è possibile archiviare Skype for Business comunicazioni per tutti gli utenti in Exchange. In questo caso, non è necessario configurare SQL Server archivio.
    
   - Per specificare un nuovo SQL Server store, fare clic su **Nuovo** e quindi nella finestra di dialogo Definisci nuovo **SQL Server Store** eseguire le operazioni seguenti:
    
   - In **SQL Server FQDN** specificare il nome di dominio completo del server in cui si desidera creare il nuovo SQL Server archivio.
    
   - Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.
    
   - Se l'istanza SQL Server specificata si trova in una relazione di mirroring, selezionare la casella di controllo Questa istanza di **SQL è in** relazione di mirroring e quindi, in **Numero** porta mirror, specificare il numero di porta.
    
9. Se si desidera utilizzare il mirroring dell SQL Server store, selezionare **Abilita mirroring** SQL Server Store e quindi eseguire le operazioni seguenti:
    
   - Per utilizzare un archivio SQL Server esistente per il mirroring, nella casella di riepilogo a discesa Mirror archivio **SQL Server** archiviazione fare clic sul nome dell'archivio SQL Server che si desidera utilizzare per il mirroring.
    
   - Per specificare un nuovo archivio SQL Server per il mirroring, fare clic su **Nuovo** e quindi nella finestra di dialogo Definisci nuovo **SQL Server Store** eseguire una delle operazioni seguenti:
    
     a. In **SQL Server FQDN** specificare il nome di dominio completo del SQL Server in cui si desidera creare il nuovo SQL Server archivio.
    
     b. Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.
    
     c. Se l'istanza SQL Server specificata si trova in una relazione di mirroring, selezionare la casella di controllo Questa istanza di **SQL è in** relazione di mirroring e quindi, in **Numero** porta mirror, specificare il numero di porta.
    
   - Se si abilita il mirroring SQL Server e si desidera includere un controllo del mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità delle istanze SQL Server e mirror primarie), selezionare la casella di controllo Usa **controllo del mirroring** di SQL Server per abilitare il failover automatico e quindi eseguire una delle seguenti attività: e:
    
     a. In **SQL Server FQDN** specificare il nome di dominio completo del server in cui si desidera creare il nuovo SQL Server di mirroring.
    
     b. Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare per il controllo di mirroring.
    
     c. Se l'istanza SQL Server specificata si trova in una relazione di mirroring, selezionare la casella di controllo Questa istanza di **SQL è in** relazione di mirroring e quindi, in **Numero** porta mirror, specificare il numero di porta.
    
10. Per salvare la configurazione, fare clic su **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Pubblicare la topologia aggiornata per aggiungere un database di archiviazione alla distribuzione

1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere utilizzando un account membro del gruppo Users locale (o un account con diritti utente equivalenti).
    
    > [!NOTE]
    > È possibile definire una topologia utilizzando un account membro del gruppo Users locale, ma per pubblicare una topologia, necessaria per aggiungere un server alla topologia, è necessario utilizzare un account membro del gruppo **Domain Admins** e **rtcUniversalServerAdmins** e che dispone delle autorizzazioni di controllo completo (lettura,  scrivere e modificare) nella condivisione file in uso per l'archivio file di Skype for Business Server ,in modo che Generatore di topologie possa configurare l'elenco di controllo di accesso discrezionale (DACL) necessario o un account con diritti equivalenti.
  
2. Aprire la topologia creata nella sezione precedente utilizzando Generatore di topologie.
    
3. Nell'albero della console fare clic con il pulsante destro **Skype for Business Server** e quindi scegliere **Pubblica topologia**.
    
4. Nella pagina **Pubblicare la topologia** fare clic su **Avanti**.
    
5. Nella pagina **Crea altri database** verificare che il database sia selezionato e quindi fare clic su **Avanti**. 
    
    > [!NOTE]
    > Se non si dispone delle autorizzazioni appropriate per creare i database, è possibile annullare la selezione del database e un utente con le autorizzazioni appropriate può creare il database. > solo i database in SQL server dedicati possono essere installati utilizzando Generatore di topologie. I database in computer SQL Server collocati con altri componenti server devono essere installati eseguendo il programma di installazione locale nel computer in questione. 
  
6. Nella pagina **Pubblicazione guidata completata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **Fine**.
    
    > [!IMPORTANT]
    > Dopo aver pubblicato la topologia, è necessario configurare le opzioni e i criteri per l'archiviazione, prima che sia possibile archiviare qualsiasi contenuto. Per informazioni dettagliate, vedere [Configure archiving options for Skype for Business Server](configure-archiving-options.md) e Configure archiving policies for [Skype for Business Server](configure-archiving-policies.md). 
  

