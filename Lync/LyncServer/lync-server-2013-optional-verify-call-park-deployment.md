---
title: 'Lync Server 2013: (facoltativo) verificare la distribuzione di Call Park'
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
ms.openlocfilehash: 5cfc0d62bcfabe1a5bcddfb069d95b18aa0d30d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>Opzionale Verificare la distribuzione di Call Park in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-11_

Dopo l'installazione e la configurazione di Call Park, è necessario verificare la configurazione per assicurarsi che il parcheggio e il recupero delle chiamate funzionino come previsto. Verificare quanto segue:

  - Chiama un utente con il parcheggio delle chiamate abilitato e fai parcheggiare la chiamata dall'utente.
    
    <div>
    

    > [!NOTE]  
    > Se è stato abilitato Call Park nel criterio vocale subito prima di eseguire questo test, l'utente che sta parcheggiando la chiamata deve disconnettersi da Lync Server e quindi eseguire di nuovo l'accesso per poter vedere l'opzione Call Park nell'elenco trasferimento chiamate.

    
    </div>

  - Componi il numero dell'orbita per recuperare la chiamata.

  - Parcheggiare un'altra chiamata, consentire il timeout della chiamata parcheggiata e non ritirare la risponderia. Verificare che la chiamata scaduta venga indirizzata correttamente alla destinazione di fallback specificata per **OnTimeoutURI**.

</div>

<span> </span>

</div>

</div>

</div>

