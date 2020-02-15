---
title: Utilizzo di generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza
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
ms.openlocfilehash: fc0f47bf8e0a0aec5d2a2374decd79ce2bae77f2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Utilizzo di generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

Eseguire i passaggi seguenti all'interno di generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente.

1.  Aggiungere i database mirror e gli archivi SQL Server del database secondario di log shipping.

2.  Modificare le proprietà del servizio del server Chat persistente in:
    
    1.  Abilitare il mirroring per il database primario.
    
    2.  Aggiungere l'archivio SQL Server mirror primario.
    
    3.  Abilitare il database di log shipping di SQL Server.
    
    4.  Aggiungere l'archivio SQL Server secondario di log shipping di SQL Server.
    
    5.  Aggiungere il mirror dell'archivio SQL Server per il database secondario.
    
    6.  Pubblicare la topologia.

</div>

<span> </span>

</div>

</div>

</div>

