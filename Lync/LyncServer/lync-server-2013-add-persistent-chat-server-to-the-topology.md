---
title: 'Lync Server 2013: aggiungere il server Chat persistente alla topologia'
description: 'Lync Server 2013: aggiungere il server Chat persistente alla topologia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0321978ce4a0c7381cf2915030267645931f572b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572432"
---
# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>Aggiungere il server Chat persistente alla topologia in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

È necessario includere Lync Server 2013, il supporto del server Chat persistente nella topologia prima di poter configurare la distribuzione per il supporto del server Chat persistente. Nelle informazioni contenute in questo argomento viene descritto come utilizzare il generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia esistente.

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>Per aggiungere il server Chat persistente a una topologia

Eseguire la procedura seguente per installare un singolo pool di server Chat persistente senza una configurazione di ripristino di emergenza. Per la configurazione di un pool di server Chat persistente esteso per la disponibilità elevata e il ripristino di emergenza, vedere [Configuring Persistent Chat Server for High Availability and Disaster Recovery in Lync server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) nella documentazione relativa alla distribuzione.

Per distribuire più pool di server di chat persistente, ripetere lo stesso processo per ogni pool.

1.  In un computer in cui è in esecuzione Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, eseguire l'accesso utilizzando un account membro del gruppo utenti locali (o un account con diritti utente equivalenti).
    
    <div>
    

    > [!NOTE]  
    > È possibile definire una topologia utilizzando un account membro del gruppo Users locale, ma per pubblicare una topologia, necessaria per installare un server Lync Server 2013, è necessario utilizzare un account che sia membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> e che disponga di autorizzazioni di controllo completo, ovvero lettura, scrittura e modifica, nell'archivio file da utilizzare per l'archivio file del server Chat persistente, ovvero in modo che il generatore di topologie possa configurare gli elenchi DACL necessari oppure un account con diritti equivalenti.

    
    </div>

2.  Avviare Generatore di topologie.

3.  Nell'albero della console, passare al nodo **pool di chat persistente** ed espanderlo per selezionare un pool di server Chat persistente oppure fare clic con il pulsante destro del mouse sul nodo e scegliere **nuovo pool di chat persistente**. È necessario definire il nome di dominio completo (FQDN) del pool, e indicare se il pool sarà una distribuzione a server singolo o a server multiplo.
    
    È possibile scegliere un **Pool di più computer** o un **Pool computer singolo**. Scegliere il primo se si prevede di avere più di un server front-end del server Chat persistente nel pool di server Chat persistente. Questa selezione deve essere operata subito o in seguito, poiché se si crea un pool computer singolo, non è possibile aggiungervi altri server in seguito. Se si sceglie un pool di più computer, immettere i nomi dei singoli server front end server di Persistent Chat che costituiscono il pool.
    
    <div>
    

    > [!IMPORTANT]  
    > Se il ruolo del server Chat persistente è in fase di installazione in un server Lync Server 2013 &nbsp; Standard Edition, il nome FQDN deve corrispondere al nome di dominio completo del server Standard Edition.

    
    </div>

4.  Definire un **nome visualizzato** semplice per il pool di server Chat persistente. Il nome visualizzato può essere utilizzato dai client personalizzati, in particolare quando sono presenti più pool di server Chat persistente, per differenziare le sale.

5.  Definire la porta utilizzata dal server Chat persistente per comunicare con i server front end di Lync Server. Per impostazione predefinita, viene utilizzata la porta 5041.

6.  Se l'organizzazione richiede il supporto della conformità, selezionare la casella di controllo **Abilita conformità**. Se si sceglie, il servizio di conformità del server Chat persistente viene installato nello stesso computer del server front end server di chat persistente. Viene richiesto di selezionare un server back-end SQL Server per la conformità del server Chat persistente in un secondo momento.

7.  Assegnare l'affinità dei siti per il pool di server Chat persistente. Selezionare la casella di controllo **utilizza questo pool come \<SiteName\> ** predefinito per il sito oppure **utilizzare questo pool come predefinito per tutti i siti** per designare il pool di server Chat persistente come pool predefinito per il sito corrente o per tutti i siti. Quando il client Lync 2013 viene utilizzato per creare e gestire le chat room, il pool predefinito associato al sito dell'utente viene utilizzato dall'esperienza di creazione e gestione della sala in modo che sia possibile instradare le operazioni di creazione e gestione della sala in tale pool. Questo valore si applica solo quando si dispone di più pool di server Chat persistente e si desidera utilizzare le funzionalità di creazione e gestione delle chat del server Persistent.
    
    <div>
    

    > [!IMPORTANT]  
    > È possibile personalizzare le funzionalità di creazione e gestione della sala utilizzando il Software Development Kit (SDK) di Persistent Chat Server.<BR>Per informazioni dettagliate su come configurare i database di backup di SQL Server per il ripristino di emergenza, vedere <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for High Availability and Disaster Recovery in Lync server 2013</A> nella documentazione relativa alla distribuzione.

    
    </div>

8.  Definire l' **Archivio SQL per il back-end del server Chat persistente (in cui è archiviato il contenuto della chat room)** eseguendo una delle operazioni seguenti:
    
      - Per utilizzare un database di SQL Server esistente, nell'elenco a discesa fare clic sul nome del database di SQL Server che si desidera utilizzare.
    
      - Per specificare un nuovo database di SQL Server, fare clic su **nuovo**e in **Definisci nuovo archivio SQL**, eseguire le operazioni seguenti:
    
    <!-- end list -->
    
      - In **FQDN SQL Server**specificare il nome di dominio completo di SQL Server in cui si desidera creare il nuovo database di SQL Server.
    
      - Selezionare **Istanza predefinita** per utilizzare un'istanza predefinita oppure **Istanza denominata** per specificare un'istanza diversa, quindi specificare l'istanza che si desidera utilizzare.

9.  Se è stata abilitata la conformità, definire il database di conformità di SQL Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Per informazioni dettagliate su come configurare i mirror di SQL Server per la disponibilità elevata per il database del server Chat persistente e il database di conformità del server Chat persistente, vedere <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for High Availability and Disaster Recovery in Lync server 2013</A> nella documentazione relativa alla distribuzione.

    
    </div>

10. Definire l'archivio file. Un archivio file è una cartella in cui è archiviata una copia di qualunque file caricato nell'archivio dei file (ad esempio, gli allegati pubblicati in una chat room). Nel caso di una topologia del server Chat persistente a più server, deve essere un percorso UNC (Universal Naming Convention). per una topologia del server Chat persistente a server singolo, può essere un percorso di file locale.
    
    Per utilizzare un archivio file esistente, eseguire le operazioni seguenti:
    
      - In **FQDN file server**, specificare l'FQDN dell'archivio file in cui si desidera creare il nuovo archivio file.
    
      - In **Condivisione file**, specificare l'archivio file che si desidera utilizzare.
    
    <div>
    

    > [!IMPORTANT]  
    > È possibile definire l'archivio file in Generatore di topologie prima di creare l'archivio file, ma è necessario creare l'archivio file nel percorso definito prima di pubblicare la topologia.

    
    </div>

11. Selezionare il pool Front End Server da utilizzare come hop successivo per il pool di server Chat persistente. Si tratta del pool Front End Server che sarà in grado di instradare le richieste del server Chat persistente al pool.

12. Per salvare la configurazione, fare clic su **Fine**. Il pool di server Chat persistente viene visualizzato in Generatore di topologie accompagnato dalle impostazioni del pool specifiche.
    
    Per pubblicare la topologia aggiornata in cui è presente il server Chat persistente, vedere [pubblicare la topologia aggiornata in Lync server 2013](lync-server-2013-publish-the-updated-topology.md) nella documentazione relativa alla distribuzione.
    
    <div>
    

    > [!NOTE]  
    > Con generatore di topologie già aperto, è possibile procedere con il passaggio 3 in <A href="lync-server-2013-publish-the-updated-topology.md">pubblicare la topologia aggiornata in Lync Server 2013</A> per iniziare a pubblicare la topologia aggiornata.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

