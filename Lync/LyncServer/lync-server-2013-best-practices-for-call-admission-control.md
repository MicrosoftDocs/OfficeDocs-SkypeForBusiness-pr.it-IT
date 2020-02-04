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

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="3a805-102">Procedure consigliate per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a805-102">Best practices for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a805-103">_**Argomento Ultima modifica:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="3a805-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="3a805-104">Per migliorare le prestazioni e facilitare la distribuzione, applicare le procedure consigliate seguenti quando si distribuisce il controllo di ammissione di chiamata:</span><span class="sxs-lookup"><span data-stu-id="3a805-104">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="3a805-105">Assicurarsi che le WAN vengano adeguatamente provisionate per il traffico multimediale corrente e previsto.</span><span class="sxs-lookup"><span data-stu-id="3a805-105">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a805-106">Ti consigliamo di fattorizzare i limiti della larghezza di banda in un buffer.</span><span class="sxs-lookup"><span data-stu-id="3a805-106">We recommend that you factor in a buffer to your bandwidth limits.</span></span> <span data-ttu-id="3a805-107">Esistono scenari come le condizioni di competizione che influiscono sulla larghezza di banda totale usata e possono causare situazioni in cui viene superato il limite di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="3a805-107">There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded.</span></span> <span data-ttu-id="3a805-108">Ad esempio, se due chiamate provano a iniziare mentre il traffico multimediale si avvicina a un limite di larghezza di banda, uno di essi potrebbe essere negato perché l'altro è riuscito a iniziare per primo.</span><span class="sxs-lookup"><span data-stu-id="3a805-108">For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="3a805-109">Monitorare l'uso della rete e i record dei dettagli delle chiamate per scegliere le impostazioni di CAC ottimali e aggiornare le impostazioni di CAC come modifiche all'utilizzo della rete.</span><span class="sxs-lookup"><span data-stu-id="3a805-109">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="3a805-110">Usare i criteri di larghezza di banda CAC per completare le impostazioni QoS.</span><span class="sxs-lookup"><span data-stu-id="3a805-110">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="3a805-111">Se si vuole reinstradare le chiamate bloccate sulla rete PSTN, verificare la funzionalità e la capacità PSTN.</span><span class="sxs-lookup"><span data-stu-id="3a805-111">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="3a805-112">Per informazioni dettagliate, vedere [pianificazione del routing vocale in uscita in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="3a805-112">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a805-113">La capacità si riferisce al numero di porte che è necessario aprire per supportare l'eventuale reindirizzamento PSTN.</span><span class="sxs-lookup"><span data-stu-id="3a805-113">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

