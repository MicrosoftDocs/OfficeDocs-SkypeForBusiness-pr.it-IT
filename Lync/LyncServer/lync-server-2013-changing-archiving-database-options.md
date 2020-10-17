---
title: 'Lync Server 2013: modifica delle opzioni del database di archiviazione'
description: 'Lync Server 2013: modifica delle opzioni del database di archiviazione.'
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
ms.openlocfilehash: 7a3751be63e17688ad9258b9773a1a5397b67952
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543582"
---
# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Modifica delle opzioni del database di archiviazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Se si distribuisce l'archiviazione utilizzando l'archiviazione di SQL Server per l'archiviazione di un utente, è possibile apportare le modifiche apportate ai database seguenti:

  - Utilizzare un database di SQL Server diverso per l'archiviazione. Sono inclusi il database di archiviazione principale e qualsiasi database utilizzato per il mirroring di SQL Server.

  - Passare all'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file sui server Exchange 2013. Se tutti gli utenti sono ospitati nei server Exchange 2013 e si desidera utilizzare lo spazio di archiviazione di Microsoft Exchange per tutti gli utenti nella distribuzione, è necessario rimuovere i database dell'archivio SQL Server dalla topologia.

Per apportare una o più di queste modifiche, è necessario eseguire Generatore di topologie, apportare le modifiche e quindi ripubblicare la topologia. Per eseguire questa operazione, è possibile utilizzare Generatore di topologie. Non specificare l' **Archivio SQL Server di archiviazione** o abilitare le informazioni sul **mirroring dell'archivio SQL Server** , a meno che non siano presenti utenti di Lync che non sono ospitati nei server Exchange 2013.

<div>

## <a name="to-change-your-archiving-database-option"></a>Per modificare l'opzione del database di archiviazione

1.  In un computer in cui è in esecuzione Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).
    
    <div>
    

    > [!NOTE]  
    > È possibile definire una topologia utilizzando un account membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per aggiungere un componente alla topologia, è necessario utilizzare un account membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> . e che dispone di autorizzazioni di controllo completo (ovvero lettura, scrittura e modifica) sulla condivisione file utilizzata per l'archivio file di Lync Server 2013 (ovvero, in modo che generatore di topologie possa configurare gli elenchi di controllo di accesso discrezionale necessari o un account con diritti equivalenti.

    
    </div>

2.  Avviare Generatore di topologie.

3.  Nell'albero della console accedere al pool Front End in cui è stata distribuita Archiviazione e fare clic sul nome del pool Front End in cui si vuole modificare le opzioni di database.

4.  Nel menu **Azione** fare clic su **Modifica proprietà**.

5.  Nella finestra di dialogo **Modifica proprietà** fare clic su **Generale**.

6.  Scorrere verso il basso fino ad **Archiviazione**.

7.  In **Archiviazione** seguire questa procedura:
    
      - Per passare a un archivio SQL Server esistente diverso, nella casella di riepilogo a discesa in **Archivio SQL Server archiviazione** seguire la procedura seguente:
        
          - Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare.
        
          - Per specificare un nuovo archivio SQL Server, fare clic su **Nuovo**, quindi nella finestra di dialogo **Definire un nuovo archivio SQL Server** seguire questa procedura:
            
              - Per usare un archivio SQL Server esistente, nella casella di riepilogo a discesa fare clic sul nome dell'archivio SQL Server che si vuole usare.
            
              - Per specificare un nuovo archivio SQL Server, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire le operazioni seguenti:
                
                  - In **FQDN SQL Server**specificare il nome di dominio completo del server in cui si desidera creare il nuovo archivio SQL Server.
                
                  - Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.
                
                  - Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.
    
      - Per aggiungere l'archivio SQL Server per il mirroring o passare a un archivio SQL Server esistente diverso per il mirroring dell'archivio SQL Server, selezionare **Abilita mirroring dell'archivio SQL Server**, quindi procedere come segue:
        
          - Per utilizzare un archivio SQL Server esistente per il mirroring, nella casella di riepilogo a discesa **mirror archivio SQL Server archiviazione** fare clic sul nome dell'archivio SQL Server che si desidera utilizzare per il mirroring.
        
          - Per specificare un nuovo archivio SQL Server per il mirroring, fare clic su **nuovo**e quindi nella finestra di dialogo **Definisci nuovo archivio SQL Server** eseguire una delle operazioni seguenti:
            
            1.  In **FQDN SQL Server**specificare il nome di dominio completo di SQL Server in cui si desidera creare il nuovo archivio SQL Server.
            
            2.  Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare.
            
            3.  Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.
        
          - Se si Abilita il mirroring di SQL Server e si desidera aggiungere o modificare un controllo del mirroring di SQL Server (una terza istanza di SQL Server separata in grado di rilevare l'integrità del server SQL Server primario e delle istanze di mirroring), selezionare la casella utilizza verifica del **mirroring di SQL Server per abilitare il failover automatico** e quindi eseguire una delle operazioni seguenti:
            
            1.  In **FQDN SQL Server**specificare il nome di dominio completo del server in cui si desidera creare il nuovo controllo del mirroring di SQL Server.
            
            2.  Fare clic su **Istanza predefinita** per usare l'istanza predefinita oppure su **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si vuole usare per il controllo di mirroring.
            
            3.  Se l'istanza di SQL Server specificata è in una relazione di mirroring, selezionare la casella **di controllo questa istanza di SQL è in relazione di mirroring** e quindi, in **numero di porta dello specchio**, specificare il numero di porta.
    
      - Per passare all'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file sui server Exchange 2013 (se tutti gli utenti della distribuzione sono ospitati nei server Exchange 2013), eliminare tutte le informazioni per i database di archiviazione.
    
    <div>
    

    > [!IMPORTANT]  
    > Se si dispone di utenti Lync che non sono ospitati nei server Exchange 2013, non eliminare le informazioni sull'archivio SQL Server.

    
    </div>

8.  Per salvare la configurazione, fare clic su **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Le modifiche apportate in Generatore di topologie non sono effettive finché non si pubblica la nuova topologia. Per ulteriori informazioni, vedere <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topologie to Add Archiving Databases in Lync Server 2013</A> nella documentazione relativa alla distribuzione.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

