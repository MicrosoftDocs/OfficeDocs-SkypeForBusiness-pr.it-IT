---
title: 'Lync Server 2013: Collocazione dei server in una distribuzione di pool Enterprise Edition Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947d732cf17cc053e48596ffd310f5df3b11636
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Collocazione dei server in una distribuzione di pool Enterprise Edition Front End per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-11_

In questa sezione vengono descritti i ruoli del server, i database e le condivisioni di file che è possibile collocare in una distribuzione del pool Front End di Lync Server 2013.

<div>

## <a name="server-roles"></a>Ruoli del server

In Lync Server 2013, il servizio di conferenza A/V, il servizio di mediazione, il monitoraggio e l'archiviazione sono collocati nel server front-end, ma è necessaria una configurazione aggiuntiva per abilitarli. Se non si vuole collocare il Mediation Server con il front end server, è possibile distribuirlo come Mediation Server autonomo in un computer separato.

È possibile collocare un server delle applicazioni attendibile con il server front-end.

I ruoli del server seguenti devono essere distribuiti in un computer separato:

  - Director

  - Edge Server

  - Mediation Server (se non è collocato nel server front-end)

  - Server Office Web Apps

Non è possibile collocare il ruolo del server di chat persistente con il server front-end.

</div>

<div>

## <a name="databases"></a>Database

È possibile collocare tutti i database seguenti nello stesso server di database:

  - Database back-end

  - Database di monitoraggio

  - Database di archiviazione

  - Database di chat persistente

  - Database di conformità della chat persistente

È possibile collocare tutti o uno o tutti questi database in una singola istanza di SQL Server o utilizzare un'istanza distinta di SQL Server per ognuno di essi, con le limitazioni seguenti:

  - Ogni istanza di SQL Server può contenere solo un singolo database back-end, un singolo database di monitoraggio, un singolo database di archiviazione, un singolo database di chat persistente e un singolo database di conformità della chat persistente.

  - Il server di database non può supportare più di un pool Front-End, una distribuzione di archiviazione e una distribuzione di monitoraggio, ma può supportare uno di essi, indipendentemente dal fatto che i database utilizzino la stessa istanza di SQL Server o le istanze separate di SQL Server.

È possibile collocare una condivisione di file con i database, come descritto più avanti in questa sezione.

<div>


> [!NOTE]  
> In Lync Server 2013 è possibile integrare lo spazio di archiviazione di archiviazione con lo spazio di archiviazione di Exchange 2013 per alcuni o tutti gli utenti della distribuzione. Non è possibile distribuire tutti i server che utilizzano Lync Server o componenti nello stesso server dell'archivio di Exchange.



</div>

<div>


> [!IMPORTANT]  
> Anche se è supportata la collocazione dei database, è possibile che le dimensioni dei database crescano rapidamente. Ad esempio, se si considera la collocazione del database di archiviazione con altri database, tenere presente che, se si archiviano i messaggi di più utenti, lo spazio su disco necessario per il database di archiviazione può diventare molto grande. Per questo motivo, non è consigliabile collocare più database, in particolare il database di archiviazione, il database di chat persistente o il database di conformità della chat persistente con il database back-end.



</div>

</div>

<div>

## <a name="file-share"></a>Condivisione file

La condivisione file può essere un server separato o può essere collocata nello stesso server di una o tutte le operazioni seguenti:

  - Server di database, incluso il server back-end di un pool Front-end Enterprise Edition

  - Database di archiviazione

  - Database di monitoraggio

  - Database di chat persistente

  - Database di conformità della chat persistente

È possibile usare una singola condivisione di file per più pool Front-End, server Standard Edition (tutti nello stesso sito).

<div>


> [!NOTE]  
> In Lync Server 2013 il monitoraggio e l'archiviazione usano la condivisione file di Lync Server come server front-end.



</div>

</div>

<div>

## <a name="other-components"></a>Altri componenti

Non è possibile collocare un server proxy inverso, che non è un componente Lync Server 2013, ma è necessario nella distribuzione se si vuole supportare la condivisione di contenuto Web per gli utenti federati con qualsiasi ruolo del server Lync Server 2013. Puoi tuttavia implementare il supporto del proxy inverso per una distribuzione di Lync Server 2013 configurando il supporto di un server proxy inverso esistente nell'organizzazione usato per altre applicazioni.

Non è possibile collocare un componente di messaggistica UNIFICAta di Exchange o un componente di SharePoint con qualsiasi ruolo di SharePoint Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

