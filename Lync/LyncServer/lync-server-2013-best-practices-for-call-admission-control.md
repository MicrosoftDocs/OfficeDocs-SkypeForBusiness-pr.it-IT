---
title: 'Lync Server 2013: procedure consigliate per il controllo di ammissione di chiamata'
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
ms.openlocfilehash: c00dbaa2f47d34f06424c9013a5b691caab56499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Procedure consigliate per il controllo di ammissione di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-22_

Per migliorare le prestazioni e facilitare la distribuzione, applicare le procedure consigliate seguenti quando si distribuisce il servizio Controllo di ammissione di chiamata:

  - Verificare che il provisioning delle WAN sia adeguato al traffico multimediale corrente e previsto.
    
    <div>
    

    > [!NOTE]  
    > È consigliabile considerare un buffer rispetto ai limiti di larghezza di banda. Esistono scenari, ad esempio le race condition, che incidono sulla larghezza di banda totale utilizzata e possono produrre situazioni in cui i limiti di larghezza di banda vengono superati. Se ad esempio si tenta di avviare due chiamate mentre il traffico multimediale si avvicina al limite di larghezza di banda, è possibile che una delle due venga rifiutata perché l'altra è configurata per partire per prima.

    
    </div>

  - Monitorare l'utilizzo della rete e i record dettagli chiamata, in modo da poter scegliere impostazioni ottimali per il servizio Controllo di ammissione di chiamata e aggiornarle al variare dell'utilizzo della rete.

  - Utilizzare i criteri larghezza di banda relativi al servizio Controllo di ammissione di chiamata a complemento delle impostazioni QoS.

  - Se si desidera reindirizzare le chiamate bloccate al PSTN, verificare le funzionalità e le capacità PSTN. Per informazioni dettagliate, vedere [pianificazione del routing vocale in uscita in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).
    
    <div>
    

    > [!NOTE]  
    > La capacità fa riferimento al numero di porte che è necessario aprire per supportare il potenziale reindirizzamento PSTN.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

