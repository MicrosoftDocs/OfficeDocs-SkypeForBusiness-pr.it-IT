---
title: 'Lync Server 2013: Posizione del gateway PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b897d9ce438844cde7617bb7c3e1dae086605f09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Posizione del gateway PSTN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-09_

Le chiamate instradate tramite gateway e PBX PSTN potrebbero richiedere restrizioni di routing basate sulla posizione a seconda della posizione di tali sistemi. Il routing basato sulla posizione può essere abilitato alla granularità per ogni trunk base.

Il routing basato sulla posizione introduce il set di regole seguente quando è abilitato su un trunk:

  - Quando il routing basato sulla posizione è abilitato per ogni trunk, le regole definite in tale trunk verranno applicate solo alle chiamate instradate tramite il trunk.

  - Per impedire l'esclusione dei pedaggi PSTN in cui le chiamate provengono da un sito di rete diverso da quello del sito di rete in cui si trova il gateway PSTN, il routing basato sulla posizione introduce l'associazione di un sito di rete a un trunk specifico. Questo definisce il sito di rete che consente alle chiamate di essere indirizzate a un trunk specifico.

Trunks può essere abilitato per il routing basato sulla posizione in due modi:

  - Il trunk viene definito per un gateway PSTN che egresses chiama alla rete PSTN. Le chiamate in arrivo instradate da un trunk di questo tipo verranno instradate solo agli endpoint situati nello stesso sito di rete del trunk.

  - Il trunk viene definito per un peer di Mediation Server che non consente l'uscita delle chiamate agli utenti di servizi e PSTN con telefoni legacy in posizioni statiche (ad esempio telefoni PBX). Per questa particolare configurazione, tutte le chiamate in arrivo instradate da un trunk di questo tipo verranno considerate come originarie dello stesso sito di rete del trunk. Le chiamate degli utenti PBX avranno la stessa applicazione di routing basata sulla posizione degli utenti di Lync che si trovano nello stesso sito di rete del trunk. Se due sistemi PBX situati in siti di rete separati sono connessi tramite Lync Server, il routing basato sulla posizione consentirà il routing da un endpoint PBX in un sito di rete a un altro endpoint PBX nell'altro sito di rete. Questo scenario non verrà bloccato dal routing basato sulla posizione. Oltre a questo scenario e in modo simile a quello di un utente di Lync nella stessa posizione, gli endpoint connessi a un peer di Mediation Server con questa configurazione saranno in grado di effettuare o ricevere chiamate da e verso altri peer di Mediation Server che non instradano le chiamate alla rete PSTN (i. e. endpoint connesso a un PBX diverso indipendentemente dal sito di rete a cui è associato il peer di Mediation Server. Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti di chiamata e i forward di chiamata che coinvolgono endpoint PSTN saranno soggetti al routing basato sulla posizione per usare solo gateway PSTN definiti come locali a tale peer di Mediation Server.

<div>

## <a name="see-also"></a>Vedere anche


[Linee guida per il routing in base alla posizione in Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

