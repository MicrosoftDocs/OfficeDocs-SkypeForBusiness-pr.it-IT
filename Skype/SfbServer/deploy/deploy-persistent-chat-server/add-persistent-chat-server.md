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
  
Dopo aver installato il software prerequisito su ogni server in cui si prevede di distribuire il server Chat persistente, è possibile utilizzare Generatore di topologie per: 
  
- Aggiornare la topologia in modo da includere il server Chat persistente
    
- Pubblicare la topologia aggiornata
    
> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Aggiornare la topologia in modo da includere il server Chat persistente

Eseguire la procedura seguente per installare un singolo pool di server Chat persistente senza una configurazione di ripristino di emergenza. Per configurare un pool di server Chat persistente esteso per la disponibilità elevata e il ripristino di emergenza, vedere [configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Per distribuire più pool di server di chat persistente, ripetere lo stesso processo per ogni pool.
  
1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).
    
    > [!NOTE]
    > È possibile definire una topologia utilizzando un account membro del gruppo Users locale, ma per pubblicare una topologia, necessaria per installare Skype for Business Server, è necessario utilizzare un account che sia membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** e che disponga di autorizzazioni di controllo completo (lettura, scrittura e modifica) nell'archivio file da utilizzare per l'archivio file del server Chat persistente, in modo che il generatore di topologie possa configurare gli elenchi DACL necessari o un account con diritti equivalenti.
  
2. Avviare Generatore di topologie.
    
3. Nell'albero della console, passare al nodo **pool di chat persistente** ed espanderlo per selezionare un pool di Skype for Business Server oppure fare clic con il pulsante destro del mouse sul nodo e scegliere **nuovo pool di chat persistente**. È necessario definire il nome di dominio completo (FQDN) del pool e indicare se il pool sarà un pool a server singolo o una distribuzione di pool con più server.
    
    È possibile scegliere un **Pool di più computer** o un **Pool computer singolo**. Scegliere l'ex se si prevede di avere più di un front end server nel pool di server Chat persistente. Questa selezione deve essere operata subito o in seguito, poiché se si crea un pool computer singolo, non è possibile aggiungervi altri server in seguito. Se si sceglie un pool di più computer, immettere i nomi dei singoli front end server che costituiscono il pool.
    
    > [!IMPORTANT]
    > Se il ruolo del server Chat persistente è in fase di installazione in un server Standard Edition, il nome FQDN deve corrispondere al nome di dominio completo del server Standard Edition. 
  
4. Definire un **nome visualizzato** semplice per il pool di server Chat persistente. Il nome visualizzato può essere utilizzato dai client personalizzati, in particolare quando sono presenti più pool di server di chat persistente per differenziare le sale.
    
5. Definire la porta utilizzata dal server Chat persistente per comunicare con i server front end di Skype for Business Server. Per impostazione predefinita, viene utilizzata la porta 5041.
    
6. Se l'organizzazione richiede il supporto della conformità, selezionare la casella di controllo **Abilita conformità**. Se si sceglie, il servizio di conformità del server Chat persistente viene installato nello stesso computer del server front end server di chat persistente. Viene richiesto di selezionare un server back-end SQL Server per la conformità del server Chat persistente in un secondo momento.
    
7. Assegnare l'affinità dei siti per il pool di server Chat persistente. Selezionare la casella di controllo **utilizza questo pool come \<SiteName\>** predefinito per il sito oppure **utilizzare questo pool come predefinito per tutti i siti** per designare il pool di server Chat persistente come pool predefinito per il sito corrente o per tutti i siti. Quando si utilizza il client Skype for business per creare e gestire le chat room, il pool predefinito associato al sito dell'utente viene utilizzato dall'esperienza di creazione e gestione della sala in modo che possa instradare le operazioni di creazione e gestione della sala in tale pool. Questo valore si applica solo quando si dispone di più pool di server Chat persistente e si desidera utilizzare le funzionalità di creazione e gestione delle chat del server Persistent.
    
    > [!IMPORTANT]
    > È possibile personalizzare le funzionalità di creazione e gestione della sala utilizzando il Software Development Kit (SDK) di Persistent Chat Server. 
  
8. Definire l' **Archivio SQL per il back-end del server Chat persistente (in cui è archiviato il contenuto della chat room)** eseguendo una delle operazioni seguenti:
    
   - Per utilizzare un archivio SQL Server esistente, nell'elenco a discesa fare clic sul nome dell'archivio SQL Server che si desidera utilizzare.
    
   - Per specificare un nuovo database di SQL Server, fare clic su **nuovo** e in **Definisci nuovo archivio SQL**, eseguire le operazioni seguenti:
    
   - In **FQDN SQL Server** specificare il nome di dominio completo di SQL Server in cui si desidera creare il nuovo database di SQL Server.
    
   - Selezionare **Istanza predefinita** per utilizzare un'istanza predefinita oppure **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si desidera utilizzare.
    
     > [!NOTE]
     > Per informazioni dettagliate su come configurare i database di backup di SQL Server per il ripristino di emergenza, vedere [configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Se è stata abilitata la conformità, definire l'archivio di conformità di SQL Server.
    
    > [!IMPORTANT]
    > Per informazioni dettagliate su come configurare i mirror di SQL Server per la disponibilità elevata per il database del server Chat persistente e il database di conformità del server Chat persistente, vedere [configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Definire l'archivio file. Un archivio file è una cartella in cui è archiviata una copia di qualunque file caricato nell'archivio dei file (ad esempio, gli allegati pubblicati in una chat room). Nel caso di una topologia del server Chat persistente a più server, deve essere un percorso UNC (Universal Naming Convention). per una topologia del server Chat persistente a server singolo, può essere un percorso di file locale.
    
    Per utilizzare un archivio file esistente, eseguire le operazioni seguenti:
    
    - In **FQDN file server** specificare il nome di dominio completo del computer in cui si desidera creare il nuovo archivio file.
    
    - In **Condivisione file**, specificare l'archivio file che si desidera utilizzare.
    
      > [!IMPORTANT]
      > È possibile definire l'archivio file in Generatore di topologie prima di creare l'archivio file, ma è necessario creare l'archivio file nel percorso definito prima di pubblicare la topologia. Se l'archivio file non esiste già, il tentativo di pubblicare la topologia avrà esito negativo. 
  
11. Selezionare il pool Front End Server da utilizzare come hop successivo per il pool di server Chat persistente. Si tratta del pool Front End Server che sarà in grado di instradare le richieste del server Chat persistente al pool.
    
12. Per salvare la configurazione, fare clic su **Fine**. Il pool di server Chat persistente viene visualizzato in Generatore di topologie accompagnato dalle impostazioni del pool specifiche.
    
    Per pubblicare la topologia aggiornata a cui è stato aggiunto il server Chat persistente, vedere pubblicare la topologia aggiornata.
    
    > [!NOTE]
    > Con generatore di topologie già aperto, è possibile procedere con il passaggio 3 in pubblicare la topologia aggiornata per iniziare a pubblicare la topologia aggiornata. 
  
## <a name="publish-the-updated-topology"></a>Pubblicare la topologia aggiornata
<a name="BKMK_PublishTopology"> </a>

Dopo aver aggiornato la topologia in Generatore di topologie, è necessario pubblicare la topologia nell'archivio di gestione centrale prima di poter configurare e usare Skype for Business Server. In tutti i server della topologia vengono replicate copie di sola lettura dei dati in modo che siano sincronizzati con la topologia e altre modifiche della configurazione.
  
Prima di pubblicare la topologia, installare i database per il server Chat persistente. Utilizzare Generatore di topologie per installare i database selezionando **azione** e **Installa database**.
  
1. In un computer in cui è in esecuzione Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere utilizzando un account che sia membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** e che disponga di autorizzazioni di controllo completo (lettura, scrittura e modifica) nell'archivio file da utilizzare per l'archivio file del server Chat persistente, in modo che il generatore di topologie possa configurare gli elenchi di controllo di accesso discrezionale necessari o un account con diritti utente equivalenti.
    
2. Avviare Generatore di topologie. Se è stato salvato localmente, selezionare **Apri topologia da un file locale** .
    
3. Nell'albero della console fare clic con il pulsante destro del mouse su **Skype for Business Server 2015** e quindi scegliere **Pubblica topologia**.
    
4. Nella pagina **Pubblicare la topologia** fare clic su **Avanti**.
    
5. Nella pagina **Pubblicazione guidata completata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **Fine**.
    

