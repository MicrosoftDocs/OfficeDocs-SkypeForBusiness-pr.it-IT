---
title: "Lync Server 2013: Pianificazione dell'abbinamento dei pool Front End"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0445a6d952ba7311b8f6b5435c16d9e91de587f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Pianificazione dell'abbinamento dei pool Front End in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Per le migliori capacità di ripristino di emergenza in Lync Server 2013, distribuire coppie di pool Front-end in due siti dislocati geograficamente. Ogni sito contiene un pool Front-end che viene associato a un pool Front-End corrispondente nell'altro sito. Entrambi i siti sono attivi e il servizio di backup di Lync Server offre la replica dei dati in tempo reale per sincronizzare i pool. Il servizio di backup è una nuova funzionalità di Lync Server 2013, progettata per supportare la soluzione di ripristino di emergenza. Viene installata in un pool Front-end quando si associa il pool a un altro pool Front-end.

Se il pool in un sito non riesce, è possibile eseguire il failover degli utenti da tale pool al pool nell'altro sito, che fornisce quindi Servizi a tutti gli utenti in entrambi i pool. Per scopi di pianificazione della capacità, ogni pool deve essere progettato per gestire i carichi di lavoro di tutti gli utenti in entrambi i pool in caso di emergenza.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Opzioni di associazione e procedure consigliate per la combinazione di pool supportate per Lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Eseguire il backup delle relazioni di registrazione in Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Tempo di ripristino per il failover e il failback dei pool in Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Failover dell'archivio di gestione centrale in Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Sicurezza dei dati per l'abbinamento dei pool Front End in Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

