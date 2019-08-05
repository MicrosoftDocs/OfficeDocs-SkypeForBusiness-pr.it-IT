---
title: Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisioni necessarie per la pianificazione di una distribuzione E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 648713ce3474779a588d638e3e81272fbd62e2f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187565"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="91823-103">Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="91823-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="91823-104">Decisioni necessarie per la pianificazione di una distribuzione E9-1-1 in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="91823-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="91823-105">Prima di configurare Skype for business per E9-1-1, è necessario pianificare la distribuzione di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="91823-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="91823-106">Alcune delle domande da prendere in considerazione includono:</span><span class="sxs-lookup"><span data-stu-id="91823-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="91823-107">**Quali sono i criteri e gli obblighi legali dell'organizzazione per quanto riguarda il E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="91823-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="91823-108">I requisiti legali di E9-1-1 per i PBX (detti sistemi telefonici multilinea o MLTS, in E9-1-1) sono diversi da stato a stato.</span><span class="sxs-lookup"><span data-stu-id="91823-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="91823-109">Dovresti consultarti con il tuo team legale per comprendere gli obblighi che possono essere applicati alla tua distribuzione di Skype for business nelle tue geografie pertinenti.</span><span class="sxs-lookup"><span data-stu-id="91823-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="91823-110">**Quali aree all'interno dell'organizzazione devono essere abilitate per il E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="91823-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="91823-111">È possibile abilitare E9-1-1 per l'intera organizzazione o per le posizioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="91823-111">You can enable E9-1-1 for the entire enterprise or for selected locations.</span></span> <span data-ttu-id="91823-112">Ad esempio, potresti avere requisiti di E9-1-1 diversi per gli uffici in diversi Stati oppure vuoi escludere i siti al di fuori degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="91823-112">For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="91823-113">**Come si distribuisce E9-1-1 a siti di succursale?**</span><span class="sxs-lookup"><span data-stu-id="91823-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="91823-114">La resilienza vocale è un concetto importante da comprendere quando si distribuisce E9-1-1 in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="91823-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="91823-115">Se sono presenti trunk SIP e-9-1-1 centralizzati e si verifica un'interruzione WAN, i client che accedono potrebbero non essere in grado di ottenere un percorso dal servizio informazioni sulla posizione o connettersi al provider di servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="91823-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="91823-116">Skype for business offre diverse strategie per gestire la resilienza vocale nelle filiali, tra cui: avere reti di dati resilienti, distribuire un trunk SIP in ogni filiale o spingere le chiamate di emergenza al gateway locale durante le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="91823-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="91823-117">Per informazioni dettagliate, vedere [pianificazione della resilienza vocale del sito](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)di succursale.</span><span class="sxs-lookup"><span data-stu-id="91823-117">For details, see [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>

 <span data-ttu-id="91823-118">**Si Abilita E9-1-1 per gli utenti che lavorano all'esterno della rete?**</span><span class="sxs-lookup"><span data-stu-id="91823-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="91823-119">L'acquisizione automatica della posizione è disponibile solo per i client che si trovano all'interno della rete dell'organizzazione, quindi l'organizzazione deve decidere se supportare le chiamate E9-1-1 effettuate da client Skype for business mentre è fuori sede.</span><span class="sxs-lookup"><span data-stu-id="91823-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="91823-120">Ad esempio, puoi consentire agli utenti di inserire chiamate di emergenza se lavorano da casa o da un sito del cliente?</span><span class="sxs-lookup"><span data-stu-id="91823-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="91823-121">Se un client si trova all'esterno della rete aziendale, il client può essere configurato per richiedere all'utente una posizione.</span><span class="sxs-lookup"><span data-stu-id="91823-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="91823-122">Tuttavia, dato che questi percorsi forniti dall'utente non possono essere convalidati rispetto alla guida per gli indirizzi master Street (stradario), il dispatcher del provider di servizi di emergenza dovrà confermare la validità della posizione verbalmente con il chiamante prima del routing chiamata al punto di risposta della sicurezza pubblica (PSAP).</span><span class="sxs-lookup"><span data-stu-id="91823-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="91823-123">I client Skype for business degli utenti che si connettono alla rete dell'organizzazione tramite VPN possono raccogliere informazioni interne sull'indirizzo IP, ma poiché questi indirizzi non possono essere usati per identificare la posizione effettiva dell'utente, è essenziale escludere le subnet VPN dal servizio informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="91823-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="91823-124">**Si desidera specificare il routing delle chiamate di emergenza ai siti esterni agli Stati Uniti?**</span><span class="sxs-lookup"><span data-stu-id="91823-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="91823-125">Potrebbe essere necessario disporre di un routing di emergenza per le aree della società non gestite da un provider di servizi di emergenza (ad esempio, posizioni internazionali).</span><span class="sxs-lookup"><span data-stu-id="91823-125">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations).</span></span> <span data-ttu-id="91823-126">A questo scopo, crea un nuovo sito e quindi Assegna criteri vocali ai siti che fanno riferimento a un uso PSTN che instrada la chiamata tramite il gateway PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="91823-126">To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>


