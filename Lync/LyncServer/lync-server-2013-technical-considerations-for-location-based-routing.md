---
title: 'Lync Server 2013: considerazioni tecniche per il routing di Location-Based'
description: 'Lync Server 2013: considerazioni tecniche per il routing Location-Based.'
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
ms.openlocfilehash: 54a025af81ab148ad41f95d0a8cf4f900beb7e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568052"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Considerazioni tecniche per il routing Location-Based in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-09_

Quando si pianifica Location-Based il routing, è opportuno considerare l'impatto sui seguenti scenari.

<div>

## <a name="disaster-recovery"></a>Ripristino di emergenza

Durante un failover dal pool primario a un pool di backup e durante il ripristino di normali operazioni nel pool primario, Location-Based il routing rimane applicato sempre durante una procedura di ripristino e di emergenza.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

La configurazione di Location-Based influisce sulla pianificazione del percorso in cui vengono distribuiti i gateway associati ai Survivable Branch Appliance. Il gateway associato all'ASB deve trovarsi nello stesso sito di rete del Survivable Branch Appliance. in caso contrario, gli utenti ospitati nel Survivable Branch Appliance non saranno autorizzati a inserire le chiamate in uscita se Location-Based il routing è configurato. Quando la connessione WAN tra il Survivable Branch Appliance e il sito centrale è inattiva, Location-Based restrizioni di routing restano applicate.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del routing Location-Based in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

