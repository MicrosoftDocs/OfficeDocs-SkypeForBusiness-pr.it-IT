---
title: Lync Server 2013 relazioni di registrazione di backup
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac47dcda07d7c0ca368cc572ccfafe2c6c95b2f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Relazioni di registrazione di backup in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-28_

Oltre ad offrire funzioni di ripristino di emergenza, due pool accoppiati funzionano come registrar di backup l'uno per l'altro. In Lync Server 2013, le relazioni di registrazione di backup tra pool Front End sono sempre 1:1 e reciproche. Pertanto, se il P1 è il backup del P2, il P2 sarà il backup del P1, e nessuno dei due potrà essere il backup di un altro pool Front End. Si tratta di una modifica da Lync Server 2010, in cui le relazioni di backup del pool Front end potrebbero essere numerose.

Anche se le relazioni di backup tra due pool Front end devono essere 1:1 e simmetriche, ogni pool Front end può essere sempre anche il servizio di registrazione di backup per un numero qualsiasi di Survivable Branch Appliance, come in Lync Server 2010.

Si noti che Lync Server 2013 non estende il supporto per il ripristino di emergenza agli utenti ospitati in un Survivable Branch Appliance. Se un pool Front end che funge da backup per un Survivable Branch Appliance diminuisce, gli utenti che hanno effettuato l'accesso a Survivable Branch Appliance rientrano in modalità di resilienza anche dopo che gli utenti ospitati nel pool Front end non sono riusciti a eseguire il backup nel pool Front end.

</div>

<span> </span>

</div>

</div>

</div>

