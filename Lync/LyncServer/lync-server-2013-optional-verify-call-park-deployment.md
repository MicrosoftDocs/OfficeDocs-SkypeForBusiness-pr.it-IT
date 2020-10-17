---
title: 'Lync Server 2013: (facoltativo) verificare la distribuzione del parcheggio di chiamata'
description: 'Lync Server 2013: (facoltativo) verificare la distribuzione del parcheggio di chiamata.'
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
ms.openlocfilehash: 772392a3a791ed57c3220d80e9bd510d8803debb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541932"
---
# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="2a850-103">Optional Verificare la distribuzione del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a850-103">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a850-104">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="2a850-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="2a850-105">Dopo l'installazione e la configurazione del parcheggio di chiamata, è necessario verificare la configurazione per garantire che le chiamate di parcheggi e recupero funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="2a850-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="2a850-106">Effettuare almeno le verifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a850-106">At minimum, verify the following:</span></span>

  - <span data-ttu-id="2a850-107">Chiamare un utente con parcheggio di chiamata abilitato e far parcheggiare la chiamata da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2a850-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2a850-108">Se è stato abilitato il parcheggio di chiamata nel criterio vocale appena prima di eseguire questo test, l'utente che sta parcheggiando la chiamata deve disconnettersi da Lync Server e quindi accedere nuovamente per poter visualizzare l'opzione parcheggio di chiamata nell'elenco trasferimento chiamate.</span><span class="sxs-lookup"><span data-stu-id="2a850-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="2a850-109">Comporre il numero di orbit per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a850-109">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="2a850-p102">Parcheggiare un'altra chiamata, attendere il timeout della chiamata parcheggiata e non rispondere alla richiamata. Verificare che dopo il timeout la chiamata venga correttamente instradata alla destinazione di fallback specificata per **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="2a850-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

