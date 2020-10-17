---
title: Collocazione del server Lync Server 2013 in una distribuzione di pool Enterprise Edition front end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0162a4338a1504ed425015e5b9391fca9903d4ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510283"
---
# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Collocazione dei server in una distribuzione di pool Enterprise Edition front end per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-11_

In questa sezione vengono descritti i ruoli del server, i database e le condivisioni di file che è possibile collocare in una distribuzione di pool Front End di Lync Server 2013.

<div>

## <a name="server-roles"></a>Ruoli del server

In Lync Server 2013, il servizio A/V Conferencing, il servizio Mediation, il monitoraggio e l'archiviazione sono collocati nel front end server, ma è necessaria una configurazione aggiuntiva per abilitarli. Se si sceglie di non collocare il Mediation Server nel Front End Server, è possibile distribuirlo come Mediation Server autonomo in un computer distinto.

È possibile collocare un server applicazioni attendibili nel Front End Server.

I ruoli del server seguenti devono essere ognuno distribuito in un computer distinto:

  - Director

  - Server perimetrale

  - Mediation Server (se non collocato con il Front End Server)

  - server Office Web Apps

Non è possibile collocare il ruolo del server Chat persistente con il front end server.

</div>

<div>

## <a name="databases"></a>Database

È possibile collocare ognuno dei database seguenti nello stesso server di database:

  - Database back-end

  - Database di monitoraggio

  - Database di archiviazione

  - Database di chat persistente

  - Database di conformità di Persistent Chat

È possibile collocare tutti o uno o tutti questi database in una singola istanza di SQL Server oppure utilizzare un'istanza separata di SQL Server per ognuno, con le limitazioni seguenti:

  - Ogni istanza di SQL Server può contenere solo un singolo database back-end, un singolo database di monitoraggio, un singolo database di archiviazione, un singolo database di chat persistente e un singolo database di conformità di Persistent Chat.

  - Il server di database non è in grado di supportare più di un pool Front End, una distribuzione di archiviazione e una distribuzione di monitoraggio, ma è in grado di supportare ognuno di essi, indipendentemente dal fatto che i database utilizzino la stessa istanza di SQL Server o le istanze separate di SQL Server.

È possibile collocare una condivisione file con i database, come descritto più avanti in questa sezione.

<div>


> [!NOTE]  
> In Lync Server 2013, si ha la possibilità di integrare l'archiviazione di archiviazione con Exchange 2013 storage per alcuni o tutti gli utenti nella distribuzione. Non è possibile distribuire i server che eseguono Lync Server o i componenti negli stessi server dell'archivio di Exchange.



</div>

<div>


> [!IMPORTANT]  
> Sebbene la collocazione dei database sia supportata, la dimensione dei database può aumentare rapidamente. Ad esempio, se si intende collocare il database di archiviazione con altri database, è opportuno tenere presente che l'archiviazione dei messaggi di più utenti può comportare un notevole aumento dello spazio su disco richiesto dal database di archiviazione. Per questo motivo, non è consigliabile collocare più database, in particolare il database di archiviazione, il database di chat persistente o il database di conformità di Persistent Chat con il database back-end.



</div>

</div>

<div>

## <a name="file-share"></a>Condivisione file

La condivisione file può essere un server separato o essere collocata nello stesso server utilizzato da uno, più o tutti gli elementi seguenti:

  - Server di database, inclusi il server back-end di un pool Enterprise Edition Front End

  - Database di archiviazione

  - Database di monitoraggio

  - Database di chat persistente

  - Database di conformità di Persistent Chat

Una singola condivisione file può essere utilizzata per più pool Front End e server Standard Edition, tutti nello stesso sito.

<div>


> [!NOTE]  
> In Lync Server 2013, il monitoraggio e l'archiviazione utilizzano la condivisione file di Lync Server come front end server.



</div>

</div>

<div>

## <a name="other-components"></a>Altri componenti

Non è possibile collocare un server proxy inverso, che non è un componente di Lync Server 2013, ma che è necessario nella distribuzione se si desidera supportare la condivisione di contenuto Web per gli utenti federati con qualsiasi ruolo del server Lync Server 2013. È tuttavia possibile implementare il supporto del proxy inverso per una distribuzione di Lync Server 2013 configurando il supporto su un server proxy inverso esistente nell'organizzazione utilizzato per altre applicazioni.

Non è possibile collocare alcun componente di messaggistica unificata di Exchange o componente di SharePoint con qualsiasi ruolo di SharePoint Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

