---
title: 'Lync Server 2013: elenco di controllo per la distribuzione delle chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e768cdd11d92b3aab5ce849f91cc1a422f119407
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Elenco di controllo della distribuzione dei controlli di ammissione delle chiamate per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Usare l'elenco di controllo seguente per verificare di aver completato tutte le attività di configurazione necessarie per distribuire il controllo di ammissione di chiamata (CAC).

  - Se vengono distribuiti uno o più Edge Server, ogni indirizzo IP dell'interfaccia esterna deve essere aggiunto all'elenco subnet nelle impostazioni di configurazione della rete, con una maschera di bit di 32. Devi anche associare questa subnet (indirizzo IP) con l'ID sito di rete per la posizione geografica in cui è distribuito il servizio A/V Edge.
    
    <div>
    

    > [!NOTE]  
    > I server perimetrali non sono obbligatori per implementare CAC.

    
    </div>

  - Verificare che CAC sia abilitato, tramite il pannello di controllo di Lync Server o eseguendo il cmdlet come specificato in [Abilita controllo ammissione chiamata in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).

  - Verificare che CAC sia abilitato in tutti i siti centrali. Questa operazione può essere eseguita tramite il generatore di topologie. Se viene generato un avviso durante la pubblicazione, *non* ignorarlo.

  - Verificare che tutte le subnet gestite nella rete aziendale siano configurate nelle impostazioni di configurazione della rete. È anche essenziale che ogni subnet sia associata a un sito di rete, come spiegato in [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

  - Verificare che la subnet o gli indirizzi IP di tutti i server front-end, Survivable Branch Appliances (SBAs), audio/video Conferencing Servers (se in un pool separato) e Mediation Server siano configurati nelle impostazioni di configurazione della rete.

</div>

<span> </span>

</div>

</div>

</div>

