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

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="76107-102">Optional Verificare la distribuzione del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76107-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76107-103">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="76107-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="76107-104">Dopo l'installazione e la configurazione del parcheggio di chiamata, è necessario verificare la configurazione per garantire che le chiamate di parcheggi e recupero funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="76107-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="76107-105">Effettuare almeno le verifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="76107-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="76107-106">Chiamare un utente con parcheggio di chiamata abilitato e far parcheggiare la chiamata da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="76107-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="76107-107">Se è stato abilitato il parcheggio di chiamata nel criterio vocale appena prima di eseguire questo test, l'utente che sta parcheggiando la chiamata deve disconnettersi da Lync Server e quindi accedere nuovamente per poter visualizzare l'opzione parcheggio di chiamata nell'elenco trasferimento chiamate.</span><span class="sxs-lookup"><span data-stu-id="76107-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="76107-108">Comporre il numero di orbit per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="76107-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="76107-p102">Parcheggiare un'altra chiamata, attendere il timeout della chiamata parcheggiata e non rispondere alla richiamata. Verificare che dopo il timeout la chiamata venga correttamente instradata alla destinazione di fallback specificata per **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="76107-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

