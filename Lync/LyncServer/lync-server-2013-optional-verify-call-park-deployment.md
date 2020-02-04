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

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="dc5be-102">Opzionale Verificare la distribuzione di Call Park in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc5be-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc5be-103">_**Argomento Ultima modifica:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="dc5be-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="dc5be-104">Dopo l'installazione e la configurazione di Call Park, è necessario verificare la configurazione per assicurarsi che il parcheggio e il recupero delle chiamate funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="dc5be-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="dc5be-105">Verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="dc5be-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="dc5be-106">Chiama un utente con il parcheggio delle chiamate abilitato e fai parcheggiare la chiamata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="dc5be-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dc5be-107">Se è stato abilitato Call Park nel criterio vocale subito prima di eseguire questo test, l'utente che sta parcheggiando la chiamata deve disconnettersi da Lync Server e quindi eseguire di nuovo l'accesso per poter vedere l'opzione Call Park nell'elenco trasferimento chiamate.</span><span class="sxs-lookup"><span data-stu-id="dc5be-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="dc5be-108">Componi il numero dell'orbita per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="dc5be-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="dc5be-109">Parcheggiare un'altra chiamata, consentire il timeout della chiamata parcheggiata e non ritirare la risponderia.</span><span class="sxs-lookup"><span data-stu-id="dc5be-109">Park another call, let the parked call time out, and do not pick up the ringback.</span></span> <span data-ttu-id="dc5be-110">Verificare che la chiamata scaduta venga indirizzata correttamente alla destinazione di fallback specificata per **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="dc5be-110">Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

