---
title: 'Lync Server 2013: componenti e topologie per il server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 320605ab363ff4879811873cc9ce957520b91b29
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Componenti e topologie per il server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-05_

Il server Chat persistente supporta configurazioni a server singolo e configurazioni con più server. Il server Chat persistente può anche essere eseguito su un server Lync Server 2013 Standard Edition. Queste configurazioni sono costituite dai seguenti componenti e topologie del server Chat persistente.

<div>

## <a name="persistent-chat-server-components"></a>Componenti del server Chat persistente

L'installazione della versione più recente del server di chat persistente richiede i componenti seguenti:

  - Uno o più computer che eseguono il server Chat persistente e offrono i servizi seguenti:
    
      - Servizio chat persistente
    
      - Servizio di conformità, attivato se la conformità è abilitata
    
    <div>
    

    > [!IMPORTANT]  
    > In Lync Server 2013, i servizi Web di chat persistente per il caricamento e il download dei file sono ora collocati con Lync Server 2013&nbsp;front end server.<BR>I servizi Web di chat persistente per la gestione delle chat room sono collocati anche&nbsp;con Lync Server 2013 front end server.

    
    </div>

  - Server (più server se si utilizza il mirroring) che ospitano il database back-end di SQL Server per ospitare il database del contenuto di chat persistente in cui vengono archiviati il contenuto delle chat room, le sale e le categorie.
    
    <div>
    

    > [!NOTE]  
    > Nel database back-end sono archiviati i dati della cronologia chat, incluse le informazioni sulle categorie e le chat room persistenti create.

    
    </div>

  - Se la conformità è abilitata, vengono archiviati i server (più server se si utilizza il mirroring) che ospitano il database back-end di SQL Server per ospitare il database di conformità di Persistent Chat, in cui vengono memorizzati gli eventi di conformità e il contenuto della chat ai fini della conformità.

Per amministrare il server Chat persistente da un computer separato, ad esempio una console di amministrazione, utilizzare il pannello di controllo di Lync Server nel computer. Il computer deve quindi essere distribuito in un dominio di servizi di dominio Active Directory, con almeno un server di catalogo globale nella radice della foresta.

Per informazioni dettagliate sui requisiti hardware e software per il server Chat persistente, vedere [requisiti tecnici per il server Chat persistente in Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md)e supporto dell'infrastruttura e del [software server in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) nella documentazione relativa alla supportabilità.

</div>

<div>

## <a name="supported-collocation"></a>Collocazione supportata

Lync Server 2013 supporta una serie di scenari di collocazione, offrendo la flessibilità necessaria per salvare i costi hardware eseguendo più componenti in un server (se si dispone di un'organizzazione di piccole dimensioni) o per eseguire singoli componenti in server diversi (se si dispone di un organizzazione di grandi dimensioni che richiede scalabilità e prestazioni. Prima di decidere se collocare i componenti, è sicuramente importante considerare i fattori di scalabilità.

Il servizio di conformità di Persistent Chat, se la conformità è abilitata, è collocato con il front end server Lync Server 2013.

Il server Chat persistente può essere distribuito nel server Standard Edition. Il server back-end server di chat persistente e il database di conformità di chat persistente possono essere collocati nel server Standard Edition sul server SQL Server Express back-end locale. Per informazioni dettagliate sui componenti che possono essere collocati in tale posizione, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.

Per Lync Server 2013 Enterprise Edition, i server di chat persistente non possono essere collocati nel server Enterprise Edition. Il database di SQL Server per il server Chat persistente può essere collocato con il database del server back-end di un pool Enterprise Edition front end. Il database di SQL Server per la conformità della chat persistente può anche essere collocato con il database del server back-end di un pool Enterprise Edition.

<div>


> [!IMPORTANT]  
> Il server che ospita il database di chat persistente può ospitare altri database. Tuttavia, se si considera la collocazione del database di chat persistente con altri database, tenere presente che se si archiviano i messaggi di più utenti, lo spazio su disco necessario per il database di chat persistente può aumentare molto. Per questo motivo, non è consigliabile collocare il database di Persistent Chat con il database back-end.



</div>

Se si colloca il database di chat persistente con il database back-end, è possibile utilizzare una singola istanza di SQL Server per uno o per tutti i database oppure è possibile utilizzare un'istanza separata di SQL Server per ogni database, con la limitazione seguente:

  - Ogni istanza di SQL Server può contenere solo un singolo database back-end e un singolo database di chat persistente.

Per informazioni dettagliate sulla collocazione di tutti i ruoli del server e dei database, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>Topologie del server Chat persistente

Il server Chat persistente supporta le topologie seguenti:

  - Lync Server 2013 Enterprise Edition single server Persistent Chat Server front end server

  - Lync Server 2013 Enterprise Edition server front end server con più server di chat persistente

  - Lync Server 2013 Standard Edition server con SQL Server Express

  - Lync Server 2013 Standard Edition Server e Persistent Chat Server in un server separato che utilizza il server Standard Edition come server dell'hop successivo.

È possibile aggiungere il server Chat persistente alla distribuzione di Lync Server 2013 utilizzando Generatore di topologie. È possibile aggiungere un singolo server o un pool di server Chat persistente a più server alla topologia.

<div>


> [!IMPORTANT]  
> Dopo aver creato un pool di server Chat persistente con un singolo server utilizzando Generatore di topologie, non è possibile aggiungere altri server al pool.



</div>

<div>

## <a name="single-server-topology"></a>Topologia a server singolo

La configurazione minima e la distribuzione più semplice per il server Chat persistente è una singola topologia del server front-end del server di chat persistente. Questa distribuzione richiede un singolo server che esegue il server Chat persistente (che facoltativamente esegue il servizio di conformità, se la conformità è abilitata), un server che ospita il database di SQL Server e, se è necessaria la conformità, il database di SQL Server per archiviare la dati di conformità.

<div>


> [!IMPORTANT]  
> Non è possibile aggiungere altri server a un pool di server Chat persistente avviato come distribuzione a server singolo in Generatore di topologie. È consigliabile utilizzare la topologia con pool di più server, anche se si utilizza un singolo server, in modo da poter aggiungere ulteriori server in seguito all'occorrenza.



</div>

Nella figura seguente vengono illustrati tutti i componenti obbligatori e facoltativi di una topologia per un singolo server front-end di Persistent Chat Server con conformità.

**Singolo server Persistent Chat**

![Topologia a server singolo con servizio di conformità](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia a server singolo con servizio di conformità")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologia a più server

Per garantire maggiore capacità e affidabilità, è possibile distribuire una topologia a più server, come descritto in [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topologia a più server può includere ben quattro computer attivi che eseguono il server Chat persistente (le configurazioni a disponibilità elevata e ripristino di emergenza consentiranno fino a otto, ma solo quattro possono essere attive e le restanti quattro in standby). Ogni server è in grado di supportare fino a 20.000 utenti simultanei, per un totale di 80.000 utenti simultanei connessi a un pool di server Chat persistente con 4 server. Una topologia a più server è identica alla topologia a server singolo, tranne per il fatto che più server ospitano il server Chat persistente e che possono aumentare la scalabilità verticale. Più computer che eseguono il server Chat persistente devono risiedere nello stesso dominio di servizi di dominio Active Directory come Lync Server e il servizio di conformità.

Nella figura seguente vengono illustrati tutti i componenti di una topologia a più server con più computer che eseguono il server Chat persistente, il servizio di conformità facoltativo e un database di conformità distinto.

**Più server Persistent Chat**

![Topologia a più server](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia a più server")

Le topologie a più server consentono di creare pool delle funzionalità dei server. In un pool di server, i servizi chat persistente comunicano e condividono i dati. Ad esempio, la cronologia delle chat originariamente inviata a un servizio di chat persistente è disponibile da qualsiasi servizio chat persistente nel sistema. È possibile accedere a un file caricato tramite un servizio di chat persistente da qualsiasi servizio chat persistente. Gli utenti possono essere connessi a diversi server front-end di chat persistente e possono chattare e comunicare tra loro.

La porta predefinita di TCP 8011 connette un server a un pool di server e viene utilizzata dal servizio chat persistente per comunicare tra loro o a fini amministrativi.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

