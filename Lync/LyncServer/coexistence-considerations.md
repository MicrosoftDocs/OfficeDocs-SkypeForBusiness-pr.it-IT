---
title: Considerazioni sulla coesistenza
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e53c57b90a85024ed5375129ce23c6ff0060edc4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>Considerazioni sulla coesistenza

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-06_

Dopo la migrazione, esisterà solo un Lync Server 2013, il pool di server di chat persistente e sarà possibile rimuovere la Commissione dalla distribuzione legacy.

Prima che la migrazione venga completata e prima di aver disattivato completamente la distribuzione del server di chat di gruppo corrente, è possibile che si disponga di una delle distribuzioni seguenti:

  - Lync Server 2013, pool di server di chat persistente, che deve essere ospitato in un pool di Lync Server 2013.

  - Lync Server 2010, pool di chat di gruppo, che deve essere ospitato in un pool di Lync Server 2010.

  - Pool di chat di gruppo di Office Communications Server 2007 R2, che deve essere ospitato in un pool di Office Communications Server 2007 R2.

Queste distribuzioni possono essere affiancate. Tuttavia, le categorie, le sale e i componenti aggiuntivi di una distribuzione non interagiscono con quelli della distribuzione che lo accompagna.

Usando la configurazione manuale, un client legacy (client di chat di gruppo) può connettersi a un pool alla volta per Office Communications Server 2007 R2, Lync Server 2010, Group Chat o Lync Server 2013.

Lync 2013 (client) può interagire solo con Lync Server 2013, il pool di server di chat persistente, non con i pool di server di chat di gruppo legacy. Per usare la chat persistente in un Lync 2013 (client), l'utente deve essere ospitato in Lync 2013 e abilitato per criteri.

</div>

<span> </span>

</div>

</div>

</div>

