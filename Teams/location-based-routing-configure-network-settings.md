---
title: Configurare le impostazioni di rete-routing basato sulla posizione
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare e configurare aree geografiche, siti e subnet di rete per Location-Based routing per il routing diretto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822946"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="f06dd-103">Configurare le impostazioni di rete per l'instradamento basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="f06dd-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="f06dd-104">Se non è già stato fatto, leggere [piano Location-Based routing per il routing diretto](location-based-routing-plan.md) per rivedere altri passaggi che è necessario eseguire prima di configurare le impostazioni di rete per Location-Based routing.</span><span class="sxs-lookup"><span data-stu-id="f06dd-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="f06dd-105">Questo articolo descrive come configurare le impostazioni di rete per Location-Based routing.</span><span class="sxs-lookup"><span data-stu-id="f06dd-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="f06dd-106">Dopo aver distribuito il routing diretto del sistema telefonico nell'organizzazione, i passaggi successivi sono la creazione e la configurazione di aree di rete, siti di rete e subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="f06dd-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="f06dd-107">Definire le aree di rete</span><span class="sxs-lookup"><span data-stu-id="f06dd-107">Define network regions</span></span>

<span data-ttu-id="f06dd-108">Un'area di rete contiene una raccolta di siti di rete e interconnette varie parti di una rete in più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="f06dd-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="f06dd-109">Per istruzioni su come configurare le aree di rete, vedere [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="f06dd-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="f06dd-110">Definire i siti di rete</span><span class="sxs-lookup"><span data-stu-id="f06dd-110">Define network sites</span></span>

<span data-ttu-id="f06dd-111">Un sito di rete rappresenta una posizione in cui l'organizzazione ha una sede fisica, ad esempio un ufficio, un set di edifici o un campus.</span><span class="sxs-lookup"><span data-stu-id="f06dd-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="f06dd-112">È necessario associare ogni sito di rete della topologia a un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="f06dd-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="f06dd-113">Per istruzioni su come configurare i siti di rete, vedere [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="f06dd-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="f06dd-114">Una procedura consigliata per Location-Based routing consiste nel creare un sito separato per ogni posizione con connettività PSTN univoca.</span><span class="sxs-lookup"><span data-stu-id="f06dd-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="f06dd-115">È possibile creare un sito abilitato per Location-Based routing o un sito non abilitato per Location-Based routing.</span><span class="sxs-lookup"><span data-stu-id="f06dd-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="f06dd-116">Ad esempio, potresti voler creare un sito non abilitato per Location-Based routing per consentire agli utenti abilitati per Location-Based routing di effettuare chiamate PSTN quando si spostano in tale sito.</span><span class="sxs-lookup"><span data-stu-id="f06dd-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="f06dd-117">Definire le subnet di rete</span><span class="sxs-lookup"><span data-stu-id="f06dd-117">Define network subnets</span></span>

<span data-ttu-id="f06dd-118">Ogni subnet deve essere associata a un sito di rete specifico.</span><span class="sxs-lookup"><span data-stu-id="f06dd-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="f06dd-119">È possibile associare più subnet allo stesso sito di rete, ma non è possibile associare più siti alla stessa subnet.</span><span class="sxs-lookup"><span data-stu-id="f06dd-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="f06dd-120">Per istruzioni su come configurare le subnet di rete, vedere  [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="f06dd-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="f06dd-121">Per Location-Based routing, le subnet IP nella posizione in cui i team endpoint possono connettersi alla rete devono essere definite e associate a una rete definita per applicare il bypass a pedaggio.</span><span class="sxs-lookup"><span data-stu-id="f06dd-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="f06dd-122">Questa associazione di subnet consente Location-Based routing per individuare gli endpoint geograficamente per determinare se una determinata chiamata PSTN deve essere consentita.</span><span class="sxs-lookup"><span data-stu-id="f06dd-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="f06dd-123">Sono supportate sia le subnet IPv6 che IPv4.</span><span class="sxs-lookup"><span data-stu-id="f06dd-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="f06dd-124">Per determinare se un endpoint di teams si trova in un sito, Location-Based routing controlla prima di tutto un indirizzo IPv6 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f06dd-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="f06dd-125">Se non è presente un indirizzo IPv6, Location-Based il routing controlla l'indirizzo IPv4.</span><span class="sxs-lookup"><span data-stu-id="f06dd-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="f06dd-126">Definire indirizzi IP attendibili (subnet esterne)</span><span class="sxs-lookup"><span data-stu-id="f06dd-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="f06dd-127">Gli indirizzi IP attendibili sono gli indirizzi IP esterni Internet della rete aziendale e vengono usati per determinare se l'endpoint dell'utente si trova all'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="f06dd-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="f06dd-128">Per istruzioni su come configurare indirizzi IP attendibili, vedere  [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="f06dd-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="f06dd-129">Se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP presente nell'elenco indirizzi IP attendibili, Location-Based i controlli di routing per determinare la subnet interna in cui si trova l'endpoint dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f06dd-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="f06dd-130">Se l'indirizzo IP esterno dell'utente non corrisponde a un indirizzo IP definito nell'elenco di indirizzi IP attendibili, l'endpoint viene classificato come in una posizione sconosciuta e tutte le chiamate PSTN da o verso un utente abilitato per Location-Based routing sono bloccate.</span><span class="sxs-lookup"><span data-stu-id="f06dd-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f06dd-131">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f06dd-131">Next steps</span></span>

<span data-ttu-id="f06dd-132">Accedere a [abilita Location-Based routing per il routing diretto](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="f06dd-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f06dd-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f06dd-133">Related topics</span></span>

- [<span data-ttu-id="f06dd-134">Impostazioni di rete per le funzionalità vocali di cloud in teams</span><span class="sxs-lookup"><span data-stu-id="f06dd-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
