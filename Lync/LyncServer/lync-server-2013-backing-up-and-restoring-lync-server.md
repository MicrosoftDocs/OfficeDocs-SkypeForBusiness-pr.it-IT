---
title: 'Lync Server 2013: eseguire il backup e il ripristino di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0cf9f9baabd095e54373c31acd4f4522974a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>Backup e ripristino di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

In questa sezione sono disponibili le procedure consigliate per eseguire il backup dei dati di Lync Server 2013 e per ripristinarlo in caso di errore. Queste procedure consigliate si applicano alle situazioni seguenti:

  - Un intero pool di Lync Server di qualsiasi tipo (front end server, Edge Server, Mediation Server, Persistent Chat Server o Director) o un singolo server in uno di questi pool.

  - Server di gestione centrale

  - Un server Standard Edition

  - Server back-end Enterprise Edition

  - Un archivio di file

  - Database di archiviazione, database di monitoraggio o database di chat persistente

Questa sezione non include informazioni sul ripristino di un intero sito o per lo sviluppo di un sito standby. Per informazioni dettagliate sullo sviluppo di una soluzione di ripristino di emergenza con pool Front-End associati, vedere [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Questo è il metodo consigliato per pianificare il ripristino di emergenza.

Se sono stati distribuiti pool Front-End associati, se uno di questi pool non riesce e diventa irrecuperabile, è possibile ripristinare questo pool con un nuovo nome di dominio completo (FQDN) dal pool associato. Per informazioni dettagliate sui passaggi per eseguire questo ripristino, vedere [mancanza di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md). Inoltre, se in seguito si vuole ricreare un pool non riuscito e non recuperabile che faceva parte di una coppia front-end, è possibile usare la procedura descritta in [esecuzione di un failover del pool di front end ABC in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).

La metodologia descritta in questo documento comporta considerazioni particolari durante la fase di pianificazione. Per informazioni dettagliate, vedere [creazione di un piano di backup e ripristino per Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Preparazione per il backup e il ripristino di Lync Server 2013](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Backup dei dati e delle impostazioni in Lync Server 2013](lync-server-2013-backing-up-data-and-settings.md)

  - [Ripristino di dati e impostazioni in Lync Server 2013](lync-server-2013-restoring-data-and-settings.md)

  - [Fogli di lavoro di backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

