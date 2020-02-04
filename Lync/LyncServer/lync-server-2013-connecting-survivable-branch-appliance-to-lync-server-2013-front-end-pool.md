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
ms.openlocfilehash: d73806f481cfe7c44a5eb9507d043565765a08f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Connessione di Survivable Branch Appliance al pool Front End di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

Ogni Survivable Branch Appliance (SBA) è associato a un pool Front-End, che funge da registrar di backup per l'SBA. Quando il pool Front-end viene aggiornato a Lync Server 2013, l'SBA deve essere dissociato dal pool Front-end mentre il pool Front-end viene aggiornato. Dopo l'aggiornamento del pool Front-End, l'SBA può essere riassociato al pool Front-end. In questo caso, è necessario eliminare l'SBA dalla topologia in Generatore di topologia e quindi aggiungere di nuovo l'SBA a Generatore di topologie. Gli utenti residenti nell'ASB devono essere spostati in un altro pool Front-end prima di rimuovere l'SBA dalla topologia. Dopo aver aggiunto l'SBA alla topologia, questi utenti possono essere spostati di nuovo nella SBA.

Questi passaggi sono riepilogati di seguito:

1.  Sposta gli utenti di Branch residenti in SBA in un altro pool Front-end.

2.  Rimuovi SBA dalla topologia per dissociare il pool Front end esistente come registrar di backup.

3.  Aggiornare il pool Front-end a Microsoft Lync Server 2013.

4.  Aggiungere SBA di nuovo alla topologia.

5.  Associare il nuovo pool Front-end alla SBA come registrar di backup.

6.  Riportare gli utenti di Branch nell'SBA.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Aggiungere un sito di succursale Survivable Branch Appliance di Lync Server 2013 alla topologia](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Aggiungere un sito di succursale Survivable Branch Appliance di Lync Server 2010 alla topologia](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

