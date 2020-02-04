---
title: 'Lync Server 2013: disponibilità elevata del server back-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Disponibilità elevata del server back-end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-08-12_

Per garantire una disponibilità elevata per i server back-end, è possibile usare il mirroring SQL sincrono o il clustering SQL. L'uso di una di queste soluzioni è facoltativo, ma è consigliabile mantenere la continuità aziendale dell'organizzazione. Il mirroring asincrono di SQL non è supportato per la disponibilità elevata del server back-end in Lync Server 2013. Nel resto di questo documento, il mirroring SQL indica il mirroring SQL sincrono, a meno che non sia specificato diversamente esplicitamente.

È possibile configurare facilmente il mirroring SQL con generatore di topologie. Per la configurazione del clustering di failover SQL, è necessario usare SQL Server.

Se si usa il mirroring SQL o il clustering SQL in un pool associato a un altro pool Front-end per il ripristino di emergenza, è consigliabile usare la stessa soluzione di disponibilità elevata di back-end in entrambi i pool. Non è consigliabile associare un pool tramite il mirroring SQL con un pool tramite il clustering SQL.

Quando si distribuisce il mirroring SQL, tutti i database di Lync Server nel pool vengono speculati, incluso l'Central Management store, se si trova in questo pool, nonché il database dell'applicazione del gruppo di risposte e il database dell'applicazione Parcheggio di chiamata, se tali applicazioni vengono eseguiti nel pool.

Con il mirroring SQL, non è necessario usare lo spazio di archiviazione condiviso per i server. Ogni server mantiene la copia dei database in uno spazio di archiviazione locale.

È possibile scegliere di distribuire il mirroring SQL con o senza un testimone. È consigliabile usare un testimone perché consente il failover del server back-end come automatico. In caso contrario, un amministratore deve richiamare manualmente il failover. Tieni presente che anche se viene distribuito un testimone, un amministratore può richiamare manualmente il failover del server di back-end, se necessario.

Se si usa un testimone, è possibile usare un solo testimone per più coppie di server back-end. Non esiste una stretta corrispondenza di 1:1 tra i testimoni e le coppie di server back-end. Le distribuzioni che usano un singolo Witness per più coppie di server back-end non sono abbastanza resilienti come le topologie con un testimone separato per ogni coppia di server back-end.

Per altre informazioni sul supporto del clustering SQL, vedere [supporto software per database in Lync Server 2013](lync-server-2013-database-software-support.md). Per informazioni dettagliate sulla distribuzione del clustering SQL, vedere [configurare il clustering di SQL Server per Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>Tempo di recupero per il failover automatico del server back-end con il mirroring SQL

Per il failover automatico del back-end con il mirroring SQL, la destinazione ingegneristica per l'obiettivo del tempo di recupero (RTO) è di 5 minuti. A causa del mirroring SQL sincrono, non anticipiamo la perdita di dati durante gli errori del server back-end, tranne in rare occasioni in cui entrambi i server front-end e il server back-end scendono contemporaneamente mentre i dati vengono spostati tra i server. La destinazione ingegneristica per l'obiettivo del punto di ripristino (RPO) è di 5 minuti.

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>Esperienza utente durante l'errore del server back-end con il mirroring SQL

L'esperienza utente durante un errore dipende dalla natura dell'errore e dalla topologia.

Se si usa il mirroring SQL e si configura un testimone e l'entità non riesce, il failover del server di back-end avviene automaticamente e rapidamente. Gli utenti attivi non dovrebbero notare molte interruzioni delle sessioni in corso.

Se non sono configurati i testimoni, sarà necessario un po' di tempo prima che l'amministratore richiami manualmente il failover. Durante tale periodo gli utenti attivi potrebbero essere interessati. Continueranno le loro sessioni normalmente per circa 30 minuti. Se il principale non è ancora stato ripristinato o un amministratore non ha eseguito il failover del backup, gli utenti vengono convertiti in modalità resilienza, pertanto non sono in grado di eseguire attività che richiedono una modifica persistente in Lync Server, ad esempio l'aggiunta di un contatto.

Se i server di back-end di Principal e mirror non riescono o se uno di questi server e il witness non riescono, il server back-end diventerà non disponibile (anche se è l'entità che sta ancora lavorando). In questo caso, dopo qualche tempo, gli utenti attivi vengono convertiti in modalità resilienza.

</div>

</div>

<span> </span>

</div>

</div>

</div>

