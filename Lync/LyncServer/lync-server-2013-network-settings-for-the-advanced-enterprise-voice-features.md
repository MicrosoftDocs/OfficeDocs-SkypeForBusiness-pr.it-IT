---
title: 'Lync Server 2013: impostazioni di rete per le funzionalità di VoIP aziendale avanzate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1d6b01009aac5fdaf3d69e24b4137897e70051b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="a820e-102">Impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a820e-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a820e-103">_**Ultimo argomento modificato:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="a820e-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="a820e-104">Lync Server dispone di tre funzionalità di VoIP aziendale avanzate: controllo di ammissione di chiamata (CAC), servizi di emergenza (E9-1-1) e bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="a820e-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="a820e-105">Tali caratteristiche condividono alcuni requisiti di configurazione per le aree di rete, i siti di rete e l'associazione di ogni subnet nella topologia di Lync Server con un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="a820e-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="a820e-106">Per informazioni dettagliate sulla pianificazione della distribuzione di queste caratteristiche, vedere:</span><span class="sxs-lookup"><span data-stu-id="a820e-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="a820e-107">Pianificazione del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a820e-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="a820e-108">Pianificazione per i servizi di emergenza (E9-1-1) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a820e-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="a820e-109">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a820e-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="a820e-110">Per informazioni dettagliate sulla distribuzione di ognuna di queste funzionalità, vedere [Deploying Advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a820e-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="a820e-111">In questo argomento viene fornita una panoramica dei requisiti di configurazione comuni a tutte e tre le funzionalità di VoIP aziendale avanzate.</span><span class="sxs-lookup"><span data-stu-id="a820e-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="a820e-112">Aree di rete</span><span class="sxs-lookup"><span data-stu-id="a820e-112">Network Regions</span></span>

<span data-ttu-id="a820e-113">Un'area di rete è un hub o un backbone di rete utilizzato solo nella configurazione dei servizi Controllo di ammissione di chiamata, E9-1-1 e Media Bypass.</span><span class="sxs-lookup"><span data-stu-id="a820e-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a820e-114">Le aree di rete non corrispondono alle aree di conferenza telefonica con accesso esterno di Lync Server, che sono necessarie per associare i numeri delle conferenze telefoniche con chiamata in ingresso con uno o più dial plan di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a820e-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="a820e-115">Per informazioni dettagliate sulle aree di conferenza telefonica con accesso esterno, vedere Servizi di <A href="lync-server-2013-dial-in-conferencing-requirements.md">conferenza telefonica con accesso esterno in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a820e-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="a820e-116">CAC richiede che ogni area di rete disponga di un sito centrale Lync Server associato, in grado di gestire il traffico multimediale all'interno dell'area (ovvero di prendere decisioni basate sui criteri configurati, in merito alla possibilità o meno di una sessione audio o video in tempo reale essere stabilito).</span><span class="sxs-lookup"><span data-stu-id="a820e-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="a820e-117">I siti centrali di Lync Server non rappresentano posizioni geografiche, ma piuttosto gruppi logici di server configurati come pool o come set di pool.</span><span class="sxs-lookup"><span data-stu-id="a820e-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="a820e-118">Per informazioni dettagliate sui siti centrali, vedere [Reference Topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a820e-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="a820e-119">Vedere anche [topologie supportate in Lync Server 2013](lync-server-2013-supported-topologies.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="a820e-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="a820e-120">Per configurare un'area di rete, è possibile utilizzare la scheda **aree** nella sezione **configurazione di rete** del pannello di controllo di Lync Server oppure eseguire i cmdlet **New-CsNetworkRegion** o **Set-CsNetworkRegion** di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a820e-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="a820e-121">Per istruzioni, vedere [creare o modificare un'area di rete in Lync server 2013](lync-server-2013-create-or-modify-a-network-region.md) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a820e-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="a820e-122">Le stesse definizioni di aree di rete sono condivise da tutte e tre le funzionalità di VoIP aziendale avanzate.</span><span class="sxs-lookup"><span data-stu-id="a820e-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="a820e-123">Se sono già state create aree di rete per una caratteristica, non è necessario creare nuove aree di rete per le altre caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="a820e-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="a820e-124">Potrebbe tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche della caratteristica.</span><span class="sxs-lookup"><span data-stu-id="a820e-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="a820e-125">Se, ad esempio, sono state create aree di rete per il servizio E9-1-1 (che non richiede un sito centrale associato) e successivamente si distribuisce il servizio Controllo di ammissione di chiamata, è necessario modificare ognuna delle definizioni di area di rete per specificare un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="a820e-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="a820e-126">Per associare un sito centrale di Lync Server a un'area di rete, è necessario specificare il nome del sito centrale utilizzando la sezione **configurazione di rete** del pannello di controllo di Lync Server oppure eseguendo i cmdlet **New-CsNetworkRegion** o **Set-CsNetworkRegion** di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a820e-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="a820e-127">Per istruzioni, vedere [creare o modificare un'area di rete in Lync server 2013](lync-server-2013-create-or-modify-a-network-region.md) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a820e-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="a820e-128">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="a820e-128">Network Sites</span></span>

<span data-ttu-id="a820e-p107">Un sito di rete rappresenta una posizione geografica, ad esempio una succursale, una filiale o la sede principale. Ogni sito di rete deve essere associato a un'area di rete specifica.</span><span class="sxs-lookup"><span data-stu-id="a820e-p107">A network site represents a geographical location, such as a branch office, a regional office, or a main office. Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a820e-131">I siti di rete vengono utilizzati solo dalle funzionalità avanzate di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="a820e-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="a820e-132">Non sono gli stessi dei siti di succursale configurati nella topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a820e-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="a820e-133">Per informazioni dettagliate sui siti di succursale, vedere <A href="lync-server-2013-reference-topologies.md">Reference Topologies in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a820e-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="a820e-134">Vedere anche <A href="lync-server-2013-supported-topologies.md">topologie supportate in Lync Server 2013</A> nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="a820e-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="a820e-135">Per configurare un sito di rete e associarlo a un'area di rete, è possibile utilizzare la sezione **configurazione di rete** del pannello di controllo di Lync Server oppure eseguire il cmdlet **New-CsNetworkSite** o **Set-CsNetworkSite** di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a820e-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="a820e-136">Per ulteriori informazioni, vedere [creare o modificare un sito di rete in Lync server 2013](lync-server-2013-create-or-modify-a-network-site.md) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a820e-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="a820e-137">Identificare le subnet IP</span><span class="sxs-lookup"><span data-stu-id="a820e-137">Identify IP Subnets</span></span>

<span data-ttu-id="a820e-p110">Per ogni sito di rete sarà necessario collaborare con l'amministratore di rete per stabilire quali subnet IP sono assegnate a ogni sito di rete. Se l'amministratore di rete ha già organizzato le subnet IP in aree di rete e siti di rete, il lavoro risulterà notevolmente semplificato.</span><span class="sxs-lookup"><span data-stu-id="a820e-p110">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="a820e-p111">In questo esempio, al sito New York nell'area Nord America sono assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si supponga che Bob, che di solito lavora a Detroit, si sposti nell'ufficio di New York per un corso di formazione. Quando accende il suo computer e si connette alla rete, al computer verrà assegnato un indirizzo IP in uno dei quattro intervalli allocati a New York, ad esempio 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="a820e-p111">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="a820e-142">Le subnet IP specificate durante la configurazione della rete nel server devono corrispondere al formato specificato dai computer client per poter essere utilizzate correttamente per Media Bypass.</span><span class="sxs-lookup"><span data-stu-id="a820e-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="a820e-143">Un client Lync prende l'indirizzo IP locale e maschera l'indirizzo IP con la subnet mask associata.</span><span class="sxs-lookup"><span data-stu-id="a820e-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="a820e-144">Durante la determinazione dell'ID bypass associato a ogni client, tramite la funzione di registrazione viene confrontato l'elenco delle subnet IP associate a ogni sito di rete con la subnet fornita dal client per individuare una corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="a820e-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="a820e-145">Per questo motivo, è importante che le subnet immesse durante la configurazione della rete nel server siano subnet effettive, anziché virtuali.</span><span class="sxs-lookup"><span data-stu-id="a820e-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="a820e-146">Se si implementa il servizio Controllo di ammissione di chiamata ma non Media Bypass, il servizio Controllo di ammissione di chiamata funzionerà in modo corretto anche se si configurano subnet virtuali.</span><span class="sxs-lookup"><span data-stu-id="a820e-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="a820e-147">Ad esempio, se un client Lync accede a un computer con un indirizzo IP di 172.29.81.57 con una subnet mask IP 255.255.255.0, richiederà l'ID di bypass associato alla subnet 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="a820e-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="a820e-148">Se la subnet è definita come 172.29.0.0/16, anche se il client appartiene alla subnet virtuale, la funzione di registrazione non la considererà una corrispondenza esatta perché cerca nello specifico la subnet 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="a820e-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="a820e-149">Pertanto, è importante che l'amministratore entri nelle subnet esattamente come indicato dai client Lync (che vengono provisionati con le subnet durante la configurazione di rete, sia in modo statico che tramite il protocollo DHCP (Dynamic Host Configuration Protocol).</span><span class="sxs-lookup"><span data-stu-id="a820e-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="a820e-150">Associazione di subnet a siti di rete</span><span class="sxs-lookup"><span data-stu-id="a820e-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="a820e-151">Ogni subnet della rete aziendale deve essere associata a un sito di rete (ovvero ogni subnet deve essere associata a una posizione geografica).</span><span class="sxs-lookup"><span data-stu-id="a820e-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="a820e-152">Questa associazione di subnet consente alle funzionalità di VoIP aziendale avanzate di individuare i punti finali in modo geografico.</span><span class="sxs-lookup"><span data-stu-id="a820e-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="a820e-153">L'individuazione degli endpoint consente, ad esempio, al servizio Controllo di ammissione di chiamata di regolare il flusso di dati audio e video in tempo reale da e verso il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="a820e-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="a820e-154">Per associare subnet a siti di rete, è possibile utilizzare la sezione **configurazione di rete** del pannello di controllo di Lync Server oppure è possibile utilizzare Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a820e-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="a820e-155">Per istruzioni, vedere [associare una subnet a un sito di rete in Lync server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) nella documentazione relativa alla distribuzione o fare riferimento alla documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a820e-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a820e-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a820e-156">See Also</span></span>


[<span data-ttu-id="a820e-157">Pianificazione del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a820e-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="a820e-158">Pianificazione per i servizi di emergenza (E9-1-1) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a820e-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="a820e-159">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a820e-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

