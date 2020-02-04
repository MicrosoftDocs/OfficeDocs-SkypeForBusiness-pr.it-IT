---
title: "Lync Server 2013: Posizione dell'utente"
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
ms.openlocfilehash: 9754b75b941944a445da33750190b9347aeb9313
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Posizione dell'utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-09_

Il routing basato sulla posizione sfrutta le stesse aree di rete, i siti e le subnet definiti in Lync Server usato da E9-1-1, CAC e bypass multimediale per applicare le restrizioni di routing delle chiamate per evitare l'esclusione del pedaggio PSTN. La posizione di un utente è determinata dalla subnet IP degli endpoint di Lync dell'utente da cui sono connessi. Ogni subnet IP è associata a un sito di rete, che viene aggregato in aree di rete definite dall'amministratore. Il routing basato sulla posizione viene applicato in base al sito di rete dell'utente.

Le regole di routing basate sulla posizione vengono applicate in base al sito di rete, pertanto un set di regole specifico verrà applicato a tutti gli endpoint abilitati per il routing basato sulla posizione che si trovano all'interno dello stesso sito di rete. Gli amministratori possono applicare il routing basato sulla posizione ai siti di rete che lo richiedono.

I criteri di routing vocale possono essere definiti in base al sito di rete per definire un gateway PSTN specifico che deve essere usato da tutti gli utenti presenti nel sito di rete per chiamare i numeri di telefono PSTN. Tali criteri di routing vocale avranno la precedenza sul routing definito dal criterio vocale dell'utente quando l'utente si trova in un sito di rete abilitato per il routing basato sulla posizione e impedirà il routing delle chiamate tramite altri gateway PSTN abilitati per Routing basato sulla posizione. Quando un utente di Lync inserisce una chiamata PSTN, il criterio vocale dell'utente determina se l'utente può essere autorizzato a effettuare la chiamata. Se il criterio vocale dell'utente consente all'utente di inserire la chiamata, il routing basato sulla posizione determina il gateway PSTN da cui deve essere uscita la chiamata. Il routing basato sulla posizione rende questa determinazione in base alla posizione dell'utente.

Una posizione utente può essere categorizzata nei modi seguenti:

  - L'utente si trova in un sito di rete noto abilitato per il routing basato sulla posizione e il suo numero DID (Direct Inward Dial) termina con un gateway PSTN inserito nello stesso sito di rete (ad esempio Office). Il routing delle chiamate in uscita avverrà tramite il criterio di routing vocale del sito di rete in cui si trova l'utente. Le chiamate PSTN in arrivo all'utente vengono instradate agli endpoint che si trovano nello stesso sito di rete del gateway PSTN.

  - L'utente si trova in un sito di rete noto che è diverso dal sito di rete in cui si trova il gateway PSTN. (ossia l'utente ha viaggiato in un altro ufficio aziendale). Il routing delle chiamate in uscita userà i criteri di routing vocale del sito di rete in cui si trova l'utente. Le chiamate PSTN in arrivo per l'utente non verranno instradate agli endpoint che si trovano in siti diversi rispetto al gateway PSTN per evitare l'esclusione dei pedaggi PSTN.

  - Quando un utente si trova in un sito di rete sconosciuto alla distribuzione di Lync Server, il routing delle chiamate in uscita sarà basato sul criterio vocale assegnato all'utente per i gateway PSTN non associati alle restrizioni di routing basate sulla posizione. Le chiamate PSTN in arrivo non verranno instradate agli endpoint che si trovano in siti di rete sconosciuti per evitare l'esclusione dei pedaggi PSTN.

<div>

## <a name="see-also"></a>Vedere anche


[Linee guida per il routing in base alla posizione in Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

