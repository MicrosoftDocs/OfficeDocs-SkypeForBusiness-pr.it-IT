---
title: 'Lync Server 2013: Panoramica del routing in base alla posizione'
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
ms.openlocfilehash: 85d24aeb94a0c16e93d885c5b6db20385cdf0f26
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Panoramica del routing in base alla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Il routing in base alla posizione introduce un nuovo set di regole che consente di modificare il routing delle chiamate PSTN nazionali e internazionali per evitare il bypass a pedaggio. Il routing in base alla posizione offre la possibilità di applicare queste regole a aree specifiche, gateway specifici o solo a un insieme specifico di utenti.

Negli scenari seguenti vengono illustrati i principali tipi di restrizioni che il routing in base alla posizione può applicare:

  - Chiamate in uscita – il routing in base alla posizione può imporre le chiamate in uscita all'accesso da un gateway PSTN che si trova nella stessa regione in cui il chiamante deve impedire il bypass a pedaggio PSTN, impedendo le chiamate all'uscita da un gateway PSTN situato in un'area diversa come chiamante.

  - Chiamate in ingresso – il routing in base alla posizione può impedire le chiamate PSTN in arrivo per suonare gli endpoint di Lync se il gateway PSTN che instrada la chiamata in arrivo non si trova nella stessa area dell'utente denominato Lync.

  - Aree sconosciute – il routing in base alla posizione limita le chiamate PSTN in ingresso e in uscita da e verso gli utenti che si trovano in posizioni Indeterminate (ad esempio, gli utenti remoti che si connettono da Internet o che si trovano in aree sconosciute).

  - Regioni internazionali – il routing in base alla posizione impone il routing delle chiamate in uscita attraverso i gateway PSTN internazionali se non è possibile trovare un gateway locale per la posizione dell'utente.

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del routing in base alla posizione in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

