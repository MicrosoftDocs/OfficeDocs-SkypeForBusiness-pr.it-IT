---
title: Rimuovere database e istanze di SQL Server nel server back-end
description: Rimuovere le istanze e i database di SQL Server nel server back-end.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c87426a3496e6def2ad65775f5dadb1a0141ae3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551282"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Rimuovere database e istanze di SQL Server nel server back-end

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

È possibile rimuovere i database e le istanze di Microsoft SQL Server dopo aver rimosso i server che eseguono Lync Server 2010 che dipendono da essi o dopo aver riconfigurato i server che eseguono Lync Server 2010 per utilizzare un altro database. È necessario eseguire la procedura descritta in questo argomento quando si ritira l'oggetto SQL Server corrente o si riconfigura il server corrente che esegue Lync Server 2010 in modo che esegua il rendering dei database obsoleti o non disponibili.

Per rimuovere i database o le istanze per il server di archiviazione o il Monitoring Server, è innanzitutto necessario rimuovere il ruolo del server. Analogamente, per rimuovere le istanze o i database per il pool Front End, è necessario prima rimuovere o riconfigurare il ruolo del server dipendente. Per queste procedure non viene fatta distinzione tra database collocati o istanze separate dei server. La collocazione dei database non incide sulle procedure.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Rimuovere il database di SQL Server per un pool Front End](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Rimuovere il database di SQL Server per un server di monitoraggio](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Rimuovere il database di SQL Server per un server di archiviazione](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

