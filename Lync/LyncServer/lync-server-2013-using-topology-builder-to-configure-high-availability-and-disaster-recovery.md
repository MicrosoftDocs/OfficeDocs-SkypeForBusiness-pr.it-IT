---
title: Utilizzo di Generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73bcd2c2892e4e121512ae852d5920d600af91ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Utilizzo di Generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-06_

Eseguire i passaggi seguenti in Generatore di topologia per configurare l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente.

1.  Aggiungere i database mirror e il database secondario del log shipping di SQL Server Store.

2.  Modificare le proprietà del servizio server di chat persistente in:
    
    1.  Abilitare il mirroring per il database primario.
    
    2.  Aggiungere il mirror principale di SQL Server Store.
    
    3.  Abilitare il database di log shipping di SQL Server.
    
    4.  Aggiungere l'archivio SQL Server log shipping secondario di SQL Server.
    
    5.  Aggiungere il mirror di SQL Server Store per il database secondario.
    
    6.  Pubblicare la topologia.

</div>

<span> </span>

</div>

</div>

</div>

