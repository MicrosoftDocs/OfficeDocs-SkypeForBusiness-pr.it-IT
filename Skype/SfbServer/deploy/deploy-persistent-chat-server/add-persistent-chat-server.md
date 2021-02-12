---
title: Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Riepilogo: leggere questo argomento per informazioni su come aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015.'
ms.openlocfilehash: 3b0f3ca57af4b9bf53125e38e1aa3005099b5b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825106"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015.
  
Dopo aver installato il software prerequisito in ogni server in cui si prevede di distribuire il server Chat persistente, utilizzare Generatore di topologie per: 
  
- Aggiornare la topologia per includere il server Chat persistente
    
- Pubblicare la topologia aggiornata
    
> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. Le stesse funzionalità sono disponibili in Teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here) Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Aggiornare la topologia per includere il server Chat persistente

Eseguire la procedura seguente per installare un singolo pool di server Chat persistente senza una configurazione di ripristino di emergenza. Per configurare un pool di server Chat persistente estesa per la disponibilità elevata e il ripristino di emergenza, vedere Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente [in Skype for Business Server 2015.](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)
  
Per distribuire più pool di server Chat persistente, ripetere lo stesso processo per ogni pool.
  
1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere con un account membro del gruppo Utenti locale (o un account con diritti utente equivalenti).
    
    > [!NOTE]
    > È possibile definire una topologia utilizzando un account membro del gruppo Utenti locale. Tuttavia, per pubblicare una topologia, necessaria per installare Skype for Business Server, è necessario utilizzare un account membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** e che dispone delle autorizzazioni di controllo completo (lettura, scrittura e modifica) nell'archivio file che si desidera utilizzare per l'archivio file del server Chat persistente (in modo che Generatore di topologie possa configurare i DACL necessari) o un account con diritti equivalenti.
  
2. Avviare Generatore di topologie.
    
3. Nell'albero della console passare al nodo Pool di **Chat persistente** ed espanderlo per selezionare un pool di Skype for Business Server oppure fare clic con il pulsante destro del mouse sul nodo e scegliere Nuovo **pool di Chat persistente.** È necessario definire il nome di dominio completo (FQDN) del pool e indicare se il pool sarà una distribuzione di pool a server singolo o a più server.
    
    È possibile scegliere un **Pool di più computer** o un **Pool computer singolo**. Scegliere il primo se si prevede di disporre di più Front End Server nel pool di server Chat persistente. Questa selezione deve essere operata subito o in seguito, poiché se si crea un pool computer singolo, non è possibile aggiungervi altri server in seguito. Se si sceglie un pool con più computer, immettere i nomi dei singoli Front End Server che costituiscono il pool.
    
    > [!IMPORTANT]
    > Se il ruolo del server Chat persistente viene installato in un server Standard Edition, il nome di dominio completo deve corrispondere al nome di dominio completo del server Standard Edition. 
  
4. Definire un nome **visualizzato semplice per** il pool di server Chat persistente. Il nome visualizzato può essere utilizzato dai client personalizzati, in particolare quando sono presenti più pool di server Chat persistente per differenziare le chat room.
    
5. Definire la porta utilizzata dal server Chat persistente per comunicare con i Front End Server di Skype for Business Server. Per impostazione predefinita, viene utilizzata la porta 5041.
    
6. Se l'organizzazione richiede il supporto della conformità, selezionare la casella di controllo **Abilita conformità**. Se scelto, il servizio Conformità server Chat persistente viene installato nello stesso computer del Front End Server del server Chat persistente. Verrà richiesto di selezionare un server SQL Server server back-end per la conformità del server Chat persistente in un secondo momento.
    
7. Assegnare l'affinità del sito per il pool di server Chat persistente. Selezionare la casella di controllo Utilizza questo **pool \<SiteName\>** come predefinito per il sito o Utilizza questo **pool** come predefinito per tutti i siti per designare il pool di server Chat persistente come pool predefinito per il sito corrente o per tutti i siti. Quando il client Skype for Business viene utilizzato per creare e gestire le chat room, il pool predefinito associato al sito dell'utente viene utilizzato dall'esperienza di creazione e gestione delle chat room in modo che possa instradare le operazioni di creazione e gestione delle chat room a tale pool. Ciò si applica solo quando sono distribuiti più pool di server Chat persistente e si desidera utilizzare le funzionalità di creazione e gestione delle chat room del server Chat persistente.
    
    > [!IMPORTANT]
    > È possibile personalizzare le funzionalità di creazione e gestione delle chat room utilizzando Persistent Chat Server Software Development Kit (SDK). 
  
8. Definire l SQL di archiviazione per il **back-end del server Chat persistente (in** cui è archiviato il contenuto della chat room) eseguendo una delle operazioni seguenti:
    
   - Per usare un archivio SQL Server esistente, nell'elenco a discesa fare clic sul nome dell'SQL Server che si desidera utilizzare.
    
   - Per specificare un nuovo database SQL Server, fare clic su **Nuovo** e in Definisci nuovo **SQL store** eseguire le operazioni seguenti:
    
   - In **SQL Server FQDN** specificare il nome di dominio completo del SQL Server in cui si desidera creare il nuovo database SQL Server database.
    
   - Selezionare **Istanza predefinita** per utilizzare un'istanza predefinita oppure **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si desidera utilizzare.
    
     > [!NOTE]
     > Per informazioni dettagliate su come configurare i database di backup di SQL Server per il ripristino di emergenza, vedere Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente [in Skype for Business Server 2015.](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md) 
  
9. Definire l'SQL Server di conformità se è stata abilitata la conformità.
    
    > [!IMPORTANT]
    > Per informazioni dettagliate su come configurare i mirror di SQL Server per la disponibilità elevata per il database del server Chat persistente e il database di conformità del server Chat persistente, vedere Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente [in Skype for Business Server 2015.](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md) 
  
10. Definire l'archivio file. Un archivio file è una cartella in cui è archiviata una copia di qualunque file caricato nell'archivio dei file (ad esempio, gli allegati pubblicati in una chat room). Nel caso di una topologia di server Chat persistente con più server, questo deve essere un percorso UNC (Universal Naming Convention). e per una topologia di server Chat persistente a server singolo, può essere un percorso di file locale.
    
    Per utilizzare un archivio file esistente, eseguire le operazioni seguenti:
    
    - In **FQDN file server** specificare il nome di dominio completo del computer in cui si desidera creare il nuovo archivio file.
    
    - In **Condivisione file**, specificare l'archivio file che si desidera utilizzare.
    
      > [!IMPORTANT]
      > È possibile definire l'archivio file in Generatore di topologie prima di creare l'archivio file, ma è necessario crearlo nel percorso definito prima di pubblicare la topologia. Se l'archivio file non esiste già, i tentativi di pubblicare la topologia avranno esito negativo. 
  
11. Selezionare il pool Front End Server da utilizzare come hop successivo per il pool di server Chat persistente. Si tratta del pool Front End Server che sarà in grado di instradare le richieste del server Chat persistente a questo pool.
    
12. Per salvare la configurazione, fare clic su **Fine**. Il pool di server Chat persistente viene visualizzato in Generatore di topologie insieme alle impostazioni specifiche del pool.
    
    Per pubblicare la topologia aggiornata a cui è stato aggiunto il server Chat persistente, vedere Pubblicare la topologia aggiornata.
    
    > [!NOTE]
    > Con Generatore di topologie già aperto, è possibile procedere con il passaggio 3 in Pubblicare la topologia aggiornata per iniziare a pubblicare la topologia aggiornata. 
  
## <a name="publish-the-updated-topology"></a>Pubblicare la topologia aggiornata
<a name="BKMK_PublishTopology"> </a>

Dopo aver aggiornato la topologia in Generatore di topologie, è necessario pubblicare la topologia nell'archivio di gestione centrale prima di poter configurare e utilizzare Skype for Business Server. In tutti i server della topologia vengono replicate copie di sola lettura dei dati in modo che siano sincronizzati con la topologia e altre modifiche della configurazione.
  
Prima di pubblicare la topologia, installare i database per il server Chat persistente. Utilizzare Generatore di topologie per installare i database **selezionando** Azione e **Installa database.**
  
1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere con un account membro sia del gruppo **Domain Admins** che del gruppo **RTCUniversalServerAdmins** e che dispone delle autorizzazioni di controllo completo (lettura, scrittura e modifica) nell'archivio file da utilizzare per l'archivio file del server Chat persistente (in modo che Generatore di topologie possa configurare gli elenchi di controllo di accesso discrezionale (DACL) necessari) o un account con diritti utente equivalenti.
    
2. Avviare Generatore di topologie. Selezionare **Apri topologia da un file locale** se è stato salvato in locale.
    
3. Nell'albero della console fare clic con il pulsante destro del mouse su **Skype for Business Server 2015** e quindi scegliere Pubblica **topologia.**
    
4. Nella pagina **Pubblicare la topologia** fare clic su **Avanti**.
    
5. Nella pagina **Pubblicazione guidata completata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **Fine**.
    

