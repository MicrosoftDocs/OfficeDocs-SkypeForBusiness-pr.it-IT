---
title: 'Lync Server 2013: modificare le opzioni di archiviazione del database'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 198e2abff6118197167f0f017ace22fc2ad76381
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Modifica delle opzioni di archiviazione del database in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Se si distribuisce l'archiviazione con l'archiviazione di SQL Server per l'archiviazione dello spazio di archiviazione per tutti gli utenti, è possibile apportare le modifiche seguenti dello spazio di archiviazione del database:

  - Usare un database SQL Server diverso per l'archiviazione dello spazio di archiviazione. Questo include il database di archiviazione principale e qualsiasi database usato per il mirroring di SQL Server.

  - Passare all'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server di Exchange 2013. Se tutti gli utenti sono ospitati nei server di Exchange 2013 e si vuole usare lo spazio di archiviazione di Microsoft Exchange per tutti gli utenti della distribuzione, è consigliabile rimuovere i database di SQL Server Store dalla topologia.

Per apportare una di queste modifiche, è necessario eseguire Generatore di topologie, apportare le modifiche e quindi pubblicare di nuovo la topologia. Per eseguire questa operazione, è possibile usare generatore di topologie. Non specificare l' **archiviazione di SQL Server Store** o abilitare le informazioni di **mirroring di SQL Server Store** , a meno che non siano presenti utenti di Lync non residenti nei server di Exchange 2013.

<div>

## <a name="to-change-your-archiving-database-option"></a>Per cambiare l'opzione del database di archiviazione

1.  In un computer che esegue Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, accedere utilizzando un account membro del gruppo utenti locali o un account con diritti utente equivalenti.
    
    <div>
    

    > [!NOTE]  
    > Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un componente alla topologia. è necessario usare un account che sia un membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> e che disponga delle autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) nella condivisione di file in uso per l'archivio di file di Lync Server 2013, in modo che il generatore di topologia possa configurare gli elenchi di controllo di accesso discrezionale necessari ( DACL) o un account con diritti equivalenti.

    
    </div>

2.  Avviare Generatore di topologie.

3.  Nell'albero della console passare al pool Front-end in cui è stata distribuita l'archiviazione e quindi fare clic sul nome del pool Front-end in cui si vogliono modificare le opzioni del database.

4.  Nel menu **azione** fare clic su **modifica proprietà**.

5.  Nella finestra di dialogo **modifica proprietà** fare clic su **generale**.

6.  Scorrere verso il basso fino all' **archiviazione**.

7.  In **archiviazione**eseguire le operazioni seguenti:
    
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
            
            1.  In **FQDN di SQL Server**specificare il nome di dominio completo di SQL Server in cui si vuole creare il nuovo archivio di SQL Server.
            
            2.  Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.
            
            3.  Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.
        
          - Se si Abilita il mirroring di SQL Server e si vuole aggiungere o modificare un witness di mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità delle istanze di SQL Server e mirror principali), selezionare la casella di controllo **USA mirroring di SQL Server per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:
            
            1.  In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo witness di mirroring di SQL Server.
            
            2.  Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare per il witness di mirroring.
            
            3.  Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.
    
      - Per passare all'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server di Exchange 2013 (se tutti gli utenti della distribuzione sono ospitati nei server di Exchange 2013), eliminare tutte le informazioni per l'archiviazione dei database.
    
    <div>
    

    > [!IMPORTANT]  
    > Se gli utenti di Lync non sono ospitati nei server di Exchange 2013, non eliminare le informazioni di SQL Server Store.

    
    </div>

8.  Per salvare la configurazione, fare clic su **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Le modifiche apportate in Generatore di topologie non hanno effetto finché non viene pubblicata la nuova topologia. Per informazioni dettagliate, vedere <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">pubblicazione della topologia aggiornata per l'aggiunta di database di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

