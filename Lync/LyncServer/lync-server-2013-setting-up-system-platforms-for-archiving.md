---
title: "Lync Server 2013: configurazione di piattaforme di sistema per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13682b7507e133dd49c102bf6c25293ff5da2c08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Configurazione di piattaforme di sistema per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-09_

Prima di avviare la distribuzione dell'archiviazione, è necessario installare il sistema operativo necessario e qualsiasi altro software prerequisito su hardware che soddisfi i requisiti di sistema:

  - ****   Le distribuzioni di Lync Server 2013 Platform Lync Server 2013 non dispongono di server di archiviazione. Gli agenti di raccolta dati unificati vengono invece eseguiti nei server front-end e nei server Standard Edition per acquisire dati per l'archiviazione, quindi non è necessaria una piattaforma di sistema separata per ospitare l'archiviazione.

  - **Piattaforma di archiviazione dati**   in Lync Server 2013 è possibile archiviare i dati utilizzando una delle opzioni seguenti:
    
      - **Integrazione di Microsoft Exchange**   se si vuole archiviare i dati di archiviazione di Lync Server 2013 tramite la distribuzione di Exchange 2013, anziché o in aggiunta alla configurazione di un database separato per l'archiviazione dei dati di archiviazione, è necessario che la distribuzione di Exchange esegua Exchange 2013. Per informazioni dettagliate sulla configurazione di piattaforme di sistema per Exchange 2013, vedere la documentazione del prodotto Exchange.
    
      - **SQL Server**   se si vuole usare un database SQL Server separato per l'archiviazione dei dati di archiviazione, anziché o oltre a usare l'integrazione di Microsoft Exchange, è necessario configurare la piattaforma di sistema per il database prima della distribuzione dell'archiviazione. I requisiti specifici della piattaforma di sistema variano a seconda che si usi Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 per il database di archiviazione. Per informazioni dettagliate sulla configurazione di piattaforme di sistema per questi database, vedere la documentazione del prodotto Microsoft SQL Server 2008 R2 e Microsoft SQL Server 2012.

  - **Piattaforma file server**   Lync Server 2013 archivia i file di archiviazione di Lync Server nella stessa posizione specificata per l'archiviazione dei file quando si configurano i server front-end o i server Standard Edition. Non è possibile specificare una posizione separata per l'archiviazione dei file, quindi non è necessaria una piattaforma di sistema separata per archiviare l'archiviazione dei file. Se si usa l'integrazione di Microsoft Exchange, Exchange 2013 i file per le comunicazioni di Lync archiviati sono archiviati nei server di Exchange 2013 per gli utenti residenti in questi server di Exchange.

</div>

<span> </span>

</div>

</div>

</div>

