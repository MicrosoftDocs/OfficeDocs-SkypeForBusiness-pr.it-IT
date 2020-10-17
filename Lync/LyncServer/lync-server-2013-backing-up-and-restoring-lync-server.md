---
title: 'Lync Server 2013: backup e ripristino di Lync Server'
description: 'Lync Server 2013: backup e ripristino di Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1a7024b2264fb895d1562a6da0775f9397644b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543782"
---
# <a name="backing-up-and-restoring-lync-server-2013"></a>Backup e ripristino di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

In questa sezione sono disponibili le procedure consigliate per il backup dei dati di Lync Server 2013 e per il ripristino in caso di errore. Queste procedure consigliate sono valide per le situazioni seguenti:

  - Un intero pool di Lync Server di qualsiasi tipo (front end server, server perimetrale, Mediation Server, server Chat persistente o Director) oppure un singolo server in uno di questi pool.

  - Server di gestione centrale

  - Un server Standard Edition

  - Server back-end Enterprise Edition

  - Archivio file

  - Database di archiviazione, database di monitoraggio o database di chat persistente

In questa sezione non sono incluse informazioni relative al ripristino di un intero sito o allo sviluppo di un sito di standby. Per informazioni dettagliate sullo sviluppo di una soluzione di ripristino di emergenza con pool Front End abbinati, vedere [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Si tratta del metodo consigliato per la pianificazione del ripristino di emergenza.

Se i pool Front End associati sono stati distribuiti, se uno di questi pool ha esito negativo e diventa irrecuperabile, è possibile ripristinare il pool con un nuovo nome di dominio completo (FQDN) dal pool associato. Per informazioni dettagliate sulla procedura per eseguire questo ripristino, vedere [failover di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md). Inoltre, se si desidera ricreare un pool non riuscito e irrecuperabile che faceva parte di una coppia front end, è possibile utilizzare la procedura descritta in [esecuzione di un failover del pool ABC front end in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).

La metodologia descritta in questo documento implica considerazioni speciali durante la fase di pianificazione. Per informazioni dettagliate, vedere [establishing a backup and Restoration Plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Preparazione per il backup e il ripristino di Lync Server 2013](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Backup dei dati e delle impostazioni in Lync Server 2013](lync-server-2013-backing-up-data-and-settings.md)

  - [Ripristino dei dati e delle impostazioni in Lync Server 2013](lync-server-2013-restoring-data-and-settings.md)

  - [Fogli di lavoro per il backup e il ripristino di Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

