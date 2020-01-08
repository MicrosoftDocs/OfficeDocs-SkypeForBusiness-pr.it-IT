---
title: 'Lync Server 2013: Informazioni su aree di rete, siti e subnet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6601a0baafd1226f4e283d62a8cbdb410064ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="71d01-102">Informazioni su aree di rete, siti e subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71d01-102">About network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71d01-103">_**Argomento Ultima modifica:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="71d01-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="71d01-104">Le funzionalità vocali avanzate di Enterprise descritte in questa sezione condividono determinati requisiti di configurazione per le aree di rete, i siti di rete e le subnet.</span><span class="sxs-lookup"><span data-stu-id="71d01-104">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets.</span></span> <span data-ttu-id="71d01-105">Ad esempio, tutte e tre le caratteristiche avanzate richiedono che ogni subnet della topologia sia associata a un *sito di rete*specifico e ogni sito di rete debba essere associato a un'area di *rete*.</span><span class="sxs-lookup"><span data-stu-id="71d01-105">For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="71d01-106">Prima di iniziare la configurazione di rete per il controllo dell'ammissione alle chiamate, E9-1-1 o bypass multimediale, verificare di avere esaminato altre informazioni sulle impostazioni di rete nelle <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">impostazioni di rete per le funzionalità vocali avanzate di Enterprise nell'argomento di Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="71d01-106">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="71d01-107">Per informazioni dettagliate sulla configurazione della rete principalmente sul controllo dell'ammissione alle chiamate, vedere anche <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">definizione dei requisiti per il controllo dell'ammissione delle chiamate in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="71d01-107">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="71d01-108">Il controllo di ammissione alle chiamate e il E9-1-1 hanno requisiti di configurazione aggiuntivi per i siti di rete:</span><span class="sxs-lookup"><span data-stu-id="71d01-108">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="71d01-109">Il controllo di ammissione alle chiamate richiede che venga specificato un *profilo dei criteri di larghezza di banda* per ogni sito vincolato dalle limitazioni della larghezza di banda WAN.</span><span class="sxs-lookup"><span data-stu-id="71d01-109">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="71d01-110">Se si prevede di distribuire il controllo di ammissione di chiamata, è necessario [creare profili dei criteri di larghezza di banda in Lync Server 2013 prima di](lync-server-2013-create-bandwidth-policy-profiles.md) configurare i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="71d01-110">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="71d01-111">E9-1-1 richiede l'impostazione di un *criterio di posizione* per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="71d01-111">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="71d01-112">Se si prevede di distribuire E9-1-1, è necessario [creare criteri di posizione in Lync Server 2013 prima di](lync-server-2013-create-location-policies.md) configurare i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="71d01-112">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="71d01-113">Creare o modificare aree di rete, siti di rete e subnet</span><span class="sxs-lookup"><span data-stu-id="71d01-113">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="71d01-114">Gli argomenti seguenti includono la procedura per creare o modificare aree di rete e siti di rete e per associare subnet a siti di rete.</span><span class="sxs-lookup"><span data-stu-id="71d01-114">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites.</span></span> <span data-ttu-id="71d01-115">Questi argomenti non sono specifici di una particolare caratteristica di VoIP aziendale avanzata.</span><span class="sxs-lookup"><span data-stu-id="71d01-115">These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="71d01-116">Creare o modificare un'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71d01-116">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="71d01-117">Creare o modificare un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71d01-117">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="71d01-118">Associare una subnet a un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71d01-118">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

