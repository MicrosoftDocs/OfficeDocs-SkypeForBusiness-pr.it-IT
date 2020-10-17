---
title: 'Lync Server 2013: elenco di controllo per la distribuzione di controlli di ammissione di chiamata'
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
ms.openlocfilehash: e16c4c77876064ca0ab9210b96d7c13d68cc4218
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537243"
---
# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Elenco di controllo per la distribuzione dei controlli di ammissione di chiamata per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Utilizzare l'elenco di controllo seguente per verificare che siano state completate tutte le attività di configurazione necessarie per la distribuzione dei controlli di ammissione di chiamata (CAC).

  - Se uno o più server perimetrali sono distribuiti, ogni indirizzo IP dell'interfaccia esterna deve essere aggiunto all'elenco di subnet nelle impostazioni di configurazione di rete, con una maschera di bit pari a 32. È inoltre consigliabile associare questa subnet (indirizzo IP) all'ID sito di rete per la posizione geografica in cui è distribuito il servizio A/V Edge.
    
    <div>
    

    > [!NOTE]  
    > I server perimetrali non sono necessari per implementare il servizio di controllo di ammissione.

    
    </div>

  - Verificare che il servizio di controllo di ammissione di chiamata sia abilitato, tramite il pannello di gestione di Lync Server o eseguendo il cmdlet come specificato in [Enable Call Admission Control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).

  - Verificare che il servizio di controllo di ammissione sia abilitato in tutti i siti centrali. È possibile eseguire questa operazione tramite il generatore di topologie. Se viene generato un avviso quando si *pubblica, non* ignorarlo.

  - Verificare che tutte le subnet gestite nella rete aziendale siano configurate nelle impostazioni di configurazione di rete. È inoltre essenziale che ogni subnet sia associata a un sito di rete, come illustrato in [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

  - Verificare che la subnet o gli indirizzi IP di tutti i Front End Server, Survivable Branch Appliance (SBA), audio/video Conferencing Server (se in un pool separato) e Mediation Server siano configurati nelle impostazioni di configurazione di rete.

</div>

<span> </span>

</div>

</div>

</div>

