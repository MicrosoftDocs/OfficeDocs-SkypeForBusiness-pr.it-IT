---
title: Utilizzo di un pool di server Chat persistente esteso per il ripristino di emergenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c09231abfae7bbcc32083d7db72d8a4be79ecff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535923"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Utilizzo di un pool di server Chat persistente esteso per il ripristino di emergenza in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

La soluzione di ripristino di emergenza per il server Chat persistente è basata su un pool di server Chat persistente esteso. Questo è simile alla resilienza del sito metropolitano in Lync Server 2010; Tuttavia, non è previsto alcun requisito per una rete LAN (Virtual Local Area Network) estesa. Se si estende il pool di server Chat persistente, è essenzialmente necessario configurare un pool nella topologia logicamente, ma i server del pool vengono fisicamente posizionati in due diversi Data Center. Configurare il mirroring di SQL Server per il database nello stesso modo e distribuire il database e il mirror nello stesso data center. È necessario configurare un database di backup nel data center secondario (con un mirror facoltativo per garantire una disponibilità elevata durante il ripristino di emergenza). Si tratta del database di backup utilizzato per il failover durante il ripristino di emergenza.

Per informazioni dettagliate su come configurare il mirroring di SQL Server per la disponibilità elevata, vedere [mirroring di SQL Server in Lync server 2013](lync-server-2013-sql-server-mirroring.md). Per informazioni dettagliate sul failover del database per il ripristino di emergenza, vedere [configurazione del log shipping di SQL Server in Lync server 2013 per il database primario del server Chat persistente](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) e [configurazione del log shipping di SQL Server tra il mirror primario e il database secondario di log shipping in Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).

</div>

<span> </span>

</div>

</div>

</div>

