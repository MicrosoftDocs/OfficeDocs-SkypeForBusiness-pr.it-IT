---
title: 'Lync Server 2013: aggiunta dei database di archiviazione alla topologia di Lync Server 2013'
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
ms.openlocfilehash: a8bed8e9fa8b15bd4e9e7fb1f72b102ed223edd9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>Aggiunta dei database di archiviazione alla topologia di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-10_

È necessario includere l'archiviazione nella topologia prima di poter configurare la distribuzione in modo che supporti l'archiviazione. Nelle informazioni contenute in questo argomento viene descritto come utilizzare il generatore di topologie per aggiungere l'archiviazione alla topologia esistente.

<div>


> [!NOTE]  
> Se si desidera utilizzare l'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file sui server Exchange 2013 per tutti gli utenti nella distribuzione, non specificare l' <STRONG>Archivio SQL Server di archiviazione</STRONG> o utilizzare le informazioni sul <STRONG>mirroring dell'archivio SQL Server</STRONG> .



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>Per aggiungere il supporto del database di archiviazione alla topologia

1.  In un computer in cui è in esecuzione Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).
    
    <div>
    

    > [!NOTE]  
    > È possibile definire una topologia utilizzando un account membro del gruppo Users locale, ma per pubblicare una topologia, necessaria per aggiungere un server alla topologia. è necessario utilizzare un account che sia membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> e che disponga di autorizzazioni di controllo completo (ovvero lettura, scrittura e modifica) sulla condivisione file utilizzata per l'archivio file di Lync Server 2013 (ovvero, in modo che generatore di topologie possa configurare l'elenco di controllo di accesso discrezionale necessario (DACL) o un account con diritti equivalenti.

    
    </div>

2.  Avviare Generatore di topologie.

3.  Nell'albero della console, passare al pool Front end in cui si desidera distribuire l'archiviazione, quindi fare clic sul nome del pool Front end in cui si desidera distribuire l'archiviazione.

4.  Nel menu **Azione** fare clic su **Modifica proprietà**.

5.  Nella finestra di dialogo **Modifica proprietà** fare clic su **Generale**.

6.  Scorrere verso il basso fino ad **Archiviazione**.

7.  Selezionare la casella di controllo **archiviazione** .

8.  In **Archivio SQL Server di archiviazione** eseguire una delle operazioni seguenti:
    
      - Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare. Se tutti gli utenti sono ospitati in Microsoft Exchange Server 2013 o superiori, è possibile archiviare le comunicazioni di Lync per tutti gli utenti in Exchange. In questo caso, non è necessario configurare l'archivio di archiviazione di SQL Server.
    
      - Per specificare un nuovo archivio SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:
        
          - In **FQDN SQL Server**specificare il nome di dominio completo del server in cui si desidera creare il nuovo archivio SQL Server.
        
          - Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.
        
          - Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.

9.  Se si desidera utilizzare il mirroring dell'archivio SQL Server, selezionare **Abilita mirroring dell'archivio SQL Server**e quindi eseguire le operazioni seguenti:
    
      - Per utilizzare un archivio SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **mirror archivio SQL Server archiviazione** fare clic sul nome dell'archivio SQL Server che si desidera utilizzare per il mirroring.
    
      - Per specificare un nuovo archivio SQL Server per il mirroring, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire una delle operazioni seguenti:
        
        1.  In **FQDN SQL Server**specificare il nome di dominio completo di SQL Server in cui si desidera creare il nuovo archivio SQL Server.
        
        2.  Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.
        
        3.  Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.
    
      - Se si Abilita il mirroring di SQL Server e si desidera includere un controllo del mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità del server di SQL Server e delle istanze di mirror primario), selezionare la casella utilizza verifica del **mirroring di SQL Server per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:
        
        1.  In **FQDN SQL Server**specificare il nome di dominio completo del server in cui si desidera creare il nuovo controllo del mirroring di SQL Server.
        
        2.  Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare per il controllo di mirroring.
        
        3.  Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.

10. Per salvare la configurazione, fare clic su **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

