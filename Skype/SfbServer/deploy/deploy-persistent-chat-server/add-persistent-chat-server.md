---
title: Aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 'Riepilogo: leggere questo argomento per informazioni su come aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015.'
ms.openlocfilehash: 7d5a61dd001c759eab4b168cb3543032de7b4fc4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239867"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>Aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015.
  
Dopo aver installato il software prerequisito in ogni server in cui si prevede di distribuire il server di chat persistente, è possibile usare generatore di topologia per: 
  
- Aggiornare la topologia per includere il server di chat persistente
    
- Pubblicare la topologia aggiornata
    
> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>Aggiornare la topologia per includere il server di chat persistente

Eseguire la procedura seguente per installare un singolo pool di server di chat persistente senza una configurazione di ripristino di emergenza. Per configurare un pool di server di chat persistente esteso per l'elevata disponibilità e il ripristino di emergenza, vedere [configurare la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).
  
Per distribuire più pool di server di chat persistenti, ripetere lo stesso processo per ogni pool.
  
1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere usando un account membro del gruppo utenti locali o un account con diritti utente equivalenti.
    
    > [!NOTE]
    > Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per installare Skype for Business Server, devi usare un account membro del gruppo **Domain Admins** e il ** Gruppo RTCUniversalServerAdmins** e con autorizzazioni controllo completo (lettura, scrittura e modifica) nell'archivio di file che si vuole usare per il file Store del server di chat persistente (in modo che il generatore di topologia possa configurare gli elenchi DACL necessari) o un account con diritti equivalenti.
  
2. Avviare Generatore di topologie.
    
3. Nell'albero della console passare al nodo **pool di chat persistente** ed espanderlo per selezionare un pool di Skype for Business Server oppure fare clic con il pulsante destro del mouse sul nodo e scegliere **nuovo pool di chat persistente**. È necessario definire il nome di dominio completo (FQDN) del pool e indicare se il pool sarà un pool a server singolo o un pool di distribuzione a più server.
    
    È possibile scegliere un **pool di computer multipli** o un **singolo pool di computer**. Scegliere il primo se si prevede di avere più di un server front-end nel pool del server di chat persistente. Fare questa scelta ora o in un secondo momento, perché dopo aver creato un singolo pool di computer non è possibile aggiungervi altri server in un secondo momento. Se si sceglie un pool di computer multipli, immettere i nomi dei singoli server front-end che costituiscono il pool.
    
    > [!IMPORTANT]
    > Se il ruolo del server di chat persistente viene installato in un server Standard Edition, l'FQDN deve corrispondere al nome di dominio completo del server Standard Edition. 
  
4. Definire un **nome visualizzato** semplice per il pool di server di chat persistente. Il nome visualizzato può essere usato dai client personalizzati, in particolare quando sono presenti più pool di server di chat persistenti per distinguere le sale.
    
5. Definire la porta usata dal server di chat persistente per comunicare con i server front-end di Skype for Business Server. La porta predefinita è 5041.
    
6. Se l'organizzazione richiede il supporto della conformità, selezionare la casella di controllo **Abilita conformità** . Se scelto, il servizio di conformità del server di chat persistente viene installato nello stesso computer del server front end del server di chat persistente. Viene richiesto di selezionare un server di SQL Server back-end per la conformità del server di chat persistente in un secondo momento.
    
7. Assegnare l'affinità del sito per il pool del server di chat persistente. Selezionare la casella di controllo **Usa il pool come \<predefinito\> per il sito SiteName** o **usare questo pool come predefinito per tutti i siti** per designare questo pool di server di chat persistente come pool predefinito per il sito corrente o per tutti i siti. Quando il client Skype for business viene usato per creare e gestire le sale, il pool predefinito associato al sito dell'utente viene usato dall'esperienza di creazione e gestione della sala in modo che possa instradare le operazioni di creazione e gestione della sala in tale pool. Questo problema si applica solo quando sono distribuiti più pool di server di chat persistenti e si vogliono usare le caratteristiche di creazione e gestione della sala del server di chat persistente.
    
    > [!IMPORTANT]
    > È possibile personalizzare le caratteristiche di creazione e gestione della sala usando il Software Development Kit (SDK) di Persistent Chat Server. 
  
8. Definire l' **Archivio SQL per il back-end del server di chat persistente (in cui è archiviato il contenuto della chat room)** eseguendo una delle operazioni seguenti:
    
   - Per usare un archivio di SQL Server esistente, nell'elenco a discesa fare clic sul nome dell'archivio di SQL Server che si vuole usare.
    
   - Per specificare un nuovo database di SQL Server, fare clic su **nuovo**e quindi, in **Definisci nuovo archivio SQL**, eseguire le operazioni seguenti:
    
   - In **FQDN di SQL Server**specificare il nome di dominio completo di SQL Server in cui si vuole creare il nuovo database di SQL Server.
    
   - Selezionare l'istanza **predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, selezionare **istanza denominata**e specificare l'istanza che si vuole usare.
    
     > [!NOTE]
     > Per informazioni dettagliate su come configurare i database di backup di SQL Server per il ripristino di emergenza, vedere [configurare la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
9. Definire l'archivio conformità di SQL Server se è stata abilitata la conformità.
    
    > [!IMPORTANT]
    > Per informazioni dettagliate su come configurare i mirror di SQL Server per una disponibilità elevata per il database del server di chat persistente e il database di conformità persistente per la chat server, vedere [configurare l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente per Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md). 
  
10. Definire l'archivio di file. Un archivio file è una cartella in cui è archiviata una copia di un file caricato nel repository del file, ad esempio l'archiviazione di file allegati inviati in una chat room. Nel caso di una topologia del server di chat persistente a più server, questo deve essere un percorso UNC (Universal Naming Convention). e per una topologia del server di chat persistente a singolo server, può essere un percorso di file locale.
    
    Per usare un archivio file esistente, eseguire la procedura seguente:
    
    - In **FQDN file server**specificare il nome di dominio completo del computer in cui si vuole creare il nuovo archivio di file.
    
    - In **condivisione file**specificare l'archivio di file che si vuole usare.
    
      > [!IMPORTANT]
      > È possibile definire l'archivio di file in Generatore di topologie prima di creare l'archivio di file, ma è necessario creare l'archivio file nella posizione definita che si definisce prima di pubblicare la topologia. Se l'archivio file non è già presente, i tentativi di pubblicare la topologia avranno esito negativo. 
  
11. Selezionare il pool del server front-end da usare come hop successivo per il pool di server di chat persistente. Si tratta del pool Front-End Server che sarà in grado di instradare le richieste del server di chat persistente al pool.
    
12. Per salvare la configurazione, fare clic su **fine**. Il pool di server di chat persistente viene visualizzato in Generatore di topologia accompagnato dalle impostazioni specifiche del pool.
    
    Per pubblicare la topologia aggiornata a cui è stato aggiunto il server di chat persistente, vedere pubblicare la topologia aggiornata.
    
    > [!NOTE]
    > Con generatore di topologia già aperto, è possibile procedere con il passaggio 3 della pubblicazione della topologia aggiornata per iniziare a pubblicare la topologia aggiornata. 
  
## <a name="publish-the-updated-topology"></a>Pubblicare la topologia aggiornata
<a name="BKMK_PublishTopology"> </a>

Dopo l'aggiornamento della topologia in Generatore di topologie, è necessario pubblicare la topologia in Central Management Store prima di poter configurare e usare Skype for Business Server. Le copie di sola lettura dei dati vengono replicate in tutti i server della topologia per garantire la sincronizzazione di tutti i server con la topologia e altre modifiche alla configurazione.
  
Prima di pubblicare la topologia, installare i database per il server di chat persistente. Usare generatore di topologie per installare i database selezionando **azione** e **Installa database**.
  
1. In un computer che esegue Skype for Business Server o in cui sono installati gli strumenti di amministrazione di Skype for Business Server, accedere con un account membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** . e con autorizzazioni di controllo completo (lettura, scrittura e modifica) nell'archivio di file da usare per l'archivio di file della chat persistente (in modo che il generatore di topologia possa configurare gli elenchi di controllo di accesso discrezionale (DACL) necessari) o un account con un utente equivalente diritti.
    
2. Avviare Generatore di topologie. Selezionare **Apri topologia da un file locale** se è stato salvato localmente.
    
3. Nell'albero della console fare clic con il pulsante destro del mouse su **Skype for Business Server 2015**e quindi scegliere **Pubblica topologia**.
    
4. Nella pagina **pubblica la topologia** fare clic su **Avanti**.
    
5. Nella pagina **completamento pubblicazione guidata** verificare che la topologia sia stata pubblicata correttamente e quindi fare clic su **fine**.
    

