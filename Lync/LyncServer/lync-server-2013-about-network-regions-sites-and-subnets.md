---
title: 'Lync Server 2013: informazioni su aree di rete, siti e subnet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2f6de7a39b3029f1edc1252b90ec264d774632f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="afee3-102">Informazioni su aree di rete, siti e subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afee3-102">About network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afee3-103">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="afee3-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="afee3-p101">Le funzionalità di VoIP aziendale avanzate illustrate in questa sezione hanno in comune alcuni requisiti di configurazione per le aree di rete, i siti di rete e le subnet. Ad esempio, tutte e tre le funzionalità avanzate richiedono che ogni subnet della topologia sia associata a un *sito di rete* specifico e che ogni sito di rete debba essere associato a un'*area di rete*.</span><span class="sxs-lookup"><span data-stu-id="afee3-p101">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets. For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="afee3-106">Prima di iniziare la configurazione di rete per il controllo di ammissione di chiamata, E9-1-1 o bypass multimediale, verificare di aver esaminato ulteriori informazioni sulle impostazioni di rete nelle <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">impostazioni di rete per le funzionalità avanzate di VoIP aziendale in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="afee3-106">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="afee3-107">Per informazioni dettagliate sulla configurazione di rete principalmente sul controllo di ammissione di chiamata, vedere <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="afee3-107">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="afee3-108">Per il controllo di ammissione di chiamata e il servizio E9-1-1 sono previsti ulteriori requisiti di configurazione per i siti di rete:</span><span class="sxs-lookup"><span data-stu-id="afee3-108">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="afee3-109">Per il controllo di ammissione di chiamata è necessario specificare un *profilo di criteri di larghezza di banda* per ogni sito vincolato da limitazioni della larghezza di banda WAN.</span><span class="sxs-lookup"><span data-stu-id="afee3-109">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="afee3-110">Se si prevede di distribuire il controllo di ammissione di chiamata, è necessario [creare i profili dei criteri di larghezza di banda in Lync Server 2013 prima di](lync-server-2013-create-bandwidth-policy-profiles.md) configurare i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="afee3-110">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="afee3-111">Per il servizio E9-1-1 è necessario specificare *criteri di percorso* per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="afee3-111">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="afee3-112">Se si prevede di distribuire il servizio E9-1-1, è necessario [creare criteri percorso in Lync Server 2013](lync-server-2013-create-location-policies.md) prima di configurare i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="afee3-112">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="afee3-113">Creare o modificare aree di rete, siti di rete e subnet</span><span class="sxs-lookup"><span data-stu-id="afee3-113">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="afee3-p105">Gli argomenti seguenti descrivono le procedure per creare e modificare aree di rete e siti di rete, nonché per associare subnet a siti di rete. Questi argomenti non sono specifici per alcuna funzionalità VoIP aziendale avanzata particolare.</span><span class="sxs-lookup"><span data-stu-id="afee3-p105">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites. These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="afee3-116">Creare o modificare un'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afee3-116">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="afee3-117">Creare o modificare un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afee3-117">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="afee3-118">Associare una subnet a un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afee3-118">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

