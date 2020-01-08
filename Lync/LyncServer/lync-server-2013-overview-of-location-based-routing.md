---
title: 'Lync Server 2013: Panoramica del routing basato sulla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b3a5cb2e89376a356daf54c6e5bc443ab52207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Panoramica del routing basato sulla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Il routing basato sulla posizione introduce un nuovo set di regole che modifica il routing delle chiamate PSTN nazionali e internazionali per evitare l'esclusione dei pedaggi. Il routing basato sulla posizione offre la flessibilità per l'ambito di queste regole per specifiche aree geografiche, gateway specifici o solo set di utenti specifici.

Gli scenari seguenti illustrano i tipi principali di restrizioni che il routing basato sulla posizione può applicare:

  - Le chiamate in uscita: il routing basato sulla posizione può applicare le chiamate in uscita a un gateway PSTN che si trova nella stessa area geografica in cui il chiamante deve impedire l'esclusione del pedaggio PSTN, impedendo le chiamate all'uscita da un gateway PSTN situato in un'area diversa come chiamante.

  - Chiamate di ingresso: il routing basato sulla posizione può impedire alle chiamate PSTN in arrivo di squillare gli endpoint di Lync se il gateway PSTN che instrada la chiamata in arrivo non si trova nella stessa area dell'utente di Lync chiamato.

  - Aree sconosciute: il routing basato sulla posizione limita le chiamate PSTN in ingresso e in uscita a e da utenti che si trovano in posizioni Indeterminate (ad esempio, gli utenti remoti che si connettono da Internet o si trovano in aree sconosciute).

  - Aree internazionali: il routing basato sulla posizione impone il routing delle chiamate in uscita tramite gateway PSTN internazionali se non è possibile trovare un gateway locale nella posizione dell'utente.

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del routing in base alla posizione in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

