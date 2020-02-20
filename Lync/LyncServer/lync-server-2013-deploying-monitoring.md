---
title: 'Lync Server 2013: distribuzione del monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e10cd492679cb412c57ea37698df198eef7721b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a>Distribuzione del monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-12-17_

Sono state apportate modifiche importanti all'infrastruttura di monitoraggio di Microsoft Lync Server 2013, a partire dal fatto che il ruolo Monitoring Server è obsoleto. Al posto di ruoli server Monitoring Server separati (che normalmente richiedono la configurazione di computer dedicati come server di monitoraggio nelle organizzazioni), i servizi di monitoraggio sono ora collocati sui singoli server front-end. Questa modifica, tra le altre cose, consente di:

  - Ridurre il numero di ruoli del server necessari per l'implementazione di Lync Server 2013. In questo caso, il decremento del ruolo server Monitoring Server si traduce anche in una riduzione dei costi poiché non è più necessario mantenere server dedicati per il monitoraggio.

  - Ridurre la complessità dell'installazione e dell'amministrazione di Lync Server. Collocando automaticamente i servizi di monitoraggio su ogni server front-end, non è più necessario installare, configurare e gestire il ruolo Monitoring Server.

<div>


> [!NOTE]  
> Il ruolo del server di archiviazione è stato deprecato anche in Lync Server 2013. Analogamente ai servizi di monitoraggio, i servizi di archiviazione di Lync Server 2013 sono ora collocati in ogni Front End Server. È importante tenerlo presente semplicemente perché il monitoraggio e l'archiviazione spesso condividono la stessa istanza di database di SQL Server.



</div>

Come si potrebbe immaginare, queste modifiche hanno un impatto importante sulla modalità di installazione e gestione dei servizi di monitoraggio. Ad esempio, poiché il ruolo Monitoring Server non esiste più, il nodo Monitoring Server è stato rimosso dal generatore di topologie di Lync Server. Ciò significa che non è più possibile utilizzare la procedura guidata del nuovo Monitoring Server di generatore di topologie per aggiungere un nuovo server di monitoraggio alla topologia. La procedura guidata non esiste più. In genere, invece, vengono implementati i servizi di monitoraggio all'interno della topologia completando i due passaggi seguenti:

1.  Abilitazione del monitoraggio nello stesso momento in cui si configura un nuovo pool di Lync Server. In Lync Server 2013, il monitoraggio è abilitato o disabilitato in base al pool. Si noti che è possibile abilitare il monitoraggio per un pool senza raccogliere effettivamente i dati di monitoraggio, un processo illustrato nella sezione Configurazione delle impostazioni di registrazione dettagli chiamata e qualità di esperienza di questa documentazione.

2.  Associazione di un archivio (database) di monitoraggio al nuovo pool. Tenere presente che un archivio di monitoraggio può essere associato a più pool. A seconda del numero di utenti ospitati nei pool di registrazione, questo comporta che non è necessario configurare un database di monitoraggio separato per ogni pool, ma un singolo archivio di monitoraggio può essere utilizzato da più pool.

Sebbene spesso risulti più semplice abilitare il monitoraggio al momento della creazione di un nuovo pool, è anche possibile creare un nuovo pool con il monitoraggio disabilitato. In questo caso, è possibile abilitare il servizio in un secondo momento utilizzando il Generatore di topologie, che consente di attivare o disattivare il monitoraggio di topologie o di associare un pool a un diverso archivio di monitoraggio. Tenere presente che, sebbene non esista più il ruolo Monitoring Server, è comunque necessario creare uno o più archivi di monitoraggio, ovvero i database back-end utilizzati per archiviare i dati raccolti dal servizio di monitoraggio. Questi database back-end possono essere creati mediante Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012.

<div>


> [!NOTE]  
> Se è stato abilitato il monitoraggio per un pool, è possibile disabilitare il processo di raccolta dei dati di monitoraggio senza dover modificare la topologia: Lync Server Management Shell consente di disabilitare (e successivamente riabilitare) la registrazione dettagli chiamata (CDR) o la qualità raccolta dati di esperienza (QoE). Per ulteriori informazioni, vedere la sezione relativa alla configurazione delle impostazioni di registrazione dettagli chiamata e QoE di questa documentazione.



</div>

Un altro importante miglioramento del monitoraggio in Lync Server 2013 è il fatto che i rapporti di monitoraggio di Lync Server ora supportano IPv6: i report che utilizzano il campo indirizzo IP visualizzeranno gli indirizzi IPv4 o IPv6 a seconda di quanto segue: 1) la query SQL utilizzata. e 2) dove l'indirizzo IPv6 è memorizzato o meno nel database di monitoraggio.

<div>


> [!NOTE]  
> Verificare che il tipo di avvio del servizio SQL Server Agent sia automatico e che il servizio SQL Server Agent sia in esecuzione per l'istanza di SQL che contiene i database di monitoraggio, in modo che i processi di manutenzione di SQL Server di monitoraggio predefiniti possano essere eseguiti sulla base pianificata sotto il controllo del servizio SQL Server Agent.



</div>

In questa documentazione viene illustrato il processo di installazione e configurazione dei rapporti di monitoraggio e monitoraggio per Lync Server 2013. Sono fornite istruzioni dettagliate per le seguenti operazioni:

  - Abilitare il monitoraggio nella topologia e associare un archivio di monitoraggio a un pool Front End.

  - Installare SQL Server Reporting Services e i report di monitoraggio di Lync Server. I report di monitoraggio sono rapporti preconfigurati che forniscono visualizzazioni diverse nelle informazioni archiviate in un database di monitoraggio.

  - Configurare la raccolta dei dati di registrazione dettagli chiamata (CDR) e qualità percepita dagli utenti (QoE). La registrazione dettagli chiamata consente di monitorare l'utilizzo delle funzionalità di Lync Server, ad esempio le chiamate telefoniche VoIP (Voice over IP). messaggistica istantanea (IM); trasferimenti di file; Servizi di conferenza audio/video (A/V); e sessioni di condivisione applicazioni. Le metriche QoE tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, includendo informazioni quali il numero di pacchetti di rete persi, i rumori di fondo e la quantità di "instabilità" (differenze nel ritardo dei pacchetti.

  - Eliminare manualmente i record CDR e/o QoE dal database di monitoraggio.

</div>

<span> </span>

</div>

</div>

</div>

