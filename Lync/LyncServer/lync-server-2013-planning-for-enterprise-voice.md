---
title: 'Lync Server 2013: pianificazione di VoIP aziendale'
description: 'Lync Server 2013: pianificazione di VoIP aziendale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice
ms:assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413081(v=OCS.15)
ms:contentKeyID: 48185959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dfa0d91fe8270e49524d648ef403cd69ede2407
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571852"
---
# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="61dbe-103">Pianificazione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-103">Planning for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61dbe-104">_**Ultimo argomento modificato:** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="61dbe-104">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="61dbe-105">Il processo di distribuzione per VoIP aziendale dipende dalla topologia esistente, dall'infrastruttura e dalla funzionalità VoIP aziendale che si desidera supportare.</span><span class="sxs-lookup"><span data-stu-id="61dbe-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="61dbe-106">Le procedure necessarie dipenderanno dalle funzionalità scelte, ma è necessario tenere conto di altre considerazioni sulla pianificazione a livello superiore.</span><span class="sxs-lookup"><span data-stu-id="61dbe-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="61dbe-107">In generale, prendere in considerazione il tipo e il numero di siti che si desidera distribuire e le relative posizioni geografiche, il volume delle chiamate in ogni sito, i tipi di collegamenti di rete che connettono i siti, se si desidera fornire ridondanza e failover per le funzionalità vocali per ogni sito e se si desidera utilizzare apparecchiature PBX esistenti.</span><span class="sxs-lookup"><span data-stu-id="61dbe-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="61dbe-108">Sono presenti alcune considerazioni, ad esempio la disponibilità elevata, che è necessario prendere in considerazione quando si pianifica il software di comunicazione di Lync Server nel suo complesso.</span><span class="sxs-lookup"><span data-stu-id="61dbe-108">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="61dbe-109">Queste considerazioni sono descritte negli argomenti in questa sezione, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="61dbe-109">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="61dbe-110">Considerazioni di pianificazione</span><span class="sxs-lookup"><span data-stu-id="61dbe-110">Planning Considerations</span></span>

<span data-ttu-id="61dbe-111">Per le decisioni relative alla distribuzione di uno scenario o di un componente di distribuzione o di una specifica funzionalità di VoIP aziendale, consultare gli argomenti di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="61dbe-111">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="61dbe-112">Definizione dei requisiti per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-112">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="61dbe-113">Stima dell'utilizzo e del traffico vocale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-113">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="61dbe-114">Impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-114">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="61dbe-115">Componenti necessari per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-115">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="61dbe-116">Pianificazione della resilienza di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-116">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="61dbe-117">Pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-117">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="61dbe-118">Pianificazione del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-118">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="61dbe-119">Pianificazione per i servizi di emergenza (E9-1-1) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-119">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="61dbe-120">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-120">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="61dbe-121">Pianificazione per le linee telefoniche private con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-121">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="61dbe-122">Pianificazione del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-122">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="61dbe-123">Pianificazione della resilienza di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-123">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="61dbe-124">Linee guida per la distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-124">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="61dbe-125">Panoramica del processo di distribuzione per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-125">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="61dbe-126">Spostamento di utenti in VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-126">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="61dbe-127">Lync PreCall Diagnostics Tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61dbe-127">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

