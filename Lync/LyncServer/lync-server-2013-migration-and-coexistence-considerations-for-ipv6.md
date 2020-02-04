---
title: 'Lync Server 2013: Considerazioni sulla migrazione e la coesistenza per IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5785b270aa3070c2b1592112ab4d5ae582e52bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Considerazioni sulla migrazione e la coesistenza per IPv6 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-14_

IP versione 6 (IPv6) non è supportato in Lync Server 2010 o Office Communications Server. Per scopi di pilotaggio, è possibile testare la coesistenza di Lync Server 2010 e Lync Server 2013. È consigliabile che tutti i pool per un sito centrale specifico vengano aggiornati a Lync Server 2013 prima di abilitare IPv6 (rete dual-stack) per uno dei pool. Se è necessario configurare solo un pool per IPv6, è consigliabile configurare un pool solo IPv6 nell'ambiente lab per i test.

Gli scenari seguenti sono supportati durante la migrazione e la coesistenza:

  - Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2 pool in modalità IPv4, che coesiste con Lync Server 2013 in modalità a doppio stack.

  - Pool di Lync Server 2013 in modalità solo IPv6, se il pool solo IPv6 è siloed.

</div>

<span> </span>

</div>

</div>

</div>

