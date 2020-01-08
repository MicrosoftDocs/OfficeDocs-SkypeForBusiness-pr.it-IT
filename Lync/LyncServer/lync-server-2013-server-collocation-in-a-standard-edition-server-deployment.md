---
title: 'Lync Server 2013: Collocazione dei server in una distribuzione server Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950f2ab06a146ec99ef9ebb2ecbc64c885c82d70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Collocazione dei server in una distribuzione server Standard Edition per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-20_

In questa sezione vengono descritti i ruoli del server, i database e le condivisioni di file che è possibile collocare in una distribuzione di Lync Server 2013 Standard Edition Server.

<div>

## <a name="server-roles"></a>Ruoli del server

In Lync Server 2013, il servizio di conferenza A/V, il servizio di mediazione, il monitoraggio e l'archiviazione sono collocati nel server Standard Edition, ma è necessaria una configurazione aggiuntiva per abilitarli. È possibile scegliere di distribuire il servizio di mediazione in server distinti.

È possibile collocare un server applicazioni attendibile con un server Standard Edition.

I ruoli del server seguenti devono essere distribuiti in un computer separato:

  - Director

  - Edge Server

  - Mediation Server (se non è collocato con il server Standard Edition)

  - Server Office Web Apps

</div>

<div>

## <a name="databases"></a>Database

Per impostazione predefinita, il database back-end di SQL Server Express è collocato nel server Standard Edition. Non è possibile spostarlo in un computer separato. Con un'unica eccezione, non è possibile collocare altri database nel server Standard Edition. Se si sceglie di distribuire il server di chat persistente in un server Standard Edition, è possibile collocare il database di chat persistente e il database di conformità della chat persistente nello stesso server Standard Edition.

È possibile collocare ognuno dei database seguenti in un singolo server di database:

  - Database di monitoraggio

  - Database di archiviazione

  - Database back-end per un pool di front-end Enterprise Edition

È possibile collocare tutti o uno o tutti questi database in una singola istanza di SQL oppure usare istanze SQL separate per ognuna di esse, con le limitazioni seguenti:

  - Ogni istanza di SQL può contenere solo un database back-end (per un pool di front-end di Enterprise Edition), un singolo database di monitoraggio, un singolo database di archiviazione, un singolo database di chat persistente e un singolo database di conformità della chat persistente.

  - Il server di database non supporta più di un pool Front-end Enterprise Edition, un server che ha eseguito l'archiviazione, un monitoraggio in esecuzione del server, un singolo database di chat persistente e un database di conformità della chat persistente, ma può supportare uno di essi. indipendentemente dal fatto che i database utilizzino la stessa istanza di SQL Server o le istanze separate di SQL Server.

È possibile collocare una condivisione di file con i database, come descritto più avanti in questa sezione.

<div>


> [!NOTE]  
> In Lync Server 2013 è possibile integrare il monitoraggio e l'archiviazione dello spazio di archiviazione con Exchange 2013 storage per alcuni o tutti gli utenti della distribuzione. Non è possibile distribuire tutti i server che utilizzano Lync Server o componenti nello stesso server dell'archivio di Exchange.



</div>

<div>


> [!IMPORTANT]  
> Anche se è supportata la collocazione dei database, è possibile che le dimensioni dei database crescano rapidamente. Ad esempio, se si considera la collocazione del database di archiviazione con altri database, tenere presente che, se si archiviano i messaggi di più utenti, lo spazio su disco necessario per il database di archiviazione può diventare molto grande. Per questo motivo, non è consigliabile collocare più database, in particolare il database di archiviazione, il database di chat persistente e il database di conformità della chat persistente con il database back-end di un pool aziendale.



</div>

</div>

<div>

## <a name="file-shares"></a>Condivisioni file

La condivisione file può essere un server separato o può essere collocata nello stesso server di una o tutte le operazioni seguenti:

  - Server di database, incluso il server back-end di un pool Front-end Enterprise Edition

  - Database di archiviazione

  - Database di monitoraggio

  - Database di chat persistente

  - Database di conformità della chat persistente

È possibile usare una singola condivisione di file per più pool Front-End, server Standard Edition (tutti nello stesso sito).

<div>


> [!NOTE]  
> In Lync Server 2013 il monitoraggio e l'archiviazione usano la condivisione file di Lync Server come server Standard Edition.



</div>

</div>

<div>

## <a name="other-components"></a>Altri componenti

Non è possibile collocare un server proxy inverso, che non è un componente Lync Server 2013, ma è necessario nella distribuzione se si vuole supportare la condivisione di contenuto Web per gli utenti federati con qualsiasi ruolo del server Lync Server 2013. Puoi tuttavia implementare il supporto del proxy inverso per una distribuzione di Lync Server 2013 configurando il supporto di un server proxy inverso esistente nell'organizzazione usato per altre applicazioni.

Non è possibile collocare un componente di messaggistica unificata di Exchange o un componente SharePoint con qualsiasi ruolo di Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

