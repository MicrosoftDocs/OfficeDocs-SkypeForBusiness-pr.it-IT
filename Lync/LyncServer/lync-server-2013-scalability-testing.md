---
title: Test di scalabilità di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4495524d7ac4e6348f86b84a8b5f860bd9a1db3f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a>Test della scalabilità in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Lync Server 2013 fornisce l'infrastruttura server per tutte le comunicazioni in tempo reale di Lync Server, tra cui la messaggistica istantanea e la presenza, le conferenze e la VoIP aziendale. Sono incluse tutte le funzionalità che utilizzano le risorse hardware di un pool di Lync Server 2013 e, pertanto, influiscono sulle prestazioni e sulla scalabilità. Non tutte le organizzazioni si avvalgono di tutte le funzionalità nello stesso modo.

Alcune organizzazioni ad esempio possono utilizzare molto frequentemente i video nelle conferenze, mentre altre possono utilizzarli raramente o addirittura non utilizzarli affatto. Alcune organizzazioni preferiscono la condivisione delle diapositive di PowerPoint alla condivisione delle applicazioni, mentre altre preferiscono il contrario. Le organizzazioni che distribuiscono VoIP aziendale potrebbero o meno utilizzare l'applicazione Response Group in modo pesante. La maggior parte delle organizzazioni distribuisce i server di monitoraggio, ma non molti di essi distribuiscono i server di archiviazione. Le organizzazioni inoltre non dispongono tutte delle stesse infrastrutture, anche in termini di capacità hardware, capacità di rete e numero e dimensione dei pool distribuiti. La diversità di funzionalità e infrastrutture pone una sfida ai fini del testing della scalabilità, in quanto non si riescono a simulare tutte le combinazioni di funzionalità e infrastrutture possibili.

Per determinare il supporto della scalabilità per Lync Server, è possibile eseguire test utilizzando contemporaneamente tutte le funzionalità di Lync Server, in base a un modello di utilizzo medio (modello utente). Per determinare un modello utente appropriato per i carichi di lavoro di Lync Server, vengono analizzati molti punti dati, inclusi i sondaggi dei clienti, i commenti e suggerimenti del programma Analisi utilizzo software Microsoft, i dati di uso di Lync Server provenienti dal reparto IT interno di Microsoft. e dati estratti dal servizio Live Meeting. In molti casi il modello utente tende a preferire i carichi più pesanti in modo da lasciare un margine adeguato per l'utilizzo all'interno di un'organizzazione.

Nei test di scalabilità sono stati configurati i pool di Lync Server 2013 in base alle specifiche hardware e software consigliate, tra cui i componenti dell'infrastruttura, ad esempio servizi di dominio Active Directory, dispositivi di bilanciamento del carico hardware e firewall. Gli ambienti di Lync Server sono configurati il più vicino possibile agli ambienti tipici del mondo reale. È quindi possibile utilizzare lo strumento Lync Server 2013 stress and performance per simulare i carichi di Lync Server 2013 (in base al modello utente). .

Vengono eseguite più iterazioni dei test di scalabilità, incluse più esecuzioni di prova della durata di tre settimane. I risultati di tutti i test vengono utilizzati per l'ottimizzazione delle prestazioni e la verifica del supporto per i numeri di scalabilità previsti nel modello utente.

</div>

<span> </span>

</div>

</div>

</div>

