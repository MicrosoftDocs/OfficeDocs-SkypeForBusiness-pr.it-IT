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
ms.openlocfilehash: b63d338e630da93c90b573ac098d47e0929f0d84
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a>Configurare il clustering di SQL Server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-01-10_

Microsoft Lync Server 2013 supporta il clustering per SQL Server 2012 e SQL Server 2008 R2. Per informazioni dettagliate sulle funzionalità supportate, vedere [supporto software per database in Lync Server 2013](lync-server-2013-database-software-support.md).

È consigliabile impostare e configurare il cluster di SQL Server prima di installare e distribuire il server front-end Enterprise Edition e il database back-end. Per le procedure consigliate e le istruzioni di configurazione per il clustering di failover <http://technet.microsoft.com/en-us/library/hh231721.aspx>in SQL Server 2012, vedere. Per il clustering di failover in SQL Server 2008 <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>, vedere.

Quando si installa SQL Server, è necessario installare SQL Server Management Studio per gestire le posizioni per i percorsi dei file di database e di log. SQL Server Management Studio viene installato come componente facoltativo durante l'installazione di SQL Server.

<div>


> [!IMPORTANT]  
> Per installare e distribuire i database nel server basato su SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per il server basato su SQL Server in cui si installano i file di database. Se non si è un membro del gruppo sysadmin di SQL Server, è necessario richiedere che venga aggiunto al gruppo fino a quando non vengono distribuiti i file di database. Se non è possibile creare un membro del gruppo sysadmin, è necessario che l'amministratore di database di SQL Server disponga dello script per la configurazione e la distribuzione dei database. Per informazioni dettagliate sui diritti utente appropriati e sulle autorizzazioni necessarie per eseguire le procedure, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorizzazioni di distribuzione per SQL Server in Lync server 2013</A>.



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a>Per configurare il clustering di SQL Server

1.  Dopo aver completato l'installazione e la configurazione del clustering di SQL Server, è possibile definire l'archivio di SQL Server in Generatore di topologia usando il nome del cluster virtuale dell'istanza di SQL Server (configurato nel clustering per SQL Server) e l'istanza nome del database di SQL Server. Diverso da un singolo server basato su SQL Server, si utilizzerà il nome di dominio completo (FQDN) del nodo virtuale per un server basato su SQL Server in cluster.
    
    <div>
    

    > [!NOTE]  
    > I singoli nodi del cluster Windows Server non devono essere configurati per il generatore di topologie. Si utilizzerà solo il nome del cluster di SQL Server virtuale.

    
    </div>

2.  Se si usa generatore di topologie per distribuire i database, è necessario essere membri del gruppo sysadmin di SQL Server. Se si è un membro del gruppo sysadmin di SQL Server, ma non si hanno privilegi nel dominio, ad esempio un ruolo di amministratore di database di SQL Server, si hanno i diritti per creare i database, ma non per leggere le informazioni necessarie in Lync Server. Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per la distribuzione di Lync Server, vedere [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Verificare che la cartella di database e i file di log predefiniti vengano mappati correttamente ai dischi condivisi nel cluster di SQL Server tramite SQL Server Management Studio. Questa è una procedura obbligatoria se si vuole creare database usando generatore di topologie.
    
    <div>
    

    > [!NOTE]  
    > Se SQL Server Management Studio non è stato installato, è possibile installarlo rieseguendo l'installazione di SQL Server e quindi selezionando lo strumento di gestione come funzionalità aggiunta per la distribuzione di SQL Server esistente.

    
    </div>

4.  Installare i database per il server basato su SQL Server utilizzando il generatore di topologia o i cmdlet di Windows PowerShell. Per usare generatore di topologie, usare la procedura seguente. Per usare i cmdlet di Windows PowerShell, vedere [installazione di database tramite Lync Server Management Shell in Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a>Per creare database tramite Generatore di topologie

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.
    
    <div>
    

    > [!WARNING]  
    > La procedura seguente presuppone che sia stata definita e configurata la topologia in Generatore di topologie. Per informazioni dettagliate sulla definizione della topologia, vedere<A href="lync-server-2013-defining-and-configuring-the-topology.md">definizione e configurazione della topologia in Lync Server 2013</A>. Per usare generatore di topologia per pubblicare la topologia e configurare il database, è necessario accedere come utente con i diritti utente corretti e le appartenenze ai gruppi. Per informazioni dettagliate sui diritti e le appartenenze ai gruppi necessari, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorizzazioni di distribuzione per SQL Server in Lync server 2013</A>.

    
    </div>

2.  In Generatore di topologia, quando si pubblica la topologia, nella pagina **Crea database** fare clic su **Avanzate**.

3.  Nella pagina **Selezione percorso file di database** sono disponibili due opzioni che determinano il modo in cui verranno distribuiti i file di database nel cluster di SQL Server. Selezionare una delle opzioni seguenti:
    
      - **Determinare automaticamente il percorso del file di database.** Questa selezione usa un algoritmo per determinare il log del database e le posizioni dei file di dati in base alla configurazione dell'unità nel server basato su SQL Server. I file verranno distribuiti in modo da provare a ottenere prestazioni ottimali.
    
      - Utilizza i valori predefiniti dell'istanza di SQL Server. Selezionando questa opzione verranno installati i file di log e di dati in base alle impostazioni dell'istanza di SQL Server. Dopo la distribuzione dei file di database a SQL Server, l'amministratore di database di SQL Server potrebbe voler rilocare i file per ottimizzare le prestazioni per i particolari requisiti di configurazione di SQL Server.

4.  Completare la pubblicazione della topologia e verificare che non siano presenti errori durante l'operazione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

