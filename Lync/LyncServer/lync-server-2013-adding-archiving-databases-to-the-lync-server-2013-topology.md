---
title: 'Lync Server 2013: aggiunta di database di archiviazione alla topologia di Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7476107b064b45dbef74b03ff9d54e02fc9eee52
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>Aggiunta di database di archiviazione alla topologia di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-10_

È necessario incorporare l'archiviazione nella topologia prima di poter configurare la distribuzione per supportare l'archiviazione. Le informazioni contenute in questo argomento spiegano come usare generatore di topologia per aggiungere l'archiviazione alla topologia esistente.

<div>


> [!NOTE]  
> Se si vuole usare l'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server di Exchange 2013 per tutti gli utenti della distribuzione, non specificare l' <STRONG>archiviazione di SQL Server Store</STRONG> o usare le informazioni di <STRONG>mirroring di SQL Server Store</STRONG> .



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>Per aggiungere il supporto di archiviazione del database alla topologia

1.  In un computer che esegue Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, accedere utilizzando un account membro del gruppo utenti locali o un account con diritti utente equivalenti.
    
    <div>
    

    > [!NOTE]  
    > Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un server alla topologia. è necessario usare un account che sia un membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> e che disponga delle autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) nella condivisione di file in uso per l'archivio di file di Lync Server 2013, in modo che il generatore di topologia possa configurare l'elenco di controllo di accesso discrezionale richiesto (DACL). o un account con diritti equivalenti.

    
    </div>

2.  Avviare Generatore di topologie.

3.  Nell'albero della console passare al pool Front-end in cui si vuole distribuire l'archiviazione e quindi fare clic sul nome del pool Front end in cui si vuole distribuire l'archiviazione.

4.  Nel menu **azione** fare clic su **modifica proprietà**.

5.  Nella finestra di dialogo **modifica proprietà** fare clic su **generale**.

6.  Scorrere verso il basso fino all' **archiviazione**.

7.  Selezionare la casella di controllo **archiviazione** .

8.  In **archiviazione SQL Server Store** eseguire una delle operazioni seguenti:
    
      - Per usare un archivio di SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio di SQL Server che si vuole usare. Se tutti gli utenti sono ospitati in Microsoft Exchange Server 2013 o versioni successive, è possibile archiviare le comunicazioni di Lync per tutti gli utenti in Exchange. In questo caso, non è necessario configurare l'archivio di archiviazione di SQL Server.
    
      - Per specificare un nuovo archivio di SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:
        
          - In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo archivio di SQL Server.
        
          - Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.
        
          - Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.

9.  Se si vuole usare il mirroring di SQL Server Store, selezionare **Abilita mirroring di SQL Server Store**e quindi eseguire le operazioni seguenti:
    
      - Per usare un archivio di SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **archiviazione di SQL Server dell'archivio** , fare clic sul nome dell'archivio di SQL Server che si vuole usare per il mirroring.
    
      - Per specificare un nuovo archivio di SQL Server per il mirroring, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio di SQL Server** eseguire una delle operazioni seguenti:
        
        1.  In **FQDN di SQL Server**specificare il nome di dominio completo di SQL Server in cui si vuole creare il nuovo archivio di SQL Server.
        
        2.  Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare.
        
        3.  Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.
    
      - Se si Abilita il mirroring di SQL Server e si vuole includere un witness di mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità delle istanze di SQL Server e mirror principali), selezionare la casella di controllo **USA mirroring di SQL Server per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:
        
        1.  In **FQDN di SQL Server**specificare il nome di dominio completo del server in cui si vuole creare il nuovo witness di mirroring di SQL Server.
        
        2.  Fare clic su **istanza predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, fare clic su **istanza denominata**e quindi specificare l'istanza che si vuole usare per il witness di mirroring.
        
        3.  Se l'istanza di SQL Server specificata si trova in una relazione speculare, selezionare la casella **di controllo questa istanza SQL è in relazione di mirroring** e quindi, in **numero di porta speculare**, specificare il numero di porta.

10. Per salvare la configurazione, fare clic su **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

