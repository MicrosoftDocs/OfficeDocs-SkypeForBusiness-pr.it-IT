---
title: 'Lync Server 2013: componenti e topologie per il server di chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ae22b2afed27109fb6e2c514211293cef42a46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Componenti e topologie per il server di chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

Il server di chat persistente supporta sia configurazioni a server singolo che configurazioni multiple-server. Il server di chat persistente può essere eseguito anche in un server Lync Server 2013 Standard Edition. Queste configurazioni sono costituite dai componenti e topologie del server di chat persistente seguenti.

<div>

## <a name="persistent-chat-server-components"></a>Componenti del server di chat persistente

L'installazione della versione più recente di Persistent Chat Server richiede i componenti seguenti:

  - Uno o più computer che eseguono il server di chat persistente e forniscono i servizi seguenti:
    
      - Servizio chat persistente
    
      - Servizio conformità, attivato se è abilitata la conformità
    
    <div>
    

    > [!IMPORTANT]  
    > In Lync Server 2013 i servizi Web di chat persistenti per il caricamento e il download di file sono ora collocati&nbsp;con lync Server 2013 front end server.<BR>I servizi Web di chat persistenti per la gestione delle chat room sono collocati anche&nbsp;con Lync Server 2013 front end server.

    
    </div>

  - Server (più server se si usa il mirroring) che ospitano il database back-end di SQL Server per ospitare il database del contenuto della chat persistente in cui sono archiviati il contenuto della chat room, le camere e le categorie.
    
    <div>
    

    > [!NOTE]  
    > Il database back-end archivia i dati della cronologia delle chat, incluse le informazioni sulle categorie e le chat room persistenti create.

    
    </div>

  - Se è stata abilitata la conformità, un server (più di un server se viene usato il mirroring) che ospita il database back-end di SQL Server per l'hosting del database di conformità della chat persistente, in cui vengono archiviati gli eventi di conformità e il contenuto della chat per lo scopo della conformità.

Per amministrare il server di chat persistente da un computer separato, ad esempio una console di amministrazione, usare il pannello di controllo di Lync Server nel computer. Questo computer deve quindi essere distribuito in un dominio di servizi di dominio Active Directory, con almeno un server di catalogo globale nella radice della foresta.

Per informazioni dettagliate sui requisiti hardware e software per il server di chat persistente, vedere [requisiti tecnici per il server di chat persistente in Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md)e [supporto per software e infrastruttura server in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) nella documentazione relativa alla supportabilità.

</div>

<div>

## <a name="supported-collocation"></a>Collocazione supportata

Lync Server 2013 supporta diversi scenari di collocazione, offrendo la flessibilità necessaria per salvare i costi hardware eseguendo più componenti in un server (se si ha una piccola organizzazione) o per eseguire singoli componenti in server diversi (se si ha un organizzazione più grande che richiede scalabilità e prestazioni). I fattori di scalabilità dovrebbero certamente essere presi in considerazione prima di decidere se collocare i componenti.

Il servizio di conformità della chat persistente, se è abilitata la conformità, è collocato nel server front-end di Lync Server 2013.

Il server di chat persistente può essere distribuito nel server Standard Edition. Il server di back-end del server di chat persistente e il database di conformità della chat persistente possono essere collocati nel server Standard Edition nel server di SQL Server Express back-end locale. Per informazioni dettagliate sui componenti che possono essere collocati in questa posizione, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.

Per Lync Server 2013 Enterprise Edition, i server di chat permanenti non possono essere collocati nel server Enterprise Edition. Il database di SQL Server per il server di chat persistente può essere collocato con il database del server back-end di un pool di front-end Enterprise Edition. Il database di SQL Server per la conformità della chat persistente può essere collocato anche con il database back-end server di un pool di Enterprise Edition.

<div>


> [!IMPORTANT]  
> Il server che ospita il database di chat persistente può ospitare altri database. Tuttavia, se si considera la possibilità di collocare il database di chat persistente con altri database, tenere presente che, se si archiviano i messaggi di più utenti, lo spazio su disco necessario per il database della chat persistente può diventare molto elevato. Per questo motivo, non è consigliabile collocare il database di chat persistente con il database back-end.



</div>

Se si colloca il database di chat persistente con il database back-end, è possibile usare una singola istanza di SQL Server per uno o tutti i database oppure si può usare un'istanza distinta di SQL Server per ogni database, con la limitazione seguente:

  - Ogni istanza di SQL Server può contenere solo un database back-end e un singolo database di chat persistente.

Per informazioni dettagliate sulla collocazione di tutti i ruoli e i database del server, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>Topologie del server di chat persistente

Il server di chat persistente supporta le topologie seguenti:

  - Lync Server 2013 Enterprise Edition single server front end server

  - Lync Server 2013 Enterprise Edition più server front end server di chat persistente

  - Lync Server 2013 Standard Edition server con SQL Server Express

  - Lync Server 2013 Standard Edition Server e il server di chat persistente in un server separato usando il server Standard Edition come server dell'hop successivo.

È possibile aggiungere il server di chat persistente alla distribuzione di Lync Server 2013 tramite Generatore di topologie. È possibile aggiungere un singolo server o un pool di server di chat persistente in più server alla topologia.

<div>


> [!IMPORTANT]  
> Dopo aver creato un pool di server di chat persistente con un singolo server tramite Generatore di topologia, non è possibile aggiungere altri server al pool.



</div>

<div>

## <a name="single-server-topology"></a>Topologia a server singolo

La configurazione minima e la distribuzione più semplice per il server di chat persistente è una singola topologia del server front end del server di chat persistente. Questa distribuzione richiede un singolo server che esegue il server di chat persistente (che facoltativamente esegue il servizio di conformità, se è abilitata la conformità), un server che ospita sia il database di SQL Server che se è necessaria la conformità, il database di SQL Server per archiviare il dati sulla conformità.

<div>


> [!IMPORTANT]  
> Non è possibile aggiungere altri server a un pool di server di chat persistente avviato come distribuzione a server singolo in Generatore di topologie. È consigliabile usare la topologia di pool a più server, anche se si usa un singolo server, in modo che sia possibile aggiungere altri server in un secondo momento, se necessario.



</div>

La figura seguente mostra tutti i componenti obbligatori e facoltativi di una topologia per un singolo server front-end del server di chat persistente con conformità.

**Singolo server di chat persistente**

![Topologia a server singolo con](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "topologia del servizio conformità Single Server con servizio conformità")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologia a più server

Per avere maggiore capacità e affidabilità, è possibile distribuire una topologia a più server, come descritto in [pianificazione per il server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topologia a più server può includere fino a quattro computer attivi che eseguono il server di chat persistente (le configurazioni ad alta disponibilità e ripristino di emergenza consentiranno fino a otto, ma solo quattro possono essere attive e le rimanenti quattro in standby). Ogni server può supportare tutti gli utenti simultanei di 20.000, per un totale di 80.000 utenti simultanei connessi a un pool di server di chat persistente con 4 server. Una topologia a più server è uguale alla topologia a server singolo, ad eccezione del fatto che più server ospitano il server di chat persistente e possono essere ridimensionati in modo più elevato. Più computer che eseguono il server di chat persistente devono risiedere nello stesso dominio di servizi di dominio Active Directory di Lync Server e nel servizio conformità.

La figura seguente mostra tutti i componenti di una topologia a più server con più computer che eseguono il server di chat persistente, il servizio di conformità facoltativo e un database di conformità separato.

**Più server di chat persistenti**

Topologia multiple server(images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "multiple") ![topologia]server

Le topologie con più server consentono di creare pool di funzionalità del server. In un pool di server i servizi di chat persistenti comunicano e condividono i dati. Ad esempio, la cronologia delle chat pubblicata in origine in un servizio di chat persistente è disponibile presso qualsiasi servizio di chat persistente nel sistema. Un file caricato tramite un servizio di chat persistente può essere accessibile da qualsiasi servizio di chat persistente. Gli utenti possono essere connessi a diversi server front end del server di chat persistente e possono essere chattati e comunicanti tra loro.

La porta predefinita di TCP 8011 connette un server a un pool di server e viene usata dal servizio chat persistente per comunicare tra loro o per scopi amministrativi.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

