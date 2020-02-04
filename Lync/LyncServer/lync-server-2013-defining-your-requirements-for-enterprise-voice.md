---
title: "Lync Server 2013: Definizione dei requisiti dell'organizzazione per VoIP aziendale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8987905d2b117eb889486882b7d74ce4e52659a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="c2347-102">Definizione dei requisiti dell'organizzazione per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2347-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2347-103">_**Argomento Ultima modifica:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="c2347-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="c2347-104">Questo argomento offre una panoramica delle considerazioni che è necessario apportare in merito alle aree geografiche, ai siti e ai collegamenti tra i siti della topologia e in che modo sono importanti quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c2347-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c2347-105">Per informazioni dettagliate su come prendere queste decisioni, vedere [impostazioni di rete per le funzionalità vocali avanzate di Enterprise in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c2347-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="c2347-106">Siti e aree geografiche</span><span class="sxs-lookup"><span data-stu-id="c2347-106">Sites and Regions</span></span>

<span data-ttu-id="c2347-107">Prima di tutto, identificare i siti della topologia in cui distribuire VoIP aziendale e le aree di rete a cui appartengono tali siti.</span><span class="sxs-lookup"><span data-stu-id="c2347-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="c2347-108">In particolare, valutare come si fornirà la connettività PSTN (Public Switched Telephone Network) a ogni sito.</span><span class="sxs-lookup"><span data-stu-id="c2347-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="c2347-109">Per motivi di gestibilità e logistica, le aree geografiche a cui appartengono questi siti possono essere un fattore decisivo.</span><span class="sxs-lookup"><span data-stu-id="c2347-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="c2347-110">Decidere dove verranno distribuiti i gateway localmente, dove saranno distribuiti gli appliance Survivable Branch (SBAs) e dove è possibile configurare trunk SIP (localmente o nel sito centrale) in un provider di servizi di telefonia Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="c2347-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="c2347-111">Collegamenti di rete tra siti</span><span class="sxs-lookup"><span data-stu-id="c2347-111">Network Links Between Sites</span></span>

<span data-ttu-id="c2347-112">È inoltre necessario prendere in considerazione l'utilizzo della larghezza di banda previsto nei collegamenti di rete tra il sito centrale e i siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="c2347-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="c2347-113">Se si ha o si prevede di distribuire i collegamenti WAN resilienti tra i siti, è consigliabile distribuire un gateway in ogni sito di succursale per specificare la terminazione per gli utenti di tali siti.</span><span class="sxs-lookup"><span data-stu-id="c2347-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="c2347-114">Se si hanno collegamenti WAN resilienti, ma è probabile che la larghezza di banda di un collegamento WAN sia vincolata, configurare il controllo di ammissione delle chiamate per il collegamento.</span><span class="sxs-lookup"><span data-stu-id="c2347-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="c2347-115">Se non si dispone di collegamenti WAN resilienti, è necessario ospitare meno di 1000 utenti nel sito di succursale e non sono disponibili amministratori di Lync Server addestrati localmente, è consigliabile distribuire un Survivable Branch Appliance nel sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="c2347-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="c2347-116">Se si ospitano tra gli utenti di 1000 e 5000 nel sito di succursale, non è disponibile una connessione WAN resiliente e sono stati addestrati gli amministratori di Lync Server, è consigliabile distribuire un Survivable Branch Server con un piccolo gateway nel sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="c2347-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="c2347-117">Se si ha un peer del gateway che supporta il bypass multimediale, è consigliabile anche abilitare il bypass multimediale sui collegamenti vincolati.</span><span class="sxs-lookup"><span data-stu-id="c2347-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2347-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2347-118">See Also</span></span>


[<span data-ttu-id="c2347-119">Impostazioni di rete per le funzionalità vocali avanzate di Enterprise in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2347-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

