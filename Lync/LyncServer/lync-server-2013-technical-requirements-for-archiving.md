---
title: "Lync Server 2013: requisiti tecnici per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c388fd04ba7600aa28a142961cd5ac07f63ae7c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Requisiti tecnici per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-09_

Nei requisiti tecnici di Lync Server 2013 sono inclusi i seguenti:

  - Requisiti dell'infrastruttura

  - Software prerequisito da installare per l'archiviazione

  - Requisiti di archiviazione dati per l'archiviazione

  - Considerazioni e requisiti per l'implementazione della scalabilità per la distribuzione di archiviazione

  - Considerazioni e requisiti di prestazioni per i database di archiviazione

<div>


> [!NOTE]  
> Le informazioni sulla scalabilità e sulle prestazioni non sono disponibili in questa versione di Lync Server 2013.



</div>

<div>

## <a name="infrastructure-requirements"></a>Requisiti dell'infrastruttura

I requisiti dell'infrastruttura di archiviazione di Lync Server 2013 sono uguali a quelli per la distribuzione di Lync Server 2013. Per informazioni dettagliate, vedere [Determining Your Infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="archiving-prerequisites"></a>Prerequisiti per l'archiviazione

Lync Server 2013 semplifica i prerequisiti per l'archiviazione a causa delle operazioni seguenti:

  - L'archiviazione non è più un ruolo del server. Ora, gli agenti di raccolta dati unificati sono eseguiti sui server Front End Server in un pool e sui server Standard Edition per la raccolta dei dati di archiviazione, in modo da evitare la configurazione di piattaforme di sistema separate per l'archiviazione.

  - L'archiviazione utilizza l'archivio file di Lync Server 2013 per l'archiviazione temporanea dei file di contenuto della riunione, pertanto non è necessario configurare un file Store separato per l'archiviazione.

  - In Lync Server 2013, Accodamento messaggi non è necessario.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>Requisiti di archiviazione dati per l'archiviazione

È inoltre necessario configurare l'infrastruttura per l'archiviazione, eseguendo una o entrambe le operazioni seguenti:

  - **Archiviazione di Microsoft Exchange**. I file di contenuto delle riunioni, ad esempio le presentazioni PowerPoint, sono archiviate come allegati. Se si desidera utilizzare l'integrazione di Microsoft Exchange in modo che i dati di archiviazione di Lync vengano archiviati con i dati di conformità di Exchange, è necessario utilizzare Exchange 2013 per la distribuzione di Exchange e verificare che le dimensioni massime di archiviazione supportino l'archiviazione dei file di contenuto della riunione. Se si distribuisce l'archiviazione utilizzando l'opzione di integrazione di Microsoft Exchange, i dati di archiviazione di Lync vengono archiviati con i dati di conformità di Exchange 2013 solo per gli utenti ospitati nei server Exchange 2013. È necessario distribuire Exchange 2013 prima di distribuire e abilitare l'archiviazione tramite l'opzione di integrazione di Microsoft Exchange. Se si sceglie di utilizzare lo spazio di archiviazione di Exchange 2013, non è necessario distribuire database SQL Server distinti per l'archiviazione, a meno che non siano presenti utenti di Lync che non sono ospitati nei server Exchange 2013.

  - **Archiviazione dei database di SQL Server per l'archiviazione**. Per supportare gli utenti che non sono ospitati nei server Exchange 2013 o se non si desidera utilizzare l'opzione di integrazione di Microsoft Exchange, è necessario distribuire l'archiviazione di archiviazione utilizzando un database di SQL Server. Lync Server 2013 supporta le seguenti versioni di SQL Server a 64 bit:
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express e Microsoft SQL Server 2012 Express non sono supportati per l'archiviazione. le versioni a 32 bit di SQL Server non sono supportate. Per ulteriori requisiti e limitazioni di SQL Server, vedere <A href="lync-server-2013-database-software-support.md">database software support in Lync server 2013</A> nella documentazione relativa alla pianificazione o nella documentazione relativa alla supportabilità.

    
    </div>
    
    È necessario configurare le piattaforme SQL Server prima di distribuire e abilitare l'archiviazione. Se l'account utilizzato per pubblicare la topologia dispone delle autorizzazioni e dei diritti di amministratore appropriati, è possibile creare il database di archiviazione (LcsLog) quando si pubblica la topologia. È inoltre possibile creare il database in un secondo momento, come parte della procedura di installazione. Per informazioni dettagliate su SQL Server, vedere il sito Web di [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)SQL Server TechCenter all'indirizzo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

