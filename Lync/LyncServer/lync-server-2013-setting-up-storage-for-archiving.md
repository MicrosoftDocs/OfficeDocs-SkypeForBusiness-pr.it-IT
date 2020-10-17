---
title: "Lync Server 2013: configurazione dello spazio di archiviazione per l'archiviazione"
description: "Lync Server 2013: configurazione dello spazio di archiviazione per l'archiviazione."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7ee431b17b31c49ace7fae1f90d79ec6de2ada4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554242"
---
# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>Configurazione dello spazio di archiviazione per l'archiviazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-12-17_

Lo spazio di archiviazione per Lync Server 2013 include gli elementi seguenti:

  - **Archiviazione**     dei dati Lo spazio di archiviazione dei dati è necessario per archiviare il contenuto di messaggistica istantanea.

  - **Archiviazione file**     Lo spazio di archiviazione dei file è necessario per archiviare i dati del contenuto e l'archiviazione delle conferenze (riunioni).

<div>

## <a name="setting-up-data-storage"></a>Configurazione dell'archivio dati

I requisiti per la configurazione dell'archiviazione dei dati per l'archiviazione in Lync Server 2013 dipendono dal modo in cui si desidera archiviare i dati di archiviazione:

  - Integrazione dell'archiviazione di Lync Server 2013 con la distribuzione di Exchange per archiviare i dati di archiviazione mediante l'archiviazione di Exchange.

  - Impostare i server di database di SQL Server separati per archiviare i dati di archiviazione.

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>Configurazione dell'archiviazione di Exchange per l'archiviazione dei dati

La configurazione di Exchange per l'archiviazione dei dati di archiviazione richiede che la distribuzione di Exchange esegua Exchange 2013. Inoltre, le cassette postali degli utenti devono essere ospitate nel server Exchange 2013 e le relative cassette postali devono essere inserite In-Place blocco. Per informazioni dettagliate sulla configurazione di Exchange 2013, vedere la documentazione del prodotto Exchange.

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>Configurazione dei server database di SQL Server per l'archiviazione dei dati

L'archiviazione in Lync Server 2013 richiede che il software di database di SQL Server memorizzi i dati archiviati, a meno che non si integri la distribuzione con Exchange.

Per i database di archiviazione di SQL Server, è necessario installare SQL Server nel computer che ospiterà il database di archiviazione. È possibile utilizzare la stessa istanza SQL utilizzata per il database back-end di un pool Front End. Per ottenere prestazioni ottimali, è consigliabile distribuire il database di archiviazione in un computer distinto dall'archivio di gestione centrale. Per informazioni dettagliate sulla collocazione dei componenti di Lync Server 2013, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.

Ogni server di database deve eseguire una versione supportata di SQL Server. Per informazioni dettagliate sulle versioni supportate, vedere [Technical Requirements for archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) nella documentazione relativa alla pianificazione.

È necessario configurare le piattaforme SQL Server prima di distribuire e abilitare l'archiviazione. Se l'account utilizzato per pubblicare la topologia dispone delle autorizzazioni e dei diritti di amministratore appropriati, è possibile creare il database di archiviazione (LcsLog) quando si pubblica la topologia. È inoltre possibile creare il database in un secondo momento, come parte della procedura di installazione. Per informazioni dettagliate su SQL Server, vedere il sito Web di SQL Server TechCenter all'indirizzo [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) .

<div>


> [!NOTE]  
> Verificare che il tipo di avvio del servizio SQL Server Agent sia automatico e che il servizio SQL Server Agent sia in esecuzione per l'istanza di SQL che contiene il database di archiviazione, in modo che il processo di manutenzione di SQL Server di archiviazione predefinito possa essere eseguito nella sua base pianificata sotto il controllo del servizio SQL Server Agent.



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>Configurazione dell'archiviazione dei file

L'archiviazione utilizza la condivisione file di Lync Server 2013 specificata durante la configurazione del pool Front end o del server Standard Edition. Non è possibile modificare la condivisione di file utilizzata per l'archiviazione. Per informazioni dettagliate sui sistemi di archiviazione dei file supportati, vedere [file Storage Support in Lync Server 2013](lync-server-2013-file-storage-support.md) nella documentazione relativa alla supportabilità.

</div>

</div>

<span> </span>

</div>

</div>

</div>

