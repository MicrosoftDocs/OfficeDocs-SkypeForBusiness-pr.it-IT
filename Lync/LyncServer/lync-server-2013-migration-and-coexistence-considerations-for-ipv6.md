---
title: 'Lync Server 2013: considerazioni sulla migrazione e la coesistenza per IPv6'
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
ms.openlocfilehash: 449e1fa516f4817afcda30ba6ffac7db04d89e56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Considerazioni sulla migrazione e la coesistenza per IPv6 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-14_

IP versione 6 (IPv6) non è supportato in Lync Server 2010 o Office Communications Server. A scopo di pilotaggio, è possibile testare Lync Server 2010 e Lync Server 2013 dual-stack coesistenza. È consigliabile che tutti i pool di un determinato sito centrale vengano aggiornati a Lync Server 2013 prima di abilitare IPv6 (dual-stack Network) per uno qualsiasi dei pool. Se è necessario configurare un pool solo per IPv6, è consigliabile configurare un pool solo IPv6 nell'ambiente di prova a fini di test.

Durante la migrazione e in caso di coesistenza sono supportati gli scenari seguenti:

  - Lync Server 2013, Lync Server 2010 e i pool di Office Communications Server 2007 R2 in modalità IPv4, coesistenti con Lync Server 2013 in modalità dual stack.

  - Pool Lync Server 2013 in modalità solo IPv6, se il pool IPv6 è solo silo.

</div>

<span> </span>

</div>

</div>

</div>

