---
title: Rimuovere un Front End Server da un pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b798674173d14c2bd3f5638f6049c3a723786f91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a>Rimuovere un Front End Server da un pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

Il server front-end di Microsoft Lync Server 2010 Enterprise Edition non può esistere come computer autonomo. Deve essere definito come pool Front-End, anche se è presente solo un singolo computer nel pool.

Questo argomento illustra il processo di rimozione di un singolo server front-end da un pool Front-end esistente. Se il server front-end è l'ultimo server del pool o se si sta rimuovendo completamente il pool, vedere [rimuovere il pool Front-end o il server Standard Edition](remove-front-end-pool-or-standard-edition-server.md). Non è necessario rimuovere i singoli server front-end prima di rimuovere il pool Front-end. Quando si rimuove il pool, si rimuove ogni server front-end.

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>Per rimuovere un server front-end da un pool

1.  Aprire il server front-end di Lync Server 2013, aprire Generatore di topologia.

2.  Passare al nodo Lync Server 2010.

3.  Espandi i **pool Front End di Enterprise Edition**, Espandi il pool Front end con il front end server che vuoi rimuovere, fai clic con il pulsante destro del mouse sul server front-end che vuoi rimuovere e quindi fai clic su **Elimina**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

