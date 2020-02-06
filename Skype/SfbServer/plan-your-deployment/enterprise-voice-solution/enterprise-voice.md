---
title: Pianificare VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Nozioni di base su Enterprise Voice Planning in Skype for Business Server, inclusi siti, aree geografiche, collegamenti di rete tra siti e stima del traffico per uso vocale.
ms.openlocfilehash: 7ef2a37a1ab39dd9c2e40544e06cfb995e846f7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802896"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="c60a5-103">Pianificare VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c60a5-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="c60a5-104">Nozioni di base su Enterprise Voice Planning in Skype for Business Server, inclusi siti, aree geografiche, collegamenti di rete tra siti e stima del traffico per uso vocale.</span><span class="sxs-lookup"><span data-stu-id="c60a5-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="c60a5-105">Il processo di distribuzione per VoIP aziendale dipende dalla topologia, dall'infrastruttura e dalla funzionalità di VoIP aziendale che si vuole supportare.</span><span class="sxs-lookup"><span data-stu-id="c60a5-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="c60a5-106">Le procedure necessarie dipendono dalle caratteristiche scelte, ma esistono altre considerazioni di pianificazione che è necessario apportare a un livello elevato.</span><span class="sxs-lookup"><span data-stu-id="c60a5-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="c60a5-107">In generale, prendere in considerazione il tipo e il numero di siti che si desidera distribuire e le rispettive posizioni geografiche, il volume delle chiamate in ogni sito, i tipi di collegamenti di rete che collegano i siti, se si vuole ottenere la ridondanza e il failover per le funzionalità vocali per ogni sito e se si vuole usare apparecchiature PBX esistenti.</span><span class="sxs-lookup"><span data-stu-id="c60a5-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="c60a5-108">Ci sono alcune considerazioni, ad esempio l'elevata disponibilità, da tenere in considerazione quando si prevede di usare Skype for Business Server nel suo complesso.</span><span class="sxs-lookup"><span data-stu-id="c60a5-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="c60a5-109">Queste considerazioni sono discusse in argomenti in questa sezione, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c60a5-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="c60a5-110">Siti e aree geografiche</span><span class="sxs-lookup"><span data-stu-id="c60a5-110">Sites and regions</span></span>

<span data-ttu-id="c60a5-111">Prima di tutto, identificare i siti della topologia in cui distribuire VoIP aziendale e le aree di rete a cui appartengono tali siti.</span><span class="sxs-lookup"><span data-stu-id="c60a5-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="c60a5-112">In particolare, valutare come si fornirà la connettività PSTN (Public Switched Telephone Network) a ogni sito.</span><span class="sxs-lookup"><span data-stu-id="c60a5-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="c60a5-113">Per motivi di gestibilità e logistica, le aree geografiche a cui appartengono questi siti possono essere un fattore decisivo.</span><span class="sxs-lookup"><span data-stu-id="c60a5-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="c60a5-114">Decidere dove verranno distribuiti i gateway localmente, dove saranno distribuiti gli appliance Survivable Branch (SBAs) e dove è possibile configurare trunk SIP (localmente o nel sito centrale) in un provider di servizi di telefonia Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="c60a5-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="c60a5-115">Collegamenti di rete tra siti</span><span class="sxs-lookup"><span data-stu-id="c60a5-115">Network links between sites</span></span>

<span data-ttu-id="c60a5-116">È inoltre necessario prendere in considerazione l'utilizzo della larghezza di banda previsto nei collegamenti di rete tra il sito centrale e i siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="c60a5-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="c60a5-117">Se si ha o si prevede di distribuire i collegamenti WAN resilienti tra i siti, è consigliabile distribuire un gateway in ogni sito di succursale per specificare la terminazione per gli utenti di tali siti.</span><span class="sxs-lookup"><span data-stu-id="c60a5-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="c60a5-118">Se si hanno collegamenti WAN resilienti, ma è probabile che la larghezza di banda di un collegamento WAN sia vincolata, configurare il controllo di ammissione delle chiamate per il collegamento.</span><span class="sxs-lookup"><span data-stu-id="c60a5-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="c60a5-119">Se non si dispone di collegamenti WAN resilienti, è necessario ospitare meno di 1000 utenti nel sito della filiale e non sono disponibili amministratori locali addestrati di Skype for Business Server, è consigliabile distribuire un Survivable Branch Appliance presso il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="c60a5-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="c60a5-120">Se si ospitano tra gli utenti di 1000 e 5000 presso il sito di succursale, non è disponibile una connessione WAN resiliente e sono stati addestrati gli amministratori di Skype for Business Server, è consigliabile distribuire un Survivable Branch Server con un piccolo gateway nel sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="c60a5-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="c60a5-121">Se si ha un peer del gateway che supporta il bypass multimediale, è consigliabile anche abilitare il bypass multimediale sui collegamenti vincolati.</span><span class="sxs-lookup"><span data-stu-id="c60a5-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="c60a5-122">Stima dell'utilizzo e del traffico vocale</span><span class="sxs-lookup"><span data-stu-id="c60a5-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="c60a5-123">Microsoft Lync Server 2013, strumento di pianificazione usa la metrica seguente per stimare il traffico degli utenti in ogni sito e il numero di porte necessarie per supportare il traffico.</span><span class="sxs-lookup"><span data-stu-id="c60a5-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="c60a5-124">Per il **traffico leggero** (una chiamata PSTN per utente per ora), figura 15 utenti per ogni porta.</span><span class="sxs-lookup"><span data-stu-id="c60a5-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="c60a5-125">Per il **traffico medio** (2 chiamate PSTN per utente per ora), figura 10 utenti per ogni porta.</span><span class="sxs-lookup"><span data-stu-id="c60a5-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="c60a5-126">Per **traffico intenso** (3 o più chiamate PSTN per utente per ora), figura 5 utenti per ogni porta.</span><span class="sxs-lookup"><span data-stu-id="c60a5-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="c60a5-127">Il numero di porte determina a sua volta il numero di server di mediazione e gateway che saranno necessari.</span><span class="sxs-lookup"><span data-stu-id="c60a5-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="c60a5-128">I gateway PSTN (Public Switched Telephone Network) che la maggior parte delle organizzazioni considerano la distribuzione di intervalli di dimensioni da 2 porte fino a un numero di porte di 960.</span><span class="sxs-lookup"><span data-stu-id="c60a5-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="c60a5-129">Ci sono anche gateway più grandi, ma questi sono usati principalmente dai provider di servizi di telefonia.</span><span class="sxs-lookup"><span data-stu-id="c60a5-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="c60a5-130">Ad esempio, un'organizzazione con gli utenti di 10.000 e il traffico medio richiederebbe porte 1000.</span><span class="sxs-lookup"><span data-stu-id="c60a5-130">For example, an organization with 10,000 users and medium traffic would require 1000 ports.</span></span> <span data-ttu-id="c60a5-131">Il numero di gateway necessari sarebbe uguale al numero totale di porte richieste come determinato dalla capacità totale dei gateway.</span><span class="sxs-lookup"><span data-stu-id="c60a5-131">The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="c60a5-132">Componenti, funzionalità e opzioni di Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="c60a5-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="c60a5-133">Per altre informazioni sulla pianificazione della distribuzione di VoIP aziendale, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c60a5-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="c60a5-134">Componenti necessari per VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c60a5-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="c60a5-135">Pianificare la connettività PSTN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c60a5-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="c60a5-136">Impostazioni di rete per le funzionalità vocali avanzate di VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c60a5-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="c60a5-137">Pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c60a5-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="c60a5-138">Pianificare i servizi di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c60a5-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="c60a5-139">Pianificare il bypass multimediale in Skype for business</span><span class="sxs-lookup"><span data-stu-id="c60a5-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="c60a5-140">Pianificare le linee telefoniche private con Skype for business</span><span class="sxs-lookup"><span data-stu-id="c60a5-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="c60a5-141">Pianificare il routing basato sulla posizione in Skype for business</span><span class="sxs-lookup"><span data-stu-id="c60a5-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="c60a5-142">Pianificare le funzionalità di gestione delle chiamate in Skype for business</span><span class="sxs-lookup"><span data-stu-id="c60a5-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="c60a5-143">Pianificare la resilienza di VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c60a5-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

