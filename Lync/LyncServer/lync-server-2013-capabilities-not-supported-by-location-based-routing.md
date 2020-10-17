---
title: 'Lync Server 2013: funzionalità non supportate dal routing di Location-Based'
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
ms.openlocfilehash: 40a7d32c0448abfe3552fdfe657b9c6bec960a08
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512863"
---
# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Funzionalità non supportate dal routing Location-Based in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-03-12_

Location-Based routing non si applica ai tipi di interazioni seguenti. Location-Based il routing non viene applicato quando gli endpoint di Lync interagiscono con gli endpoint PSTN utilizzando queste funzionalità.

  - Accesso esterno PSTN alle conferenze

  - Chiamate PSTN in ingresso e in uscita tramite Response Group

  - Parcheggio di chiamata o recupero delle chiamate PSTN tramite il parcheggio di chiamata

  - Chiamate PSTN in arrivo per il servizio annunci

  - Chiamate PSTN in arrivo recuperate tramite raccolta chiamate di gruppo

Per applicare le regole di routing Location-Based ai tipi di interazioni presenti nell'elenco seguente, è necessario abilitare Location-Based routing per le conferenze:

  - Accesso esterno PSTN dalle conferenze

  - Escalation dalle conversazioni audio peer-to-peer ai servizi di conferenza che coinvolgono endpoint PSTN

  - Trasferimenti consultivi che coinvolgono endpoint PSTN

Per abilitare il routing Location-Based per le conferenze, vedere [routing in base alla posizione per le conferenze in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del routing Location-Based in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

