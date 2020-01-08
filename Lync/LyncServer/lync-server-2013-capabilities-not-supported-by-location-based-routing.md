---
title: 'Lync Server 2013: Funzionalità non supportate dal routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ca2d775fc17d0919ceb31a38b242e54d37b6a55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Funzionalità non supportate dal routing in base alla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-03-12_

Il routing basato sulla posizione non si applica ai tipi di interazioni seguenti. Il routing basato sulla posizione non viene applicato quando gli endpoint di Lync interagiscono con endpoint PSTN usando queste funzionalità.

  - Accesso esterno PSTN alle conferenze

  - Chiamate PSTN in arrivo e in uscita tramite Response Group

  - Parcheggio di chiamata o recupero di chiamate PSTN tramite Call Park

  - Chiamate PSTN in arrivo per il servizio annunci

  - Chiamate PSTN in arrivo recuperate tramite raccolta chiamate di gruppo

Per applicare regole di routing basate sul percorso ai tipi di interazioni nell'elenco seguente, è necessario abilitare il routing basato sulla posizione per i servizi di conferenza:

  - Chiamata PSTN dalle conferenze

  - Escalation dalle conversazioni audio peer-to-peer alle conferenze che coinvolgono endpoint PSTN

  - Trasferimenti consultivi che coinvolgono endpoint PSTN

Per abilitare il routing basato sulla posizione per i servizi di conferenza, vedere [routing basato sulla posizione per i servizi di conferenza in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del routing in base alla posizione in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

