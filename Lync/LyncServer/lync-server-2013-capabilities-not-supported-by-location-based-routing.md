---
title: 'Lync Server 2013: funzionalità non supportate dal routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff96f72ff7d71c005f97142ed9844b7c9509e022
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Funzionalità non supportate dal routing in base alla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-03-12_

Il routing in base alla posizione non si applica ai tipi di interazioni seguenti. Il routing in base alla posizione non viene applicato quando gli endpoint di Lync interagiscono con gli endpoint PSTN utilizzando queste funzionalità.

  - Accesso esterno PSTN alle conferenze

  - Chiamate PSTN in ingresso e in uscita tramite Response Group

  - Parcheggio di chiamata o recupero delle chiamate PSTN tramite il parcheggio di chiamata

  - Chiamate PSTN in arrivo per il servizio annunci

  - Chiamate PSTN in arrivo recuperate tramite raccolta chiamate di gruppo

Per applicare le regole di routing basate sul percorso ai tipi di interazioni nell'elenco seguente, è necessario abilitare il routing in base alla posizione per le conferenze:

  - Accesso esterno PSTN dalle conferenze

  - Escalation dalle conversazioni audio peer-to-peer ai servizi di conferenza che coinvolgono endpoint PSTN

  - Trasferimenti consultivi che coinvolgono endpoint PSTN

Per abilitare il routing in base alla posizione per le conferenze, vedere [routing in base alla posizione per le conferenze in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del routing in base alla posizione in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

