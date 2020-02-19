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
ms.openlocfilehash: c84c6519ab561fef034fbe0990854087f22b2e41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="dd6d4-102">Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd6d4-102">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd6d4-103">_**Ultimo argomento modificato:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="dd6d4-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="dd6d4-104">Prima di configurare Microsoft Lync Server 2013 per il servizio E9-1-1, è necessario pianificare la distribuzione di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="dd6d4-104">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="dd6d4-105">Di seguito sono riportati alcuni aspetti di cui tenere conto:</span><span class="sxs-lookup"><span data-stu-id="dd6d4-105">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="dd6d4-106">**Politica aziendale e vincoli di tipo legale dell'organizzazione per il servizio E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="dd6d4-106">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="dd6d4-107">Le disposizioni legali del servizio E9-1-1 per i PBX (denominati sistemi telefonici multilinea, o MLTS, nella terminologia relativa a E9-1-1) variano a seconda delle località.</span><span class="sxs-lookup"><span data-stu-id="dd6d4-107">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="dd6d4-108">È consigliabile rivolgersi al proprio team legale per capire gli obblighi che possono essere applicati alla distribuzione di Lync Server nelle rispettive aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="dd6d4-108">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="dd6d4-109">**Aree dell'organizzazione che devono essere abilitate per il servizio E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="dd6d4-109">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="dd6d4-p103">È possibile abilitare il servizio E9-1-1 per l'intera organizzazione o solo per località selezionate. È ad esempio possibile applicare requisiti E9-1-1 diversi per gli uffici di stati diversi oppure escludere le sedi al di fuori degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="dd6d4-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="dd6d4-112">**Modalità di distribuzione del servizio E9-1-1 nei siti di succursale**</span><span class="sxs-lookup"><span data-stu-id="dd6d4-112">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="dd6d4-113">La resilienza vocale è un concetto importante di cui tenere conto quando si distribuisce il servizio E9-1-1 in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="dd6d4-113">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="dd6d4-114">Se si dispone di trunk SIP e-9-1-1 centralizzato e si verifica un'interruzione della rete WAN, i client che effettuano l'accesso potrebbero non essere in grado di ottenere un percorso dal servizio informazioni percorso o connettersi al provider di servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="dd6d4-114">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="dd6d4-115">In Lync Server sono disponibili diverse strategie per la gestione della resilienza vocale nelle succursali, tra cui: una rete di dati resilienti, la distribuzione di un trunk SIP in ogni branch o la pressione delle chiamate di emergenza verso il gateway locale durante le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="dd6d4-115">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="dd6d4-116">Per informazioni dettagliate, vedere [pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="dd6d4-116">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="dd6d4-117">**Possibilità di abilitare il servizio E9-1-1 per gli utenti che lavorano all'esterno della rete**</span><span class="sxs-lookup"><span data-stu-id="dd6d4-117">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="dd6d4-p105">L'acquisizione automatica della posizione è disponibile solo per i client all'interno della rete aziendale. L'organizzazione deve pertanto decidere se supportare le chiamate E9-1-1 effettuate da client Lync non locali, ad esempio se consentire agli utenti di effettuare chiamate di emergenza quando lavorano dalla propria abitazione o dalla sede di un cliente. Se è posizionato all'esterno di una rete aziendale, un client può essere configurato per richiedere la posizione a un utente. Poiché tuttavia queste posizioni fornite dagli utenti non possono essere precedentemente convalidate a fronte dello stradario generale, il dispatcher del provider di servizi di emergenza dovrà verificare la validità della posizione verbalmente con il chiamante prima di instradare la chiamata al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point).</span><span class="sxs-lookup"><span data-stu-id="dd6d4-p105">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises. For example, will you enable users to place emergency calls if they are working from home or from a customer site? If a client is located outside the enterprise network, the client can be configured to prompt the user for a location. However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd6d4-122">I client Lync degli utenti che si connettono alla rete dell'organizzazione tramite VPN possono raccogliere informazioni sull'indirizzo IP interno, ma poiché questi indirizzi non possono essere utilizzati per identificare la posizione effettiva dell'utente, è essenziale che le subnet VPN siano escluse dal Servizio informazioni percorso.</span><span class="sxs-lookup"><span data-stu-id="dd6d4-122">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="dd6d4-123">**Possibilità di fornire il routing delle chiamate di emergenza per siti al di fuori degli Stati Uniti**</span><span class="sxs-lookup"><span data-stu-id="dd6d4-123">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="dd6d4-p106">È possibile offrire il routing delle chiamate di emergenza per aree dell'azienda non servite dal provider di servizi di emergenza, ad esempio sedi internazionali. A tale scopo, creare un nuovo sito e quindi assegnare i criteri vocali ai siti che fanno riferimento a un utilizzo PSTN che instrada le chiamate tramite il gateway PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="dd6d4-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

