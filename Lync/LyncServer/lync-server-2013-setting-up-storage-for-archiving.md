---
title: "Lync Server 2013: configurazione dello spazio di archiviazione per l'archiviazione"
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
ms.openlocfilehash: a5a380ce6c863c54739e74488bfa3b3979664e78
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>Configurazione dello spazio di archiviazione per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-12-17_

L'archiviazione archiviante per Lync Server 2013 include le operazioni seguenti:

  - ****   Archiviazione dei dati di archiviazione dei dati necessaria per archiviare il contenuto di messaggistica istantanea.

  - **** Lo spazio di archiviazione file è necessario per archiviare l'archiviazione dei dati del contenuto e l'archiviazione di file in conferenza.   

<div>

## <a name="setting-up-data-storage"></a>Configurazione dell'archiviazione dei dati

I requisiti per la configurazione dell'archiviazione dei dati per l'archiviazione in Lync Server 2013 dipendono dal modo in cui si vogliono archiviare i dati di archiviazione:

  - Integrare Lync Server 2013 archiviazione con la distribuzione di Exchange per archiviare i dati di archiviazione tramite lo spazio di archiviazione di Exchange.

  - Configurare i server di database di SQL Server separati per archiviare i dati di archiviazione.

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>Configurazione dello spazio di archiviazione di Exchange per l'archiviazione dei dati

La configurazione di Exchange per l'archiviazione dei dati di archiviazione richiede che la distribuzione di Exchange esegua Exchange 2013. Inoltre, le cassette postali degli utenti devono essere ospitate nel server di Exchange 2013 e le relative cassette postali devono essere inserite in blocco sul posto. Per informazioni dettagliate sulla configurazione di Exchange 2013, vedere la documentazione del prodotto Exchange.

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>Configurazione di server di database di SQL Server per l'archiviazione dei dati di archiviazione

L'archiviazione in Lync Server 2013 richiede che il software di database di SQL Server memorizzi i dati archiviati, a meno che non si integri la distribuzione con Exchange.

Per i database di archiviazione di SQL Server, è necessario installare SQL Server nel computer in cui verrà ospitato il database di archiviazione. È possibile usare la stessa istanza SQL usata per il database back-end di un pool Front-end. Per ottenere prestazioni ottimali, è consigliabile distribuire il database di archiviazione in un computer separato dall'Central Management store. Per informazioni dettagliate sulla collocazione dei componenti di Lync Server 2013, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.

Ogni server di database deve eseguire una versione supportata di SQL Server. Per informazioni dettagliate sulle versioni supportate, vedere [requisiti tecnici per l'archiviazione in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) nella documentazione relativa alla pianificazione.

È necessario configurare le piattaforme SQL Server prima di distribuire e abilitare l'archiviazione. Se l'account da usare per pubblicare la topologia include i diritti e le autorizzazioni di amministratore appropriati, è possibile creare il database di archiviazione (LcsLog) durante la pubblicazione della topologia. È anche possibile creare il database in un secondo momento, incluso come parte della procedura di installazione. Per informazioni dettagliate su SQL Server, vedere SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).

<div>


> [!NOTE]  
> Verificare che il tipo di avvio del servizio di SQL Server Agent sia automatico e che il servizio SQL Server Agent sia in esecuzione per l'istanza SQL in cui è in possesso il database di archiviazione, in modo che il processo di archiviazione predefinito di SQL Server possa essere eseguito in base alle proprie condizioni pianificate sotto la controllo del servizio SQL Server Agent.



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>Configurazione dello spazio di archiviazione file

L'archiviazione usa la condivisione di file di Lync Server 2013 specificata durante la configurazione del pool Front-end o del server Standard Edition. Non è possibile modificare la condivisione di file usata per l'archiviazione. Per informazioni dettagliate sui sistemi di archiviazione dei file supportati, vedere [supporto dell'archiviazione dei file in Lync Server 2013](lync-server-2013-file-storage-support.md) nella documentazione relativa alla supportabilità.

</div>

</div>

<span> </span>

</div>

</div>

</div>

