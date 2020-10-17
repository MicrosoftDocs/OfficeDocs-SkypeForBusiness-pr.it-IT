---
title: "Lync Server 2013: pianificazione dell'abbinamento dei pool Front End"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 484a19b890602ea338f5e98a126a13582ce7e931
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522193"
---
# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Pianificazione dell'abbinamento dei pool Front end in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

Per le migliori funzionalità di ripristino di emergenza in Lync Server 2013, distribuire coppie di pool Front end tra due siti dislocati in aree geografiche diverse. Ogni sito contiene un pool Front end che è associato a un pool Front End corrispondente nell'altro sito. Entrambi i siti sono attivi e il servizio di backup di Lync Server fornisce la replica dei dati in tempo reale per mantenere sincronizzati i pool. Il servizio di backup è una nuova funzionalità di Lync Server 2013, progettata per supportare la soluzione di ripristino di emergenza. L'installazione viene eseguita in un pool Front end quando si associa il pool a un altro pool Front end.

Se il pool in un sito ha esito negativo, è possibile eseguire il failover degli utenti da tale pool al pool nell'altro sito, che fornisce quindi Servizi a tutti gli utenti in entrambi i pool. A scopo di pianificazione della capacità, ogni pool deve essere progettato per gestire i carichi di lavoro di tutti gli utenti in entrambi i pool in caso di emergenza.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Opzioni di abbinamento del pool supportate e procedure consigliate per Lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Relazioni di registrazione di backup in Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Tempo di ripristino per il failover del pool e il failback del pool in Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Failover dell'archivio di gestione centrale in Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Sicurezza dei dati per l'abbinamento del pool Front end in Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

