---
title: 'Lync Server 2013: posizione del gateway PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29898244dc0e54da2586d0a58212148c493b96db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512443"
---
# <a name="pstn-gateways-location-in-lync-server-2013"></a>Posizione del gateway PSTN in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-09_

Le chiamate instradate tramite gateway PSTN e PBX potrebbero richiedere Location-Based limitazioni del routing in base alla posizione di tali sistemi. Location-Based il routing può essere abilitato alla granularità per ogni base trunk.

Location-Based routing introduce il set di regole seguente quando è abilitato su un trunk:

  - Quando Location-Based routing è abilitato per ogni trunk, le regole definite su tale trunk verranno applicate solo alle chiamate instradate attraverso il trunk.

  - Per evitare che i pedaggi PSTN vengano ignorati in cui le chiamate provengono da un sito di rete diverso da quello del sito di rete in cui si trova il gateway PSTN, Location-Based routing introduce l'associazione di un sito di rete a un trunk specificato. In questo modo viene definito il sito di rete che consente di instradare le chiamate a un determinato trunk.

I trunk possono essere abilitati per il routing Location-Based in due modi:

  - Il trunk è definito per un gateway PSTN che egresses le chiamate alla rete PSTN. Le chiamate in arrivo instradate da un trunk di questo tipo verranno instradate solo agli endpoint situati all'interno dello stesso sito di rete del trunk.

  - Il trunk è definito per un peer di Mediation Server che non consente di uscire dalle chiamate agli utenti di servizi PSTN e con i telefoni legacy in posizioni statiche (ovvero telefoni PBX). Per questa configurazione specifica, tutte le chiamate in arrivo instradate da un trunk di questo tipo verranno considerate come originate dallo stesso sito di rete del trunk. Le chiamate provenienti da utenti PBX avranno lo stesso Location-Based l'applicazione di routing come utenti di Lync che si trovano nello stesso sito di rete del trunk. Se due sistemi PBX situati in siti di rete separati sono connessi tramite Lync Server, Location-Based routing consentirà il routing da un endpoint PBX in un sito di rete a un altro endpoint PBX nell'altro sito di rete. Questo scenario non verrà bloccato da Location-Based routing. Oltre a questo scenario e in modo analogo a quello di un utente Lync nello stesso percorso, gli endpoint connessi a un peer di Mediation Server con questa configurazione saranno in grado di effettuare o ricevere chiamate verso e da altri peer di Mediation Server che non instradano le chiamate alla rete PSTN (ovvero un endpoint connesso a un altro sistema PBX) indipendentemente dal sito di rete a cui è associato il peer di Mediation Server. Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti di chiamata e gli inoltri di chiamata che coinvolgono endpoint PSTN sono soggetti al routing basato sulla posizione per l'utilizzo di solo gateway PSTN definiti come locali per tale peer di Mediation Server.

<div>

## <a name="see-also"></a>Vedere anche


[Linee guida per il routing Location-Based in Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

