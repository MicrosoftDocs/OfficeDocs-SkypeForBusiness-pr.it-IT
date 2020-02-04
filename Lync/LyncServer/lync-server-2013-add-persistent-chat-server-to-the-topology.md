---
title: 'Lync Server 2013: Aggiungere il server Chat persistente alla topologia'
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
ms.openlocfilehash: 53f8c65f561a0f2c7b1937d60344c0177d221ba8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>Aggiungere il server Chat persistente alla topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-06_

È necessario incorporare Lync Server 2013, il supporto del server di chat persistente nella topologia prima di poter configurare la distribuzione per supportare il server di chat persistente. Le informazioni contenute in questo argomento illustrano come usare generatore di topologia per aggiungere il supporto del server di chat persistente alla topologia esistente.

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>Per aggiungere un server di chat persistente a una topologia

Eseguire la procedura seguente per installare un singolo pool di server di chat persistente senza una configurazione di ripristino di emergenza. Per configurare un pool di server di chat persistente esteso per l'elevata disponibilità e il ripristino di emergenza, vedere [configurazione del server di chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) nella documentazione relativa alla distribuzione.

Per distribuire più pool di server di chat persistenti, ripetere lo stesso processo per ogni pool.

1.  In un computer che esegue Lync Server 2013 o in cui sono installati gli strumenti di amministrazione di Lync Server, accedere con un account membro del gruppo utenti locali o un account con diritti utente equivalenti.
    
    <div>
    

    > [!NOTE]  
    > Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma per pubblicare una topologia, necessaria per installare un Server 2013 di Lync Server, è necessario usare un account che sia un membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> e che disponga delle autorizzazioni di controllo completo (ovvero, lettura, scrittura e modifica) nell'archivio di file che si vuole usare per il file Store del server di chat persistente, in modo che il generatore di topologia possa configurare gli elenchi DACL necessari. o un account con diritti equivalenti.

    
    </div>

2.  Avviare Generatore di topologie.

3.  Nell'albero della console passare al nodo **pool di chat persistente** ed espanderlo per selezionare un pool di server di chat persistente oppure fare clic con il pulsante destro del mouse sul nodo e scegliere **nuovo pool di chat persistente**. È necessario definire il nome di dominio completo (FQDN) del pool e indicare se il pool sarà un pool a server singolo o un pool di distribuzione a più server.
    
    È possibile scegliere un **pool di computer multipli** o un **singolo pool di computer**. Scegliere il primo se si prevede di avere più di un server front end server di chat persistente nel pool del server di chat persistente. Fare questa scelta ora o in un secondo momento, perché dopo aver creato un singolo pool di computer non è possibile aggiungervi altri server in un secondo momento. Se si sceglie un pool di computer multipli, immettere i nomi dei singoli server front-end del server di chat persistente che costituiscono il pool.
    
    <div>
    

    > [!IMPORTANT]  
    > Se il ruolo del server di chat persistente viene installato in un server&nbsp;Lync Server 2013 Standard Edition, l'FQDN deve corrispondere al nome di dominio completo del server Standard Edition.

    
    </div>

4.  Definire un **nome visualizzato** semplice per il pool di server di chat persistente. Il nome visualizzato può essere usato dai client personalizzati, in particolare quando sono presenti più pool di server di chat persistenti per distinguere le sale.

5.  Definire la porta utilizzata dal server di chat persistente per comunicare con i server front-end di Lync Server. La porta predefinita è 5041.

6.  Se l'organizzazione richiede il supporto della conformità, selezionare la casella di controllo **Abilita conformità** . Se scelto, il servizio di conformità del server di chat persistente viene installato nello stesso computer del server front end del server di chat persistente. Viene richiesto di selezionare un server di SQL Server back-end per la conformità del server di chat persistente in un secondo momento.

7.  Assegnare l'affinità del sito per il pool del server di chat persistente. Selezionare la casella di controllo **Usa il pool come \<predefinito\> per il sito SiteName** o **usare questo pool come predefinito per tutti i siti** per designare questo pool di server di chat persistente come pool predefinito per il sito corrente o per tutti i siti. Quando il client Lync 2013 viene usato per creare e gestire le sale, il pool predefinito associato al sito dell'utente viene usato dall'esperienza di creazione e gestione della sala in modo che possa instradare le operazioni di creazione e gestione della sala in tale pool. Questo problema si applica solo quando sono distribuiti più pool di server di chat persistenti e si vogliono usare le caratteristiche di creazione e gestione della sala del server di chat persistente.
    
    <div>
    

    > [!IMPORTANT]  
    > È possibile personalizzare le caratteristiche di creazione e gestione della sala usando il Software Development Kit (SDK) di Persistent Chat Server.<BR>Per informazioni dettagliate su come configurare i database di backup di SQL Server per il ripristino di emergenza, vedere <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">configurazione del server di chat persistente per l'elevata disponibilità e ripristino di emergenza in Lync Server 2013</A> nella documentazione relativa alla distribuzione.

    
    </div>

8.  Definire l' **Archivio SQL per il back-end del server di chat persistente (in cui è archiviato il contenuto della chat room)** eseguendo una delle operazioni seguenti:
    
      - Per usare un database di SQL Server esistente, nell'elenco a discesa fare clic sul nome del database di SQL Server che si vuole usare.
    
      - Per specificare un nuovo database di SQL Server, fare clic su **nuovo**e quindi, in **Definisci nuovo archivio SQL**, eseguire le operazioni seguenti:
    
    <!-- end list -->
    
      - In **FQDN di SQL Server**specificare il nome di dominio completo di SQL Server in cui si vuole creare il nuovo database di SQL Server.
    
      - Selezionare l'istanza **predefinita** per usare l'istanza predefinita oppure, per specificare un'istanza diversa, selezionare **istanza denominata**e specificare l'istanza che si vuole usare.

9.  Definire il database di conformità di SQL Server se è stata abilitata la conformità.
    
    <div>
    

    > [!IMPORTANT]  
    > Per informazioni dettagliate su come configurare i mirror di SQL Server per una disponibilità elevata per il database del server di chat persistente e per il database di conformità persistente per il server di chat, vedere <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">configurazione del server di chat persistente per l'elevata disponibilità e ripristino di emergenza in Lync server 2013</A> nella documentazione sulla distribuzione

    
    </div>

10. Definire l'archivio di file. Un archivio file è una cartella in cui è archiviata una copia di un file caricato nel repository del file, ad esempio l'archiviazione di file allegati inviati in una chat room. Nel caso di una topologia del server di chat persistente a più server, questo deve essere un percorso UNC (Universal Naming Convention). e per una topologia del server di chat persistente a singolo server, può essere un percorso di file locale.
    
    Per usare un archivio file esistente, eseguire la procedura seguente:
    
      - In **FQDN file server**specificare il nome di dominio completo dell'archivio di file in cui si vuole creare il nuovo archivio di file.
    
      - In **condivisione file**specificare l'archivio di file che si vuole usare.
    
    <div>
    

    > [!IMPORTANT]  
    > È possibile definire l'archivio di file in Generatore di topologie prima di creare l'archivio di file, ma è necessario creare l'archivio file nella posizione definita che si definisce prima di pubblicare la topologia.

    
    </div>

11. Selezionare il pool del server front-end da usare come hop successivo per il pool di server di chat persistente. Si tratta del pool Front-End Server che sarà in grado di instradare le richieste del server di chat persistente al pool.

12. Per salvare la configurazione, fare clic su **fine**. Il pool di server di chat persistente viene visualizzato in Generatore di topologia accompagnato dalle impostazioni specifiche del pool.
    
    Per pubblicare ora la topologia aggiornata in cui si è installato il server di chat persistente, vedere [pubblicare la topologia aggiornata in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) nella documentazione relativa alla distribuzione.
    
    <div>
    

    > [!NOTE]  
    > Con generatore di topologia già aperto, è possibile procedere con il passaggio 3 della <A href="lync-server-2013-publish-the-updated-topology.md">pubblicazione della topologia aggiornata in Lync Server 2013</A> per iniziare a pubblicare la topologia aggiornata.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

