---
title: Connessione di Survivable Branch Appliance al pool Front End di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a637716f1e5b1a2082f694554951d42f36978f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502023"
---
# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Connessione di Survivable Branch Appliance al pool Front End di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-05_

Ogni Survivable Branch Appliance (SBA) è associato a un pool Front End, che funge da registrar di backup per la SBA. Quando il pool Front end viene aggiornato a Lync Server 2013, è necessario che l'SBA sia dissociata dal pool Front end mentre il pool Front end viene aggiornato. Dopo l'aggiornamento del pool Front End, l'SBA può essere riassociato al pool Front end. Si tratta di eliminare l'ASB dalla topologia in Generatore di topologie e quindi aggiungere di nuovo l'SBA a Generatore di topologie. Gli utenti ospitati nell'ASB devono essere spostati in un altro pool Front end prima di rimuovere la SBA dalla topologia. Dopo aver aggiunto la SBA alla topologia, gli utenti possono essere spostati di nuovo nell'ASB.

La procedura è sintetizzata sotto.

1.  Spostare gli utenti di succursale presenti in SBA in un altro pool Front end.

2.  Rimuovere SBA dalla topologia per dissociare il pool Front end esistente come registrazione di backup.

3.  Aggiornare il pool Front end a Microsoft Lync Server 2013.

4.  Aggiungere nuovamente l'SBA alla topologia.

5.  Associare il nuovo pool Front end all'ASB come registrar di backup.

6.  Trasferire nuovamente gli utenti dei siti di succursale nell'SBA.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Aggiungere il sito di succursale del Survivable Branch Appliance di Lync Server 2013 alla topologia](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Aggiungere il sito di succursale del Survivable Branch Appliance di Lync Server 2010 alla topologia](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

