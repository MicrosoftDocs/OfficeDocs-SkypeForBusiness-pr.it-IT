---
title: Supporto software per database di Lync Server 2013
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
ms.openlocfilehash: da1ffd79ccfb652c0f853cb027577d477a14d33e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Supporto software per database in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-12-01_

Lync Server 2013 supporta i sistemi di gestione dei database seguenti:

  - **Database back-end di un pool Front End, database di archiviazione, database di monitoraggio, database di chat persistente e database di conformità di chat persistente**
    
      - Software di database di Microsoft SQL Server 2008 R2 Enterprise (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.
    
      - Microsoft SQL Server 2008 R2 Standard (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.
    
      - Microsoft SQL Server 2012 Enterprise (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.
    
      - Microsoft SQL Server 2012 Standard (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.

  - **Database del server Standard Edition e database front end server**
    
      - Microsoft SQL Server 2012 Express (versione 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.
        
        È supportata l'applicazione di patch e l'aggiornamento di Microsoft SQL Server nei front end server e nei server Standard Edition. Tuttavia, quando si esegue qualsiasi tipo di aggiornamento o patch nei Front End Server, è necessario tenere conto dei requisiti di quorum. Per ulteriori informazioni, vedere [aggiornare o aggiornare Front End Server in Lync server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) e [topologie e componenti per Front End Server, messaggistica istantanea e presenza in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (versione 64 bit) viene installato automaticamente da Lync Server 2013 in ogni server Standard Edition e in ogni server front end server.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 non supporta l'edizione a 32 bit di SQL Server. È necessario utilizzare l'edizione a 64 bit.</P>
> <LI>
> <P>SQL Server Web Edition e SQL Server Workgroup Edition non sono supportati. Non è possibile utilizzarli con Lync Server 2013.</P>
> <LI>
> <P>Lync Server 2013 supporta il mirroring del database nativo.</P>
> <LI>
> <P>Per utilizzare il ruolo Monitoring Server, è necessario installare SQL Server Reporting Services.</P></LI></UL>



</div>

In un pool Front End, il database back-end può essere un singolo computer SQL Server.

<div>


> [!IMPORTANT]  
> Se si installano i database di Lync Server con altri database, è consigliabile valutare tutti i fattori che possono influire sulla disponibilità e sulle prestazioni, nonché garantire che, se un nodo ha esito negativo, il nodo rimanente può gestire il carico. Per verificare le capacità di failover, è consigliabile testare tutti gli scenari di failover.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>Utilizzo del mirroring SQL e del clustering SQL

Lync Server 2013 supporta l'utilizzo del mirroring SQL o del clustering SQL per ogni database di Lync Server. È possibile configurare facilmente il mirroring SQL con lo strumento generatore di topologie in Lync Server 2013. Per il clustering di failover SQL, è necessario utilizzare SQL Server per il programma di installazione.

Lync Server 2013 supporta sia il mirroring SQL che le topologie di clustering SQL per tutte le distribuzioni, incluse le distribuzioni Greenfield e le organizzazioni che hanno eseguito l'aggiornamento dalle versioni precedenti di Lync Server.

Il supporto per il clustering di SQL è per una configurazione attiva/passiva. Per motivi di prestazioni, il nodo passivo non deve essere condiviso da un'altra istanza di SQL.

È incluso il supporto seguente:

  - Clustering di failover a due nodi per gli elementi seguenti:
    
      - Microsoft SQL Server 2012 Standard (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.
    
      - Microsoft SQL Server 2008 R2 Standard (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.

  - Clustering di failover fino a sedici nodi per gli elementi seguenti:
    
      - Microsoft SQL Server 2012 Enterprise (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.
    
      - Software di database di Microsoft SQL Server 2008 R2 Enterprise (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.

Per ulteriori informazioni sul mirroring SQL, vedere [back end server high availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md). Per informazioni dettagliate su come distribuire il clustering SQL, vedere [Configure SQL Server clustering for Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).

Per ulteriori informazioni e procedure consigliate per il clustering di failover in SQL Server <http://technet.microsoft.com/library/hh231721.aspx>2012, vedere. Per il clustering di failover in SQL Server 2008 <http://technet.microsoft.com/library/ms189134(v=sql.105).aspx>, vedere.

</div>

</div>

<span> </span>

</div>

</div>

</div>

