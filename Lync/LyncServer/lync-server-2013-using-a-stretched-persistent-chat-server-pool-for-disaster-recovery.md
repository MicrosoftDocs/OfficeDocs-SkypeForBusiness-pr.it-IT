---
title: Utilizzo di un pool di server Chat persistente esteso per il ripristino di emergenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae23ed2d12548388cd1462aad653de4652633dc
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Utilizzo di un pool di server Chat persistente esteso per il ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-06_

La soluzione di ripristino di emergenza per il server di chat persistente è basata su un pool di server di chat persistente allungato. Questa operazione è simile alla resilienza del sito metropolitano in Lync Server 2010; Tuttavia, non esiste alcun requisito per una VLAN (Virtual Local Area Network) allungata. Allungando il pool di server di chat persistente, essenzialmente si configura un pool nella topologia in modo logico, ma si posiziona fisicamente i server nel pool in due centri dati diversi. Configurare il mirroring di SQL Server per il database nello stesso modo e distribuire il database e lo specchio nello stesso centro dati. È necessario configurare un database di backup nel centro dati secondario (con uno specchio facoltativo per ottenere una disponibilità elevata durante il ripristino di emergenza). Questo è il database di backup usato per il failover durante il ripristino di emergenza.

Per informazioni dettagliate su come configurare il mirroring di SQL Server per una disponibilità elevata, vedere [mirroring di SQL Server in Lync server 2013](lync-server-2013-sql-server-mirroring.md). Per informazioni dettagliate sul mancato rispetto del database per il ripristino di emergenza, vedere [configurazione della distribuzione di log di SQL Server in Lync server 2013 per il database primario del server di chat persistente](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) e [configurazione del log shipping di SQL Server tra lo specchio principale e il database secondario del log shipping in Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).

</div>

<span> </span>

</div>

</div>

</div>

