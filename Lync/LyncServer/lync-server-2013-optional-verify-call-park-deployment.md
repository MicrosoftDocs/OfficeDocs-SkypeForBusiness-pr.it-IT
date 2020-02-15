---
title: 'Lync Server 2013: (facoltativo) verificare la distribuzione del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05b18de4af492fb45ef37e64cca45cc2d3d2b965
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>Optional Verificare la distribuzione del parcheggio di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-11_

Dopo l'installazione e la configurazione del parcheggio di chiamata, è necessario verificare la configurazione per garantire che le chiamate di parcheggi e recupero funzionino come previsto. Effettuare almeno le verifiche seguenti:

  - Chiamare un utente con parcheggio di chiamata abilitato e far parcheggiare la chiamata da parte dell'utente.
    
    <div>
    

    > [!NOTE]  
    > Se è stato abilitato il parcheggio di chiamata nel criterio vocale appena prima di eseguire questo test, l'utente che sta parcheggiando la chiamata deve disconnettersi da Lync Server e quindi accedere nuovamente per poter visualizzare l'opzione parcheggio di chiamata nell'elenco trasferimento chiamate.

    
    </div>

  - Comporre il numero di orbit per recuperare la chiamata.

  - Parcheggiare un'altra chiamata, attendere il timeout della chiamata parcheggiata e non rispondere alla richiamata. Verificare che dopo il timeout la chiamata venga correttamente instradata alla destinazione di fallback specificata per **OnTimeoutURI**.

</div>

<span> </span>

</div>

</div>

</div>

