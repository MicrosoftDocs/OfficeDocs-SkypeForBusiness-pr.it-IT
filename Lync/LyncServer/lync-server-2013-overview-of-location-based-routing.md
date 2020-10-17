---
title: 'Lync Server 2013: Panoramica del routing di Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48fee2b9db45519ff4773b4dfe47b33745e5fb10
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520963"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Panoramica del routing Location-Based in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Location-Based routing introduce un nuovo set di regole che consente di modificare il routing delle chiamate PSTN nazionali e internazionali per evitare il bypass a pedaggio. Location-Based routing offre la possibilità di applicare queste regole a aree specifiche, gateway specifici o solo a un insieme specifico di utenti.

Negli scenari seguenti vengono illustrati i principali tipi di restrizioni Location-Based il routing può applicare:

  - Chiamate in uscita – Location-Based il routing può applicare le chiamate in uscita per l'ingresso da un gateway PSTN che si trova nella stessa regione in cui il chiamante deve impedire il bypass a pedaggio PSTN, impedendo le chiamate in uscita da un gateway PSTN che si trova in un'area diversa come chiamante.

  - Ingress calls – Location-Based routing può impedire le chiamate PSTN in arrivo per suonare gli endpoint di Lync se il gateway PSTN che instrada la chiamata in arrivo non si trova nella stessa area dell'utente denominato Lync.

  - Aree sconosciute – Location-Based il routing limita le chiamate PSTN in ingresso e in uscita da e verso gli utenti che si trovano in posizioni Indeterminate (ad esempio, gli utenti remoti che si connettono da Internet o che si trovano in aree sconosciute).

  - Aree internazionali – Location-Based il routing impone il routing delle chiamate in uscita attraverso i gateway PSTN internazionali se non è possibile trovare un gateway locale per la posizione dell'utente.

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del routing Location-Based in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

