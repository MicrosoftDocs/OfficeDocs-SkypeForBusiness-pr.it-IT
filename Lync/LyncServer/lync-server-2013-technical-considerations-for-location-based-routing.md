---
title: 'Lync Server 2013: Considerazioni tecniche per il routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 978590484cbb6bd3c23fac26422c186847662e49
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Considerazioni tecniche per il routing in base alla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-09_

Quando si pianifica il routing basato sulla posizione, è consigliabile considerare l'impatto sugli scenari seguenti.

<div>

## <a name="disaster-recovery"></a>Ripristino di emergenza

Durante un failover dal pool principale a un pool di backup e quando si ripristinano le normali operazioni nel pool principale, il routing basato sulla posizione rimane imposto in qualsiasi momento durante una procedura di emergenza e ripristino.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

La configurazione del routing basato sulla posizione ha un impatto sulla pianificazione della distribuzione dei gateway associati agli elettrodomestici Survivable Branch. Il gateway associato alla SBA deve trovarsi nello stesso sito di rete dell'appliance Survivable Branch; in caso contrario, gli utenti residenti nell'appliance Survivable Branch non saranno autorizzati a inserire chiamate in uscita se è configurato il routing basato sulla posizione. Quando la connessione WAN tra l'appliance Survivable Branch e il sito centrale è in calo, le restrizioni di routing basate sulla posizione restano applicate.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del routing in base alla posizione in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

