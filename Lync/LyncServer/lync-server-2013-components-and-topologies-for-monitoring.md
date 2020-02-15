---
title: 'Lync Server 2013: componenti e topologie per il monitoraggio'
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
ms.openlocfilehash: 065cab8b4db7ecbc764ab8a8c6168c88fe1afd50
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Componenti e topologie per il monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-05_

Poiché gli agenti di raccolta dati unificati vengono installati e attivati automaticamente su ogni Front End Server, non è necessario configurare un server per agire come Monitoring Server. ogni Front End Server funziona già come Monitoring Server. Tuttavia, è necessario installare e configurare un database in modo che funga da archivio dati back-end per i dati di monitoraggio. Microsoft Lync Server 2013 può utilizzare uno dei database seguenti come archivio back-end per il monitoraggio:

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

Tenere presente che è necessario utilizzare le edizioni a 64 bit di questi database; le versioni a 32 bit di SQL Server non possono essere utilizzate come archivio back-end per il monitoraggio. Analogamente, Lync Server 2013 non supporta le edizioni Express di SQL Server 2008 o SQL Server 2012. Per ulteriori informazioni sui requisiti di database per Lync Server 2013, vedere l'argomento [supporto software per database in Lync server 2013](lync-server-2013-database-software-support.md) nella Guida alla supportabilità di lync Server 2013.

Tenere presente che SQL Server deve essere installato e configurato prima di distribuire e configurare il monitoraggio. Tuttavia, è necessario solo distribuire SQL Server stesso. non è necessario configurare i database di monitoraggio in anticipo. Al contrario, i database verranno creati automaticamente quando si pubblica la topologia di Lync Server.

I dati di monitoraggio possono condividere un'istanza di SQL Server con altri tipi di dati. In genere, il database di registrazione dettagli chiamata (LcsCdr) e il database Quality of Experience (QoEMetrics) condividono la stessa istanza SQL. è inoltre comune che i due database di monitoraggio si trovino nella stessa istanza di SQL del database di archiviazione (LcsLog). Informazioni sull'unico requisito reale con le istanze di SQL Server è che una qualsiasi istanza di SQL Server è limitata alla seguente:

  - Un'istanza del database back-end di Lync Server 2013. (Come regola generale, non è consigliabile che il database di monitoraggio sia collocato nella stessa istanza SQL o anche nello stesso computer, come database back-end. Anche se tecnicamente possibile, si corre il rischio che il database di monitoraggio utilizzi lo spazio su disco necessario per il database back-end.

  - Un'istanza del database di registrazione dettagli chiamata.

  - Un'istanza del database Quality of Experience.

  - Un'istanza del database di archiviazione.

In altre parole, non è possibile avere due istanze del database di LcsCdr nella stessa istanza di SQL Server. Se sono necessarie più istanze del database di LcsCdr, sarà necessario configurare più istanze di SQL Server.

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione del monitoraggio in Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

