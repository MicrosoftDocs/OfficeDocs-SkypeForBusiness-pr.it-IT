---
title: 'Lync Server 2013: Supporto per il software di database'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4c39a51f742266c12f618f687c23c645977ffdb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Supporto per il software di database in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-12-01_

Lync Server 2013 supporta i sistemi di gestione dei database seguenti:

  - **Database back-end di un pool Front End, database di archiviazione, database di monitoraggio, database di chat persistente e database di conformità di chat persistente**
    
      - Software di database di Microsoft SQL Server 2008 R2 Enterprise (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.
    
      - Microsoft SQL Server 2008 R2 Standard (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.
    
      - Microsoft SQL Server 2012 Enterprise (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.
    
      - Microsoft SQL Server 2012 Standard (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.

  - **Database server Standard Edition e database front end server**
    
      - Microsoft SQL Server 2012 Express (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.
        
        Supportiamo le patch e l'aggiornamento di Microsoft SQL Server nei server front-end e nei server Standard Edition. Tuttavia, quando effettui un qualsiasi tipo di aggiornamento o patch per i server front-end, devi tenere conto dei requisiti del quorum. Per altre informazioni, vedere [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) e [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64 bit Edition) viene installato automaticamente da Lync Server 2013 in ogni server Standard Edition e ogni server front-end server.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 non supporta l'edizione a 32 bit di SQL Server. È necessario utilizzare l'edizione a 64 bit.</P>
> <LI>
> <P>SQL Server Web Edition e SQL Server Workgroup Edition non sono supportati. Non è possibile usarli con Lync Server 2013.</P>
> <LI>
> <P>Lync Server 2013 supporta il mirroring nativo del database.</P>
> <LI>
> <P>Per usare il ruolo del server di monitoraggio, è necessario installare SQL Server Reporting Services.</P></LI></UL>



</div>

In un pool Front-end il database back-end può essere un singolo computer SQL Server.

<div>


> [!IMPORTANT]  
> Se si collocano i database di Lync Server con altri database, è consigliabile valutare tutti i fattori che possono influire sulla disponibilità e sulle prestazioni, oltre a garantire che, se un nodo non riesce, il nodo rimanente può gestire il carico. Per verificare le funzionalità di failover, è consigliabile testare tutti i possibili scenari.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>Uso del mirroring e del clustering SQL

Lync Server 2013 supporta l'uso del mirroring SQL o del clustering SQL per ogni database di Lync Server. È possibile configurare facilmente il mirroring SQL con lo strumento generatore di topologia in Lync Server 2013. Per la configurazione del clustering di failover SQL, è necessario usare SQL Server.

Lync Server 2013 supporta sia il mirroring SQL che le topologie di clustering SQL per tutte le distribuzioni, incluse le distribuzioni Greenfield e le organizzazioni che hanno eseguito l'aggiornamento dalle versioni precedenti di Lync Server.

Il supporto per il clustering SQL è per una configurazione attiva o passiva. Per motivi legati alle prestazioni, il nodo passivo non deve essere condiviso con un'altra istanza SQL.

È incluso il supporto seguente:

  - Clustering di failover a due nodi per:
    
      - Microsoft SQL Server 2012 Standard (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.
    
      - Microsoft SQL Server 2008 R2 Standard (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.

  - Clustering di failover con fino a sedici nodi per:
    
      - Microsoft SQL Server 2012 Enterprise (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.
    
      - Software di database di Microsoft SQL Server 2008 R2 Enterprise (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.

Per altre informazioni sul mirroring SQL, vedere [back-end server high availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md). Per informazioni dettagliate su come distribuire il clustering SQL, vedere [configurare il clustering di SQL Server per Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).

Per altre informazioni e procedure consigliate per il clustering di failover in SQL Server <http://technet.microsoft.com/en-us/library/hh231721.aspx>2012, vedere. Per il clustering di failover in SQL Server 2008 <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>, vedere.

</div>

</div>

<span> </span>

</div>

</div>

</div>

