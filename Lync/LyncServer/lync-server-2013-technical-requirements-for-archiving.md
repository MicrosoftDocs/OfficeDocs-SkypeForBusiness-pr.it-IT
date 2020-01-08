---
title: "Lync Server 2013: requisiti tecnici per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Requisiti tecnici per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-09_

I requisiti tecnici di Lync Server 2013 includono i seguenti:

  - Requisiti per l'infrastruttura.

  - Software prerequisito che deve essere installato per l'archiviazione.

  - Requisiti di archiviazione dei dati per l'archiviazione.

  - Ridimensionamento di requisiti e considerazioni per la distribuzione dell'archiviazione.

  - Requisiti e considerazioni sulle prestazioni per i database di archiviazione.

<div>


> [!NOTE]  
> Le informazioni sulla scalabilità e sulle prestazioni non sono disponibili in questa versione di Lync Server 2013.



</div>

<div>

## <a name="infrastructure-requirements"></a>Requisiti per l'infrastruttura

I requisiti dell'infrastruttura di archiviazione di Lync Server 2013 sono uguali a quelli per la distribuzione di Lync Server 2013. Per informazioni dettagliate, vedere [determinazione dei requisiti di infrastruttura per Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="archiving-prerequisites"></a>Archiviazione di prerequisiti

Lync Server 2013 semplifica i prerequisiti per l'archiviazione a causa delle operazioni seguenti:

  - Il server di archiviazione non è più un ruolo del server. Gli agenti di raccolta dati unificati vengono invece eseguiti nei server front-end in un pool e in Server Standard Edition per acquisire dati per l'archiviazione, quindi non è possibile configurare piattaforme di sistema separate per l'archiviazione.

  - L'archiviazione usa l'archiviazione di file di Lync Server 2013 per l'archiviazione temporanea dei file di contenuto della riunione, quindi non è possibile configurare un archivio di file separato per l'archiviazione.

  - In Lync Server 2013 non è necessario accodare messaggi.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>Requisiti di archiviazione dei dati per l'archiviazione

Inoltre, è necessario configurare l'infrastruttura per l'archiviazione. Questo include una o entrambe le opzioni seguenti:

  - **Archiviazione di Microsoft Exchange**. I file di contenuto della riunione, ad esempio le presentazioni di PowerPoint, vengono archiviati come allegati. Se si vuole usare l'integrazione di Microsoft Exchange in modo che i dati di archiviazione di Lync vengano archiviati con i dati di conformità di Exchange, è necessario usare Exchange 2013 per la distribuzione di Exchange e verificare che le dimensioni massime dello spazio di archiviazione supportino l'archiviazione dei file di contenuto della riunione. Se si distribuisce l'archiviazione con l'opzione di integrazione di Microsoft Exchange, i dati di archiviazione di Lync vengono archiviati con i dati di conformità di Exchange 2013 solo per gli utenti residenti nei server di Exchange 2013. È necessario distribuire Exchange 2013 prima di distribuire e abilitare l'archiviazione con l'opzione di integrazione di Microsoft Exchange. Se si sceglie di usare lo spazio di archiviazione di Exchange 2013, non è necessario distribuire database di SQL Server distinti per l'archiviazione, a meno che non siano presenti utenti di Lync non residenti nei server di Exchange 2013.

  - **Archiviazione di database di SQL Server per l'archiviazione**. Per supportare gli utenti non residenti nei server di Exchange 2013 o se non si vuole usare l'opzione di integrazione di Microsoft Exchange, è necessario distribuire archiviazione di archiviazione tramite un database di SQL Server. Lync Server 2013 supporta le versioni di SQL Server seguenti a 64 bit:
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express e Microsoft SQL Server 2012 Express non sono supportati per l'archiviazione. le versioni a 32 bit di SQL Server non sono supportate. Per ulteriori requisiti e restrizioni di SQL Server, vedere <A href="lync-server-2013-database-software-support.md">supporto del software di database in Lync Server 2013</A> nella documentazione relativa alla pianificazione o nella documentazione relativa alla supportabilità.

    
    </div>
    
    È necessario configurare le piattaforme SQL Server prima di distribuire e abilitare l'archiviazione. Se l'account da usare per pubblicare la topologia include i diritti e le autorizzazioni di amministratore appropriati, è possibile creare il database di archiviazione (LcsLog) durante la pubblicazione della topologia. È anche possibile creare il database in un secondo momento, incluso come parte della procedura di installazione. Per informazioni dettagliate su SQL Server, vedere SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).

</div>

</div>

<span> </span>

</div>

</div>

</div>

