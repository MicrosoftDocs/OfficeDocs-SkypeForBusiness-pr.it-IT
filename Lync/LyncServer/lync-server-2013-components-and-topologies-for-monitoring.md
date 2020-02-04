---
title: 'Lync Server 2013: Componenti e topologie per il monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76e857d0c80793f61b8e60686cc9455d27bb9f95
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Componenti e topologie per il monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-05_

Dato che gli agenti di raccolta dati unificati vengono installati e attivati automaticamente in ogni server front-end, non è necessario configurare un server per fungere da server di monitoraggio. ogni server front-end funziona già come server di monitoraggio. Sarà tuttavia necessario installare e configurare un database per fungere da archivio dati back-end per i dati di monitoraggio. Microsoft Lync Server 2013 può usare uno dei database seguenti come archivio back-end per il monitoraggio:

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

Si noti che è necessario usare le edizioni a 64 bit di questi database. le versioni a 32 bit di SQL Server non possono essere usate come archivio back-end per il monitoraggio. Allo stesso modo, Lync Server 2013 non supporta le edizioni Express di SQL Server 2008 o SQL Server 2012. Per altre informazioni sui requisiti di database per Lync Server 2013, vedere l'argomento [supporto software per database in Lync server 2013](lync-server-2013-database-software-support.md) nella Guida alla supportabilità di lync Server 2013.

Tieni presente che SQL Server deve essere installato e configurato prima di distribuire e configurare il monitoraggio. È tuttavia necessario distribuire solo SQL Server. non è necessario configurare preventivamente i database di monitoraggio. I database verranno invece creati automaticamente quando si pubblica la topologia di Lync Server.

I dati di monitoraggio possono condividere un'istanza di SQL Server con altri tipi di dati. In genere, il database di registrazione dei dettagli delle chiamate (LcsCdr) e la qualità del database di Experience (QoEMetrics) condividono la stessa istanza SQL. è inoltre comune che i due database di monitoraggio siano nella stessa istanza SQL del database di archiviazione (LcsLog). Informazioni sull'unico requisito reale delle istanze di SQL Server è che una qualsiasi istanza di SQL Server è limitata alle seguenti:

  - Un'istanza del database back-end di Lync Server 2013. Come regola generale, non è consigliabile che il database di monitoraggio sia collocato nella stessa istanza SQL o anche nello stesso computer, come database back-end. Anche se tecnicamente è possibile, si corre il rischio che il database di monitoraggio usi lo spazio su disco necessario per il database back-end.

  - Un'istanza del database di registrazione dei dettagli delle chiamate.

  - Un'istanza del database Quality of Experience.

  - Un'istanza del database di archiviazione.

In altre parole, non è possibile avere due istanze del database LcsCdr nella stessa istanza di SQL Server. Se sono necessarie più istanze del database di LcsCdr, sarà necessario configurare più istanze di SQL Server.

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione del monitoraggio in Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

