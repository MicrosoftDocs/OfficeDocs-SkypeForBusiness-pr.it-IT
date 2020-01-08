---
title: 'Lync Server 2013: distribuzione di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae445d954bd1be7c956d76aa48da2ad7854c6a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="474c3-102">Distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="474c3-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="474c3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="474c3-104">Lync Server 2013, Enterprise Voice fa parte dell'infrastruttura di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="474c3-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="474c3-105">La distribuzione di VoIP aziendale richiede che:</span><span class="sxs-lookup"><span data-stu-id="474c3-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="474c3-106">Esaminare la sezione [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) della documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="474c3-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="474c3-107">Finalizzare i piani per le funzionalità e i componenti da distribuire con questo carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="474c3-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="474c3-108">Eseguire lo strumento pianificazione per progettare una topologia che rispecchi le decisioni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="474c3-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="474c3-109">Aprire la struttura della topologia in Generatore di topologia, come descritto in [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="474c3-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="474c3-110">L'installazione di generatore di topologia fa parte del processo di distribuzione per il pool interno.</span><span class="sxs-lookup"><span data-stu-id="474c3-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="474c3-111">Per informazioni dettagliate, vedere <A href="lync-server-2013-install-lync-server-administrative-tools.md">installare gli strumenti di amministrazione di Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="474c3-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="474c3-112">Inoltre, è necessario che sia già stato distribuito Lync Server, Enterprise Edition presso i siti centrali e i siti di succursale che corrispondono alla topologia di riferimento che si sceglie di distribuire.</span><span class="sxs-lookup"><span data-stu-id="474c3-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="474c3-113">Non è possibile distribuire i componenti di VoIP aziendale finché non sono stati definiti, pubblicati e installati file per almeno un pool interno ed è necessario usare generatore di topologia per definire e pubblicare un pool interno.</span><span class="sxs-lookup"><span data-stu-id="474c3-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="474c3-114">Per visualizzare le topologie di riferimento con esempi di posizione in cui è possibile distribuire ruoli del server VoIP aziendale (e la loro relazione tra loro e altri ruoli del server di Lync Server 2013), vedere [topologie di riferimento in Lync server 2013](lync-server-2013-reference-topologies.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="474c3-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="474c3-115">Per visualizzare una topologia di riferimento che illustra e spiega una distribuzione del controllo di ammissione alle chiamate di esempio, incluse le aree di rete, i siti di rete e le subnet, vedere [esempio: raccolta dei requisiti per il controllo dell'ammissione delle chiamate in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="474c3-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="474c3-116">Per distribuire VoIP aziendale in un sito centrale, continuare a leggere gli argomenti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="474c3-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="474c3-117">Per distribuire VoIP aziendale in un sito di succursale, passare alla <A href="lync-server-2013-deploying-branch-sites.md">distribuzione dei siti di succursale in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="474c3-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="474c3-118">Questa sezione include procedure per le distribuzioni in cui un Mediation Server è collocato in ogni server front-end o Standard Edition, come raccomandato e anche per le distribuzioni con un pool di Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="474c3-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="474c3-119">È possibile ignorare il contenuto seguente se è stato usato generatore di topologie per definire e pubblicare una topologia che colloca un Mediation Server in ogni server front-end o Standard Edition, perché la distribuzione guidata ha già installato automaticamente i file per Mediation Server quando i file sono stati installati per il pool di front end server o per il server Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="474c3-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="474c3-120">Configurazione di trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="474c3-121">Se è stato usato generatore di topologie per definire e pubblicare un Mediation Server in un pool autonomo, è possibile usare il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="474c3-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="474c3-122">Verificare che la topologia soddisfi i prerequisiti software e ambiente, come descritto in [prerequisiti VoIP aziendale per Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="474c3-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="474c3-123">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="474c3-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="474c3-124">Prerequisiti di VoIP aziendale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="474c3-125">Distribuzione di Mediation Server e definizione di peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="474c3-126">Configurazione di trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="474c3-127">Configurazione dei dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="474c3-128">Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="474c3-129">Esportazione e importazione della configurazione di route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="474c3-130">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="474c3-131">Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="474c3-132">Distribuzione della messaggistica unificata di Exchange in locale per fornire la funzionalità di segreteria telefonica di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="474c3-133">Fornire agli utenti di Lync Server 2013 la segreteria telefonica nella messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="474c3-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="474c3-134">Configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="474c3-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="474c3-135">Distribuzione di funzionalità vocali avanzate di Enterprise in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="474c3-136">Informazioni su aree di rete, siti e subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="474c3-137">Creare o modificare un'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="474c3-138">Creare o modificare un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="474c3-139">Associare una subnet a un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="474c3-140">Configurare il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="474c3-141">Configurare i servizi di emergenza avanzati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="474c3-142">Configurare il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="474c3-143">Consentire agli utenti di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="474c3-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="474c3-144">See Also</span></span>


[<span data-ttu-id="474c3-145">Distribuzione di siti di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="474c3-146">Configurazione di conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="474c3-147">Configurazione del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="474c3-148">Configurazione degli annunci per i numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="474c3-149">Distribuzione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="474c3-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

