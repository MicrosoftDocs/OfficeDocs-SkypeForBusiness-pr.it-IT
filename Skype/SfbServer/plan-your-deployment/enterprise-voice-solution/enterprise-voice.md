---
title: Pianificare VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Nozioni di base sulla pianificazione di VoIP aziendale in Skype for Business Server, inclusi siti, aree geografiche, collegamenti di rete tra siti e stima del traffico di utilizzo vocale.
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825676"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="06a09-103">Pianificare VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="06a09-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="06a09-104">Nozioni di base sulla pianificazione di VoIP aziendale in Skype for Business Server, inclusi siti, aree geografiche, collegamenti di rete tra siti e stima del traffico di utilizzo vocale.</span><span class="sxs-lookup"><span data-stu-id="06a09-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="06a09-105">Il processo di distribuzione per VoIP aziendale dipende dalla topologia esistente, dall'infrastruttura e dalla funzionalità VoIP aziendale che si desidera supportare.</span><span class="sxs-lookup"><span data-stu-id="06a09-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="06a09-106">Le procedure necessarie dipenderanno dalle funzionalità scelte, ma è necessario tenere conto di altre considerazioni sulla pianificazione a livello superiore.</span><span class="sxs-lookup"><span data-stu-id="06a09-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="06a09-107">In generale, prendere in considerazione il tipo e il numero di siti che si desidera distribuire e le relative posizioni geografiche, il volume delle chiamate in ogni sito, i tipi di collegamenti di rete che connettono i siti, se si desidera fornire ridondanza e failover per le funzionalità vocali per ogni sito e se si desidera utilizzare apparecchiature PBX esistenti.</span><span class="sxs-lookup"><span data-stu-id="06a09-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="06a09-108">Sono presenti alcune considerazioni, ad esempio la disponibilità elevata, che è opportuno considerare quando si pianifica di utilizzare Skype for Business Server nel suo complesso.</span><span class="sxs-lookup"><span data-stu-id="06a09-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="06a09-109">Queste considerazioni sono descritte negli argomenti in questa sezione, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="06a09-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="06a09-110">Siti e aree geografiche</span><span class="sxs-lookup"><span data-stu-id="06a09-110">Sites and regions</span></span>

<span data-ttu-id="06a09-111">In primo luogo, identificare i siti nella topologia in cui verranno distribuiti Enterprise Voice e le aree di rete a cui appartengono tali siti.</span><span class="sxs-lookup"><span data-stu-id="06a09-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="06a09-112">Valutare in particolare il modo in cui verrà fornita la connettività PSTN (Public Switched Telephone Network) a ogni sito.</span><span class="sxs-lookup"><span data-stu-id="06a09-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="06a09-113">Per motivi logistici e di gestione, le aree a cui appartengono questi siti possono rappresentare un fattore decisivo.</span><span class="sxs-lookup"><span data-stu-id="06a09-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="06a09-114">Decidere dove verranno distribuiti i gateway localmente, in cui verrà distribuito Survivable Branch Appliance (SBA) e dove è possibile configurare trunk SIP (localmente o nel sito centrale) a un provider di servizi di telefonia Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="06a09-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="06a09-115">Collegamenti di rete tra siti</span><span class="sxs-lookup"><span data-stu-id="06a09-115">Network links between sites</span></span>

<span data-ttu-id="06a09-116">È inoltre necessario prendere in considerazione l'utilizzo della larghezza di banda previsto nei collegamenti di rete tra il sito centrale e i siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="06a09-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="06a09-117">Se si dispone o si pianifica la distribuzione dei collegamenti WAN resilienti tra i siti, è consigliabile distribuire un gateway in ogni sito di succursale per fornire la terminazione DID (Direct inwards) locale per gli utenti di tali siti.</span><span class="sxs-lookup"><span data-stu-id="06a09-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="06a09-118">Se si dispone di collegamenti WAN resilienti, ma è probabile che la larghezza di banda di un collegamento WAN sia vincolata, configurare il servizio Controllo di ammissione di chiamata per il collegamento.</span><span class="sxs-lookup"><span data-stu-id="06a09-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="06a09-119">Se non si dispone di collegamenti WAN resilienti, ospitare meno di 1000 utenti nel sito di succursale e non sono disponibili amministratori di Skype for Business Server addestrati localmente, è consigliabile distribuire un Survivable Branch Appliance nel sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="06a09-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="06a09-120">Se si dispone di un host compreso tra 1000 e 5000 utenti nel sito di succursale, manca una connessione WAN resiliente e sono disponibili amministratori di Skype for Business Server addestrati, è consigliabile distribuire un Survivable Branch Server con un gateway di piccole dimensioni nel sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="06a09-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="06a09-121">Prendere inoltre in considerazione l'eventualità di abilitare il bypass multimediale nei collegamenti vincolati se si dispone di un peer gateway che supporta il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="06a09-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="06a09-122">Stima dell'utilizzo e del traffico vocale</span><span class="sxs-lookup"><span data-stu-id="06a09-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="06a09-123">Microsoft Lync Server 2013, strumento di pianificazione utilizza la metrica seguente per valutare il traffico degli utenti in ogni sito e il numero di porte necessarie per il supporto del traffico.</span><span class="sxs-lookup"><span data-stu-id="06a09-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="06a09-124">Per un livello di **traffico leggero** (una chiamata PSTN per utente all'ora) considerare 15 utenti per porta.</span><span class="sxs-lookup"><span data-stu-id="06a09-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="06a09-125">Per un livello di **traffico medio** (2 chiamate PSTN per utente all'ora) considerare 10 utenti per porta.</span><span class="sxs-lookup"><span data-stu-id="06a09-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="06a09-126">Per un livello di **traffico pesante** (3 chiamate PSTN o più per utente all'ora) considerare 5 utenti per porta.</span><span class="sxs-lookup"><span data-stu-id="06a09-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="06a09-127">Il numero di porte determina il numero di Mediation Server e gateway necessari.</span><span class="sxs-lookup"><span data-stu-id="06a09-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="06a09-128">I gateway PSTN (Public Switched Telephone Network) distribuiti nella maggior parte delle organizzazioni variano in dimensione da 2 a 960 porte.</span><span class="sxs-lookup"><span data-stu-id="06a09-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="06a09-129">Sono disponibili anche gateway più grandi, ma vengono utilizzati principalmente dai provider di servizi di telefonia.</span><span class="sxs-lookup"><span data-stu-id="06a09-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="06a09-p106">Un'organizzazione con 10.000 utenti e traffico medio, ad esempio, necessiterebbe di 1000 porte. Il numero di gateway richiesti sarebbe uguale al numero totale di porte necessarie determinato in base alla capacità totale dei gateway.</span><span class="sxs-lookup"><span data-stu-id="06a09-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="06a09-132">Componenti, funzionalità e opzioni di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="06a09-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="06a09-133">Per ulteriori informazioni sulla pianificazione della distribuzione di VoIP aziendale, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="06a09-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="06a09-134">Componenti necessari per VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="06a09-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="06a09-135">Pianificare la connettività PSTN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="06a09-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="06a09-136">Impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="06a09-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="06a09-137">Pianificare il controllo di ammissione di chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="06a09-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="06a09-138">Pianificare i servizi di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="06a09-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="06a09-139">Pianificare il bypass multimediale in Skype for business</span><span class="sxs-lookup"><span data-stu-id="06a09-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="06a09-140">Pianificare le linee telefoniche private con Skype for business</span><span class="sxs-lookup"><span data-stu-id="06a09-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="06a09-141">Pianificare Location-Based routing in Skype for business</span><span class="sxs-lookup"><span data-stu-id="06a09-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="06a09-142">Pianificare le funzionalità di gestione delle chiamate in Skype for business</span><span class="sxs-lookup"><span data-stu-id="06a09-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="06a09-143">Pianificare la resilienza di VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="06a09-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

