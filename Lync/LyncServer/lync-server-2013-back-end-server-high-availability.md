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
ms.openlocfilehash: 335f7680a98eb53414a8b438975d79327b515946
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Disponibilità elevata del server back-end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-08-12_

Per garantire una disponibilità elevata per i server back-end, è possibile utilizzare il mirroring SQL sincrono o il clustering SQL. L'utilizzo di una di queste soluzioni è facoltativo, ma è consigliabile mantenere la continuità aziendale della propria organizzazione. Il mirroring asincrono SQL non è supportato per la disponibilità elevata del server back-end in Lync Server 2013. In questo documento qualsiasi riferimento al mirroring SQL sottintende il mirroring SQL sincrono, a meno che non venga specificato diversamente.

È possibile configurare facilmente il mirroring SQL con generatore di topologie. Per il clustering di failover SQL, è necessario utilizzare SQL Server per il programma di installazione.

Se si utilizza il mirroring SQL o il clustering SQL in un pool che è associato a un altro pool Front end per il ripristino di emergenza, è consigliabile utilizzare la stessa soluzione di disponibilità elevata back-end in entrambi i pool. Non è necessario accoppiare un pool utilizzando il mirroring SQL con un pool che utilizza il clustering SQL.

Quando si distribuisce il mirroring SQL, tutti i database di Lync Server nel pool vengono sottoposti a mirroring, incluso l'archivio di gestione centrale, se si trova in questo pool, nonché il database dell'applicazione Response Group e il database dell'applicazione Parcheggio di chiamata, se tali applicazioni sono in esecuzione nel pool.

Con il mirroring SQL, non è necessario utilizzare l'archiviazione condivisa per i server. Ogni server mantiene la propria copia dei database nello spazio di archiviazione locale.

È possibile scegliere di distribuire il mirroring SQL con o senza controllo. È consigliabile utilizzare un server di controllo poiché consente il failover automatico del server back-end. In caso contrario, un amministratore deve richiamare manualmente il failover. Se noti che anche se è distribuito un server di controllo, un amministratore può comunque richiamare manualmente il failover del server back-end, se necessario.

Se si dispone di un server di controllo, è possibile utilizzare un singolo server di controllo per più coppie di server back-end. Non esiste una corrispondenza esatta tra server di controllo e coppie di server back-end. Le distribuzioni in cui viene utilizzato un singolo server di controllo per più coppie di server back-end non sono resilienti quanto le topologie con un server di controllo separato per ogni coppia di server back-end.

Per ulteriori informazioni sul supporto del clustering SQL, vedere [database software support in Lync Server 2013](lync-server-2013-database-software-support.md). Per informazioni dettagliate sulla distribuzione del clustering SQL, vedere [Configure SQL Server clustering for Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>Tempo di ripristino per il failover automatico del server back-end con il mirroring SQL

Per il failover automatico del back-end con il mirroring SQL, la destinazione ingegneristica per l'obiettivo del tempo di ripristino (RTO) è di 5 minuti. A causa del mirroring SQL sincrono, non è prevista una perdita di dati in caso di errori di server back-end, eccetto in rari casi in cui si verifica un problema simultaneo dei Front End Server e del server back-end durante il trasferimento di dati tra i server. L'obiettivo in termini di punto di ripristino (RPO, Recovery Point Objective) è 5 minuti.

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>Esperienza utente durante un errore del server back-end con il mirroring SQL

L'esperienza utente durante un errore dipende dalla natura dell'errore e dalla topologia.

Se si utilizza il mirroring SQL e si dispone di un controllo configurato e l'entità ha esito negativo, il failover del server back-end avviene automaticamente e rapidamente. Gli utenti attivi non dovrebbero osservare un'interruzione delle sessioni in corso.

Se invece non è configurato alcun server di controllo, l'amministratore necessiterà del tempo previsto per richiamare manualmente il failover. Durante questo intervallo è possibile che gli utenti attivi subiscano alcuni disagi. Continueranno a utilizzare normalmente le sessioni per circa 30 minuti. Se il principale non è ancora stato ripristinato o un amministratore non ha eseguito il failover del backup, gli utenti vengono passati alla modalità di resilienza, pertanto non sono in grado di eseguire attività che richiedono una modifica permanente su Lync Server, ad esempio l'aggiunta di un contatto.

Se si verifica un errore sia del server principale che dei server back-end mirror oppure di uno di questi server e del server di controllo, il server back-end non sarà disponibile (anche se il server principale è ancora in funzione). In questo caso, gli utenti attivi passano alla modalità resilienza dopo un intervallo di tempo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

