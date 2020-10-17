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
ms.openlocfilehash: be270859304236b0704bc8cc9e1bc29f3e80fcb9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514823"
---
# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="91eee-102">Procedure consigliate per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91eee-102">Best practices for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91eee-103">_**Ultimo argomento modificato:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="91eee-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="91eee-104">Per migliorare le prestazioni e facilitare la distribuzione, applicare le procedure consigliate seguenti quando si distribuisce il servizio Controllo di ammissione di chiamata:</span><span class="sxs-lookup"><span data-stu-id="91eee-104">To enhance performance and facilitate deployment, apply the following best practices when you deploy call admission control:</span></span>

  - <span data-ttu-id="91eee-105">Verificare che il provisioning delle WAN sia adeguato al traffico multimediale corrente e previsto.</span><span class="sxs-lookup"><span data-stu-id="91eee-105">Ensure that WANs are adequately provisioned for current and anticipated media traffic.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="91eee-p101">È consigliabile considerare un buffer rispetto ai limiti di larghezza di banda. Esistono scenari, ad esempio le race condition, che incidono sulla larghezza di banda totale utilizzata e possono produrre situazioni in cui i limiti di larghezza di banda vengono superati. Se ad esempio si tenta di avviare due chiamate mentre il traffico multimediale si avvicina al limite di larghezza di banda, è possibile che una delle due venga rifiutata perché l'altra è configurata per partire per prima.</span><span class="sxs-lookup"><span data-stu-id="91eee-p101">We recommend that you factor in a buffer to your bandwidth limits. There are scenarios such as race conditions that affect the total bandwidth used and can result in situations where the bandwidth limit is exceeded. For example, if two calls try to start while media traffic is approaching a bandwidth limit, one of them may be denied because the other managed to start first.</span></span>

    
    </div>

  - <span data-ttu-id="91eee-109">Monitorare l'utilizzo della rete e i record dettagli chiamata, in modo da poter scegliere impostazioni ottimali per il servizio Controllo di ammissione di chiamata e aggiornarle al variare dell'utilizzo della rete.</span><span class="sxs-lookup"><span data-stu-id="91eee-109">Monitor network usage and call detail records so that you can choose optimal CAC settings and update CAC settings as network usage changes.</span></span>

  - <span data-ttu-id="91eee-110">Utilizzare i criteri larghezza di banda relativi al servizio Controllo di ammissione di chiamata a complemento delle impostazioni QoS.</span><span class="sxs-lookup"><span data-stu-id="91eee-110">Use CAC bandwidth policies to complement QoS settings.</span></span>

  - <span data-ttu-id="91eee-111">Se si desidera reindirizzare le chiamate bloccate al PSTN, verificare le funzionalità e le capacità PSTN.</span><span class="sxs-lookup"><span data-stu-id="91eee-111">If you want to re-route blocked calls onto the PSTN, verify PSTN functionality and capacity.</span></span> <span data-ttu-id="91eee-112">Per informazioni dettagliate, vedere [pianificazione del routing vocale in uscita in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="91eee-112">For details, see [Planning outbound voice routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="91eee-113">La capacità fa riferimento al numero di porte che è necessario aprire per supportare il potenziale reindirizzamento PSTN.</span><span class="sxs-lookup"><span data-stu-id="91eee-113">Capacity refers to the number of ports you need to open to support potential PSTN re-routing.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

