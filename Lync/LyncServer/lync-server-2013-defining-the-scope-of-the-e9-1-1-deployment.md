---
title: "Lync Server 2013: definizione dell'ambito della distribuzione di E9-1-1"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96f5ac1fb747a3e64be6cc84c44b390de8ce821c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="082d0-102">Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="082d0-102">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="082d0-103">_**Argomento Ultima modifica:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="082d0-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="082d0-104">Prima di configurare Microsoft Lync Server 2013 per E9-1-1, è necessario pianificare la distribuzione di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="082d0-104">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="082d0-105">Alcune delle domande da prendere in considerazione includono:</span><span class="sxs-lookup"><span data-stu-id="082d0-105">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="082d0-106">**Quali sono i criteri e gli obblighi legali dell'organizzazione per quanto riguarda il E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="082d0-106">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="082d0-107">I requisiti legali di E9-1-1 per i PBX (detti sistemi telefonici multilinea o MLTS, in E9-1-1) sono diversi da stato a stato.</span><span class="sxs-lookup"><span data-stu-id="082d0-107">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="082d0-108">È consigliabile rivolgersi al proprio team legale per comprendere gli obblighi che possono essere applicati alla distribuzione di Lync Server nelle relative aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="082d0-108">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="082d0-109">**Quali aree all'interno dell'organizzazione devono essere abilitate per il E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="082d0-109">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="082d0-110">È possibile abilitare E9-1-1 per l'intera organizzazione o per le posizioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="082d0-110">You can enable E9-1-1 for the entire enterprise or for selected locations.</span></span> <span data-ttu-id="082d0-111">Ad esempio, potresti avere requisiti di E9-1-1 diversi per gli uffici in diversi Stati oppure vuoi escludere i siti al di fuori degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="082d0-111">For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="082d0-112">**Come si distribuisce E9-1-1 a siti di succursale?**</span><span class="sxs-lookup"><span data-stu-id="082d0-112">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="082d0-113">La resilienza vocale è un concetto importante da comprendere quando si distribuisce E9-1-1 in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="082d0-113">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="082d0-114">Se sono presenti trunk SIP e-9-1-1 centralizzati e si verifica un'interruzione WAN, i client che accedono potrebbero non essere in grado di ottenere un percorso dal servizio informazioni sulla posizione o connettersi al provider di servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="082d0-114">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="082d0-115">Lync Server offre diverse strategie per gestire la resilienza vocale nelle filiali, tra cui: avere reti di dati resilienti, distribuire un trunk SIP in ogni ramo o spingere le chiamate di emergenza al gateway locale durante le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="082d0-115">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="082d0-116">Per informazioni dettagliate, vedere [pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="082d0-116">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="082d0-117">**Si Abilita E9-1-1 per gli utenti che lavorano all'esterno della rete?**</span><span class="sxs-lookup"><span data-stu-id="082d0-117">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="082d0-118">L'acquisizione automatica della posizione è disponibile solo per i client che si trovano all'interno della rete dell'organizzazione, quindi l'organizzazione deve decidere se supportare le chiamate E9-1-1 effettuate dai client Lync in locale.</span><span class="sxs-lookup"><span data-stu-id="082d0-118">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises.</span></span> <span data-ttu-id="082d0-119">Ad esempio, puoi consentire agli utenti di inserire chiamate di emergenza se lavorano da casa o da un sito del cliente?</span><span class="sxs-lookup"><span data-stu-id="082d0-119">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="082d0-120">Se un client si trova all'esterno della rete aziendale, il client può essere configurato per richiedere all'utente una posizione.</span><span class="sxs-lookup"><span data-stu-id="082d0-120">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="082d0-121">Tuttavia, dato che questi percorsi forniti dall'utente non possono essere convalidati rispetto alla guida per gli indirizzi master Street (stradario), il dispatcher del provider di servizi di emergenza dovrà confermare la validità della posizione verbalmente con il chiamante prima del routing chiamata al punto di risposta della sicurezza pubblica (PSAP).</span><span class="sxs-lookup"><span data-stu-id="082d0-121">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="082d0-122">I client Lync degli utenti che si connettono alla rete dell'organizzazione tramite VPN possono raccogliere informazioni interne sull'indirizzo IP, ma poiché questi indirizzi non possono essere usati per identificare la posizione effettiva dell'utente, è essenziale che le subnet VPN siano escluse dalla Servizio informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="082d0-122">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="082d0-123">**Si desidera specificare il routing delle chiamate di emergenza ai siti esterni agli Stati Uniti?**</span><span class="sxs-lookup"><span data-stu-id="082d0-123">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="082d0-124">Potrebbe essere necessario disporre di un routing di emergenza per le aree della società non gestite da un provider di servizi di emergenza (ad esempio, posizioni internazionali).</span><span class="sxs-lookup"><span data-stu-id="082d0-124">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations).</span></span> <span data-ttu-id="082d0-125">A questo scopo, crea un nuovo sito e quindi Assegna criteri vocali ai siti che fanno riferimento a un uso PSTN che instrada la chiamata tramite il gateway PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="082d0-125">To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

