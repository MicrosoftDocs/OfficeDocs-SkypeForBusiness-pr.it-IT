---
title: 'Lync Server 2013: configurare il clustering di SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21fac13a22e2b2acf400ca154551a0705544644f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535213"
---
# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>Configurare il clustering di SQL Server per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-01-10_

Microsoft Lync Server 2013 supporta il clustering per SQL Server 2012 e SQL Server 2008 R2. Per informazioni dettagliate su ciò che è supportato, vedere [database software support in Lync Server 2013](lync-server-2013-database-software-support.md).

È necessario impostare e configurare il cluster di SQL Server prima di installare e distribuire Enterprise Edition Front End Server e database back-end. Per le procedure consigliate e le istruzioni di installazione per il clustering di failover in SQL Server 2012, vedere <https://technet.microsoft.com/library/hh231721.aspx> . Per il clustering di failover in SQL Server 2008, vedere <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .

Quando si installa SQL Server, è consigliabile installare SQL Server Management Studio per gestire i percorsi dei file di database e di registro. SQL Server Management Studio viene installato come componente facoltativo quando si installa SQL Server.

<div>


> [!IMPORTANT]  
> Per installare e distribuire i database nel server basato su SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per il server basato su SQL Server in cui si installano i file di database. Se non si è membri del gruppo sysadmin di SQL Server, sarà necessario richiedere di essere aggiunti a tale gruppo finché non verranno distribuiti i file di database. Se non è possibile diventare membri del gruppo sysadmin, fornire all'amministratore del database di SQL Server lo script per configurare e distribuire i database. Per informazioni dettagliate sui diritti utente e le autorizzazioni appropriati necessari per eseguire le procedure, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>Per configurare il clustering di SQL Server

1.  Dopo aver completato l'installazione e la configurazione del clustering di SQL Server, è necessario definire l'archivio SQL Server in Generatore di topologie utilizzando il nome del cluster virtuale dell'istanza di SQL Server (come configurato nel programma di installazione per il clustering di SQL Server) e il nome dell'istanza del database di SQL Server. A differenza di un server basato su SQL Server singolo, per un server basato su SQL Server in cluster verrà utilizzato il nome di dominio completo (FQDN) del nodo virtuale.
    
    <div>
    

    > [!NOTE]  
    > I singoli nodi del cluster di Windows Server non devono essere configurati per il generatore di topologie. Verrà utilizzato solo il nome del cluster di SQL Server virtuale.

    
    </div>

2.  Se si utilizza il generatore di topologie per distribuire i database, è necessario essere membri del gruppo sysadmin di SQL Server. Se si è membri del gruppo sysadmin di SQL Server, ma non si dispone di privilegi nel dominio (ad esempio, un ruolo di amministratore di database di SQL Server), si dispone dei diritti necessari per creare i database, ma non per leggere le informazioni necessarie in Lync Server. Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per la distribuzione di Lync Server, vedere [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Verificare che le impostazioni predefinite delle cartelle dei database e dei file di registro siano mappate correttamente ai dischi condivisi nel cluster di SQL Server utilizzando SQL Server Management Studio. Questa è una procedura obbligatoria se i database verranno creati utilizzando Generatore di topologie.
    
    <div>
    

    > [!NOTE]  
    > Se non è stato installato SQL Server Management Studio, è possibile installarlo eseguendo di nuovo l'installazione di SQL Server e quindi selezionando lo strumento di gestione come funzionalità aggiunta per la distribuzione di SQL Server esistente.

    
    </div>

4.  Installare i database per il server basato su SQL Server utilizzando il generatore di topologie o i cmdlet di Windows PowerShell. Per utilizzare Generatore di topologie, eseguire la procedura seguente. Per utilizzare i cmdlet di Windows PowerShell, vedere [installazione di database mediante Lync Server Management Shell in Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>Per creare database tramite Generatore di topologie

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.
    
    <div>
    

    > [!WARNING]  
    > La procedura seguente presuppone che sia stata definita e configurata la topologia in Generatore di topologie. Per informazioni dettagliate sulla definizione della topologia, vedere<A href="lync-server-2013-defining-and-configuring-the-topology.md">define and Configuring the topologie in Lync Server 2013</A>. Per utilizzare Generatore di topologie per la pubblicazione della topologia e la configurazione del database, è necessario eseguire l'accesso in qualità di utente con appartenenze a gruppi e diritti appropriati. Per informazioni dettagliate sui diritti e le appartenenze ai gruppi richiesti, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.

    
    </div>

2.  In Generatore di topologie, durante la pubblicazione della topologia, nella pagina **Crea database** fare clic su **Avanzate**.

3.  Nella pagina **Seleziona percorso file di database** sono disponibili due opzioni per determinare come verranno distribuiti i file di database nel cluster di SQL Server. Seleziona una delle opzioni seguenti:
    
      - **Determina automaticamente il percorso del file di database.** Verrà utilizzato un algoritmo per determinare i percorsi dei file di dati e di registro del database in base alla configurazione delle unità nel server basato su SQL Server. I file verranno distribuiti in modo da tentare di fornire prestazioni ottimali.
    
      - Utilizza i valori predefiniti dell'istanza di SQL Server. Selezionando questa opzione, i file di dati e di registro verranno installati in base alle impostazioni dell'istanza di SQL Server. Dopo la distribuzione dei file di database in SQL Server, è possibile che l'amministratore di database di SQL Server desideri riposizionare i file in modo da ottimizzare le prestazioni in base a requisiti di configurazione di SQL Server specifici.

4.  Completare la pubblicazione della topologia e controllare che non si siano verificati errori durante l'operazione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

