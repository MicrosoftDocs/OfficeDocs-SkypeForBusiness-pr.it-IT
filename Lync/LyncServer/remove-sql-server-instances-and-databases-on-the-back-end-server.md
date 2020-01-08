---
title: Rimuovere database e istanze di SQL Server nel server back-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f03a318e81b839d5f92dbaa4ddcc70bbbc8e2e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Rimuovere database e istanze di SQL Server nel server back-end

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Si rimuovono i database e le istanze di Microsoft SQL Server dopo aver rimosso i server in cui è in uso Lync Server 2010, o dopo aver riconfigurato i server che usano Lync Server 2010 per usare un altro database. È necessario eseguire la procedura descritta in questo argomento quando si ritira il server SQL corrente o si riconfigura il server corrente che esegue Lync Server 2010 in modo che esegua il rendering dei database obsoleti o non disponibili.

Per rimuovere i database o le istanze per il server di archiviazione o il server di monitoraggio, è necessario prima di tutto rimuovere il ruolo del server. Allo stesso modo, per rimuovere le istanze o i database per il pool Front-End, devi prima rimuovere o riconfigurare il ruolo del server dipendente. Queste procedure non fanno distinzione tra database collocati o istanze separate per i server. Le procedure non sono influenzate dalla collocazione dei database.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Rimuovere il database di SQL Server per un pool Front End](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Rimuovere il database di SQL Server per un server di monitoraggio](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Rimuovere il database di SQL Server per un server di archiviazione](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

