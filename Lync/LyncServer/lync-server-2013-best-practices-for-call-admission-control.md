---
title: 'Lync Server 2013: Procedure consigliate per il controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8f75c546b2307de8f55504c2c6ebaab5c48f7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Procedure consigliate per il controllo di ammissione di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-22_

Per migliorare le prestazioni e facilitare la distribuzione, applicare le procedure consigliate seguenti quando si distribuisce il controllo di ammissione di chiamata:

  - Assicurarsi che le WAN vengano adeguatamente provisionate per il traffico multimediale corrente e previsto.
    
    <div>
    

    > [!NOTE]  
    > Ti consigliamo di fattorizzare i limiti della larghezza di banda in un buffer. Esistono scenari come le condizioni di competizione che influiscono sulla larghezza di banda totale usata e possono causare situazioni in cui viene superato il limite di larghezza di banda. Ad esempio, se due chiamate provano a iniziare mentre il traffico multimediale si avvicina a un limite di larghezza di banda, uno di essi potrebbe essere negato perché l'altro è riuscito a iniziare per primo.

    
    </div>

  - Monitorare l'uso della rete e i record dei dettagli delle chiamate per scegliere le impostazioni di CAC ottimali e aggiornare le impostazioni di CAC come modifiche all'utilizzo della rete.

  - Usare i criteri di larghezza di banda CAC per completare le impostazioni QoS.

  - Se si vuole reinstradare le chiamate bloccate sulla rete PSTN, verificare la funzionalità e la capacità PSTN. Per informazioni dettagliate, vedere [pianificazione del routing vocale in uscita in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).
    
    <div>
    

    > [!NOTE]  
    > La capacità si riferisce al numero di porte che è necessario aprire per supportare l'eventuale reindirizzamento PSTN.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

