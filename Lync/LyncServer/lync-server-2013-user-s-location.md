---
title: "Lync Server 2013: posizione dell'utente"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbb581f049e8d45d16ace385fc26908d3d8301b9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Posizione dell'utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-09_

Il routing basato sulla posizione utilizza le stesse aree di rete, i siti e le subnet definiti in Lync Server utilizzato da E9-1-1, CAC e bypass multimediale per applicare le restrizioni di routing delle chiamate per impedire il bypass a pedaggio PSTN. La posizione di un utente è determinata dalla subnet IP degli endpoint di Lync dell'utente da cui sono connessi. Ogni subnet IP è associata a un sito di rete, che viene aggregato nelle aree di rete definite dall'amministratore. Il routing in base alla posizione viene applicato in base al sito di rete dell'utente.

Le regole di routing basate sul percorso vengono applicate per ogni sito di rete, ovvero un determinato insieme di regole verrà applicato a tutti gli endpoint abilitati per il routing in base alla posizione che si trovano all'interno dello stesso sito di rete. Gli amministratori possono applicare il routing in base alla posizione ai siti di rete che lo richiedono.

I criteri di routing vocale possono essere definiti in base al sito di rete per definire un gateway PSTN specifico che deve essere utilizzato da tutti gli utenti che si trovano nel sito di rete per chiamare i numeri di telefono PSTN. Tali criteri di routing vocale avranno la precedenza sul routing definito dal criterio vocale dell'utente quando l'utente si trova in un sito di rete abilitato per il routing in base alla posizione e impedirà il routing delle chiamate tramite altri gateway PSTN abilitati per Routing in base alla posizione. Quando un utente di Lync inserisce una chiamata PSTN, il criterio vocale dell'utente determina se l'utente può essere autorizzato a effettuare la chiamata. Se i criteri vocali dell'utente consentono all'utente di effettuare la chiamata, il routing in base alla posizione determina il gateway PSTN da cui deve essere eseguita la chiamata. Il routing in base alla posizione rende questa determinazione in base alla posizione dell'utente.

Una posizione utente può essere categorizzata nei modi seguenti:

  - L'utente si trova in un sito di rete noto abilitato per il routing in base alla posizione e il numero DID (Direct Inward Dial) termina su un gateway PSTN posizionato nello stesso sito di rete (ad esempio, Office). Il routing delle chiamate in uscita sarà tramite il criterio di routing vocale del sito di rete in cui si trova l'utente. Le chiamate PSTN in arrivo all'utente vengono instradate agli endpoint che si trovano nello stesso sito di rete del gateway PSTN.

  - L'utente si trova in un sito di rete noto che è diverso dal sito di rete in cui si trova il gateway PSTN. (ovvero l'utente ha viaggiato in un altro ufficio aziendale). Il routing delle chiamate in uscita utilizzerà i criteri di routing vocale del sito di rete in cui si trova l'utente. Le chiamate PSTN in arrivo all'utente non verranno instradate agli endpoint che si trovano in siti diversi rispetto al gateway PSTN per impedire l'esclusione dei pedaggi PSTN.

  - Quando un utente si trova in un sito di rete sconosciuto alla distribuzione di Lync Server, il routing delle chiamate in uscita si baserà sui criteri vocali assegnati all'utente ai gateway PSTN che non sono associati alle restrizioni di routing basate sul percorso. Le chiamate PSTN in arrivo non verranno instradate agli endpoint che si trovano in siti di rete sconosciuti per impedire l'esclusione dei pedaggi PSTN.

<div>

## <a name="see-also"></a>Vedere anche


[Linee guida per il routing in base alla posizione in Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

