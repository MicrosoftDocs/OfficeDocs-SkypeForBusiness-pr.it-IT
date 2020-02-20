---
title: Collocazione del server Lync Server 2013 in una distribuzione di server Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7390c3cee8be94f6bead96ff990e380b06011eb7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Collocazione dei server in una distribuzione di server Standard Edition per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-20_

In questa sezione vengono descritti i ruoli del server, i database e le condivisioni di file che è possibile collocare in una distribuzione di Lync Server 2013 Standard Edition Server.

<div>

## <a name="server-roles"></a>Ruoli del server

In Lync Server 2013, il servizio A/V Conferencing, il servizio Mediation, il monitoraggio e l'archiviazione sono collocati nel server Standard Edition, ma è necessaria una configurazione aggiuntiva per abilitarli. È possibile scegliere di distribuire il servizio Mediation su server distinti.

È possibile collocare un server applicazioni attendibile con un server Standard Edition.

I ruoli del server seguenti devono essere ognuno distribuito in un computer distinto:

  - Director

  - Server perimetrale

  - Mediation Server (se non collocato con il server Standard Edition)

  - server Office Web Apps

</div>

<div>

## <a name="databases"></a>Database

Per impostazione predefinita, il database back-end di SQL Server Express è collocato nel server Standard Edition. Non è possibile spostarlo in un computer separato. Con un'eccezione, non è possibile collocare altri database nel server Standard Edition. Se si sceglie di distribuire il server Chat persistente in un server Standard Edition, è possibile collocare il database di chat persistente e il database di conformità di Persistent Chat nello stesso server Standard Edition.

È possibile collocare ognuno dei database seguenti in un singolo server di database:

  - Database di monitoraggio

  - Database di archiviazione

  - Un database back-end per un pool Enterprise Edition front end

È possibile collocare uno o più o tutti questi database in una singola istanza di SQL oppure utilizzare istanze SQL separate per ognuna, con le limitazioni seguenti:

  - Ogni istanza SQL può contenere un singolo database back-end (per un pool Enterprise Edition front end), un singolo database di monitoraggio, un singolo database di archiviazione, un singolo database di chat persistente e un singolo database di conformità di Persistent Chat.

  - Il server di database non è in grado di supportare più di un pool Enterprise Edition front end, un server che esegue l'archiviazione, un server che esegue il monitoraggio, un singolo database di chat persistente e un database di conformità di chat persistente, ma può supportarne uno. indipendentemente dal fatto che i database utilizzino la stessa istanza di SQL Server o le istanze separate di SQL Server.

È possibile collocare una condivisione file con i database, come descritto più avanti in questa sezione.

<div>


> [!NOTE]  
> In Lync Server 2013, è possibile integrare l'archiviazione di monitoraggio e archiviazione con Exchange 2013 storage per alcuni o tutti gli utenti nella distribuzione. Non è possibile distribuire i server che eseguono Lync Server o i componenti negli stessi server dell'archivio di Exchange.



</div>

<div>


> [!IMPORTANT]  
> Sebbene la collocazione dei database sia supportata, la dimensione dei database può aumentare rapidamente. Ad esempio, se si intende collocare il database di archiviazione con altri database, è opportuno tenere presente che l'archiviazione dei messaggi di più utenti può comportare un notevole aumento dello spazio su disco richiesto dal database di archiviazione. Per questo motivo, non è consigliabile collocare più database, in particolare il database di archiviazione, il database di chat persistente e il database di conformità di Persistent Chat con il database back-end di un pool Enterprise.



</div>

</div>

<div>

## <a name="file-shares"></a>Condivisioni file

La condivisione file può essere un server separato o essere collocata nello stesso server utilizzato da uno, più o tutti gli elementi seguenti:

  - Server di database, inclusi il server back-end di un pool Enterprise Edition Front End

  - Database di archiviazione

  - Database di monitoraggio

  - Database di chat persistente

  - Database di conformità di Persistent Chat

Una singola condivisione file può essere utilizzata per più pool Front End e server Standard Edition, tutti nello stesso sito.

<div>


> [!NOTE]  
> In Lync Server 2013, il monitoraggio e l'archiviazione utilizzano la condivisione file di Lync Server come server Standard Edition.



</div>

</div>

<div>

## <a name="other-components"></a>Altri componenti

Non è possibile collocare un server proxy inverso, che non è un componente di Lync Server 2013, ma che è necessario nella distribuzione se si desidera supportare la condivisione di contenuto Web per gli utenti federati con qualsiasi ruolo del server Lync Server 2013. È tuttavia possibile implementare il supporto del proxy inverso per una distribuzione di Lync Server 2013 configurando il supporto su un server proxy inverso esistente nell'organizzazione utilizzato per altre applicazioni.

Non è possibile collocare alcun componente di messaggistica unificata di Exchange o componente di SharePoint con un ruolo Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

