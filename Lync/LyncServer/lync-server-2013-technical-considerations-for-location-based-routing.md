---
title: 'Lync Server 2013: considerazioni tecniche per il routing in base alla posizione'
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
ms.openlocfilehash: fcdebdccd0584d31b27120709212be674e8d3c2a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Considerazioni tecniche per il routing in base alla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-09_

Durante la pianificazione del routing in base alla posizione, è opportuno considerare l'impatto sui seguenti scenari.

<div>

## <a name="disaster-recovery"></a>Ripristino di emergenza

Durante un failover dal pool primario a un pool di backup e durante il ripristino di normali operazioni al pool primario, il routing basato sulla posizione rimane applicato sempre durante una procedura di ripristino e di emergenza.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

La configurazione del routing in base alla posizione ha un impatto sulla pianificazione del percorso in cui vengono distribuiti i gateway associati ai Survivable Branch Appliance. Il gateway associato all'ASB deve trovarsi nello stesso sito di rete del Survivable Branch Appliance. in caso contrario, gli utenti ospitati nel Survivable Branch Appliance non saranno autorizzati a inserire le chiamate in uscita se è configurato il routing basato sulla posizione. Quando la connessione WAN tra il Survivable Branch Appliance e il sito centrale è inattiva, le restrizioni di routing basate sul percorso rimangono applicate.

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

