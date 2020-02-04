---
title: 'Lync Server 2013: pianificazione di VoIP aziendale'
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
ms.openlocfilehash: 83b0ec944ad857ffccb419cf9ed36fbca92306c8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41753256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="5102b-102">Pianificazione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-102">Planning for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5102b-103">_**Argomento Ultima modifica:** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="5102b-103">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="5102b-104">Il processo di distribuzione per VoIP aziendale dipende dalla topologia, dall'infrastruttura e dalla funzionalità di VoIP aziendale che si vuole supportare.</span><span class="sxs-lookup"><span data-stu-id="5102b-104">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="5102b-105">Le procedure necessarie dipendono dalle caratteristiche scelte, ma esistono altre considerazioni di pianificazione che è necessario apportare a un livello elevato.</span><span class="sxs-lookup"><span data-stu-id="5102b-105">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="5102b-106">In generale, prendere in considerazione il tipo e il numero di siti che si desidera distribuire e le rispettive posizioni geografiche, il volume delle chiamate in ogni sito, i tipi di collegamenti di rete che collegano i siti, se si vuole ottenere la ridondanza e il failover per le funzionalità vocali per ogni sito e se si vuole usare apparecchiature PBX esistenti.</span><span class="sxs-lookup"><span data-stu-id="5102b-106">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="5102b-107">Ci sono alcune considerazioni, ad esempio l'elevata disponibilità, da tenere in considerazione quando si prevede di usare il software di comunicazione Lync Server nel suo complesso.</span><span class="sxs-lookup"><span data-stu-id="5102b-107">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="5102b-108">Queste considerazioni sono discusse in argomenti in questa sezione, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="5102b-108">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="5102b-109">Considerazioni sulla pianificazione</span><span class="sxs-lookup"><span data-stu-id="5102b-109">Planning Considerations</span></span>

<span data-ttu-id="5102b-110">Per le decisioni di pianificazione relative alla distribuzione di uno scenario o di un componente specifico o di una funzionalità di distribuzione aziendale, vedere gli argomenti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="5102b-110">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="5102b-111">Definizione dei requisiti dell'organizzazione per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-111">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="5102b-112">Stima dell'utilizzo e del traffico vocale Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-112">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="5102b-113">Impostazioni di rete per le funzionalità vocali avanzate di Enterprise in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="5102b-114">Componenti necessari per Enterprise Voice in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-114">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="5102b-115">Pianificazione della resilienza di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="5102b-116">Pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-116">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="5102b-117">Pianificazione del servizio Controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-117">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="5102b-118">Pianificazione per i servizi di emergenza (E9-1-1) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-118">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="5102b-119">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-119">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="5102b-120">Pianificazione per le linee telefoniche private con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-120">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="5102b-121">Pianificazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-121">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="5102b-122">Pianificazione della resilienza di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-122">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="5102b-123">Linee guida per la distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-123">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="5102b-124">Panoramica del processo di distribuzione per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-124">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="5102b-125">Spostamento di utenti in VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-125">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="5102b-126">Strumento di diagnostica prechiamata di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5102b-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

