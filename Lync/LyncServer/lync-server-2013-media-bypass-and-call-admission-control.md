---
title: 'Lync Server 2013: Bypass multimediale e controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5e02a57add6b93f1ad5c5efc3ac644e65e97f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="66bb2-102">Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66bb2-102">Media bypass and call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66bb2-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="66bb2-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="66bb2-104">Bypass multimediale e controllo di ammissione alle chiamate (CAC) collaborare per gestire il controllo della larghezza di banda per il supporto delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="66bb2-104">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media.</span></span> <span data-ttu-id="66bb2-105">Il bypass multimediale facilita il flusso multimediale sui collegamenti collegati correttamente; CAC gestisce il traffico sui collegamenti con vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="66bb2-105">Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints.</span></span> <span data-ttu-id="66bb2-106">Poiché il bypass multimediale e il CAC si escludono a vicenda, è necessario essere consapevoli di uno durante la pianificazione per l'altro.</span><span class="sxs-lookup"><span data-stu-id="66bb2-106">Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other.</span></span> <span data-ttu-id="66bb2-107">Sono supportate le combinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66bb2-107">The following combinations are supported:</span></span>

  - <span data-ttu-id="66bb2-108">CAC e bypass multimediale sono entrambi abilitati.</span><span class="sxs-lookup"><span data-stu-id="66bb2-108">CAC and Media Bypass are both enabled.</span></span> <span data-ttu-id="66bb2-109">Il bypass multimediale deve essere impostato per l' **uso di informazioni sul sito e sulle aree**geografiche.</span><span class="sxs-lookup"><span data-stu-id="66bb2-109">Media Bypass must be set to **Use Site and Region Information**.</span></span> <span data-ttu-id="66bb2-110">Le informazioni di questo sito e area geografica sono le stesse usate per CAC.</span><span class="sxs-lookup"><span data-stu-id="66bb2-110">This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="66bb2-111">Se si Abilita CAC, non è possibile selezionare **sempre l'esclusione**e viceversa, perché le due configurazioni si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="66bb2-111">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive.</span></span> <span data-ttu-id="66bb2-112">Vale a dire che solo uno dei due verrà applicato a qualsiasi chiamata PSTN specificata.</span><span class="sxs-lookup"><span data-stu-id="66bb2-112">That is, only one of the two will apply to any given PSTN call.</span></span> <span data-ttu-id="66bb2-113">Viene innanzitutto eseguito un controllo per determinare se il bypass multimediale si applica alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="66bb2-113">First, a check is made to determine if media bypass applies to the call.</span></span> <span data-ttu-id="66bb2-114">In caso affermativo, il CAC non viene usato.</span><span class="sxs-lookup"><span data-stu-id="66bb2-114">If it does, then CAC is not used.</span></span> <span data-ttu-id="66bb2-115">Questo ha senso, perché se una chiamata è idonea per il bypass, è per definizione usando una connessione in cui CAC non è necessario.</span><span class="sxs-lookup"><span data-stu-id="66bb2-115">This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed.</span></span> <span data-ttu-id="66bb2-116">Se non è possibile applicare l'esclusione alla chiamata, ovvero se gli ID di bypass del client e del gateway non corrispondono, viene applicato il CAC alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="66bb2-116">If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="66bb2-117">CAC non abilitato e il bypass multimediale impostato su **Ignora sempre**.</span><span class="sxs-lookup"><span data-stu-id="66bb2-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="66bb2-118">In questa configurazione, sia le subnet client che quelle trunk sono mappate a uno e solo un ID di bypass, calcolato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="66bb2-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="66bb2-119">CAC non abilitato e bypass multimediale impostato per l' **uso di informazioni sul sito e sulle aree**geografiche.</span><span class="sxs-lookup"><span data-stu-id="66bb2-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="66bb2-120">Dove è abilitata l' **uso delle informazioni sul sito e sull'area geografica** , la determinazione di bypass funziona essenzialmente allo stesso modo, indipendentemente dal fatto che CAC sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="66bb2-120">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not.</span></span> <span data-ttu-id="66bb2-121">Per qualsiasi chiamata PSTN, la subnet del client viene mappata a un determinato sito e viene estratto l'ID di bypass per la subnet.</span><span class="sxs-lookup"><span data-stu-id="66bb2-121">That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted.</span></span> <span data-ttu-id="66bb2-122">Analogamente, la subnet del gateway viene mappata a un determinato sito e viene estratto l'ID di bypass per la subnet.</span><span class="sxs-lookup"><span data-stu-id="66bb2-122">Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted.</span></span> <span data-ttu-id="66bb2-123">Solo se i due ID di bypass sono identici verranno ignorati per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="66bb2-123">Only if the two bypass IDs are identical will bypass happen for the call.</span></span> <span data-ttu-id="66bb2-124">Se non sono identici, il bypass multimediale non si verificherà.</span><span class="sxs-lookup"><span data-stu-id="66bb2-124">If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="66bb2-125">Anche se CAC è disabilitato a livello globale, è necessario definire i criteri di larghezza di banda per ogni sito e collegamento se si vuole usare la configurazione del sito e dell'area geografica per controllare la decisione di esclusione.</span><span class="sxs-lookup"><span data-stu-id="66bb2-125">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision.</span></span> <span data-ttu-id="66bb2-126">Il valore effettivo del vincolo di larghezza di banda o della relativa modalità non ha importanza.</span><span class="sxs-lookup"><span data-stu-id="66bb2-126">The actual value of the bandwidth constraint or its modality doesn’t matter.</span></span> <span data-ttu-id="66bb2-127">L'obiettivo finale è quello di far calcolare automaticamente i diversi ID di bypass da associare a impostazioni locali diverse che non sono ben connesse.</span><span class="sxs-lookup"><span data-stu-id="66bb2-127">The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected.</span></span> <span data-ttu-id="66bb2-128">La definizione di un vincolo di larghezza di banda per definizione significa che un collegamento non è ben connesso.</span><span class="sxs-lookup"><span data-stu-id="66bb2-128">Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="66bb2-129">CAC è abilitato e il bypass multimediale non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="66bb2-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="66bb2-130">Questo problema si applica solo quando tutti i gateway e i PBX IP non sono ben connessi o non soddisfano altri requisiti per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="66bb2-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="66bb2-131">Per informazioni dettagliate sui requisiti per il bypass multimediale, vedere [requisiti tecnici per il bypass multimediale in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="66bb2-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="66bb2-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66bb2-132">See Also</span></span>


[<span data-ttu-id="66bb2-133">Panoramica del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66bb2-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="66bb2-134">Modalità di bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66bb2-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="66bb2-135">Requisiti tecnici per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66bb2-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

