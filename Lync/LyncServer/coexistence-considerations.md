---
title: Considerazioni sulla coesistenza
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: a7052042afbc3927e1047a9c2fbb30a71168f317
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>Considerazioni sulla coesistenza

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

Dopo la migrazione, esisterà solo un pool di server Chat persistente di Lync Server 2013 ed è possibile rimuovere le autorizzazioni della distribuzione legacy.

Prima del completamento della migrazione e prima di rimuovere completamente la distribuzione di Group Chat Server corrente, è possibile che si disponga di una delle distribuzioni seguenti:

  - Lync Server 2013, pool di server Chat persistente, che deve essere ospitato in un pool di Lync Server 2013.

  - Lync Server 2010, pool di chat di gruppo, che deve essere ospitato in un pool di Lync Server 2010.

  - Pool di chat di gruppo di Office Communications Server 2007 R2, che deve essere ospitato in un pool di Office Communications Server 2007 R2.

Queste distribuzioni possono esistere fianco a fianco. Tuttavia, le categorie, le sale e i componenti aggiuntivi in una distribuzione non interagiscono con quelli nella distribuzione di accompagnamento.

Se si utilizza la configurazione manuale, un client legacy (client Group Chat) può connettersi a un pool alla volta per Office Communications Server 2007 R2, Lync Server 2010, Group Chat o Lync Server 2013.

Lync 2013 (client) è in grado di interagire solo con Lync Server 2013, il pool di server Chat persistente, non con i pool di server di chat di gruppo legacy. Per utilizzare la chat persistente in un Lync 2013 (client), è necessario che l'utente sia ospitato in Lync 2013 e sia abilitato dal criterio.

</div>

<span> </span>

</div>

</div>

</div>

