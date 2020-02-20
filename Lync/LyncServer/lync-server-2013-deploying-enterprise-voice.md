---
title: 'Lync Server 2013: distribuzione di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b56065b0e3b7e7ef25c81f20140e8869dbe5376
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="a6f14-102">Distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6f14-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a6f14-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a6f14-104">Lync Server 2013, VoIP aziendale fa parte dell'infrastruttura di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f14-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="a6f14-105">Per la distribuzione di VoIP aziendale è necessario:</span><span class="sxs-lookup"><span data-stu-id="a6f14-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="a6f14-106">Esaminare la sezione [pianificazione per VoIP aziendale in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) della documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a6f14-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="a6f14-107">Finalizzare i piani per le funzionalità e i componenti da distribuire con questo carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a6f14-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="a6f14-108">Eseguire lo strumento di pianificazione per progettare una topologia che rispecchi le decisioni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a6f14-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="a6f14-109">Aprire la progettazione della topologia in Generatore di topologie, come descritto in [define and Configuring the topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a6f14-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6f14-110">L'installazione di generatore di topologie è parte integrante del processo di distribuzione per il pool interno.</span><span class="sxs-lookup"><span data-stu-id="a6f14-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="a6f14-111">Per informazioni dettagliate, vedere <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 Administrative Tools</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a6f14-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="a6f14-112">È inoltre necessario che sia già stato distribuito Lync Server, Enterprise Edition nei siti centrali e nei siti di succursale che corrispondono alla topologia di riferimento che si sceglie di distribuire.</span><span class="sxs-lookup"><span data-stu-id="a6f14-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="a6f14-113">Non è possibile distribuire i componenti di VoIP aziendale fino a quando non sono stati definiti, pubblicati e installati file per almeno un pool interno ed è necessario utilizzare Generatore di topologie per definire e pubblicare un pool interno.</span><span class="sxs-lookup"><span data-stu-id="a6f14-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="a6f14-114">Per visualizzare le topologie di riferimento con esempi in cui è possibile distribuire i ruoli del server VoIP aziendale e la relazione tra loro e con altri ruoli del server Lync Server 2013, vedere [Reference Topologies in Lync server 2013](lync-server-2013-reference-topologies.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a6f14-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="a6f14-115">Per visualizzare una topologia di riferimento in cui è illustrata una distribuzione del controllo di ammissione di chiamata di esempio, tra cui aree di rete, siti di rete e subnet, vedere [esempio: raccolta dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a6f14-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a6f14-116">Per distribuire VoIP aziendale in un sito centrale, continuare a leggere gli argomenti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="a6f14-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="a6f14-117">Per distribuire VoIP aziendale in un sito di succursale, passare a <A href="lync-server-2013-deploying-branch-sites.md">distribuzione dei siti di succursale in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a6f14-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="a6f14-118">In questa sezione sono incluse le procedure per le distribuzioni in cui un Mediation Server è collocato in ogni Front End Server o server Standard Edition, come consigliato, e anche per le distribuzioni con un pool Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="a6f14-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="a6f14-119">Se è stato utilizzato il generatore di topologie per definire e pubblicare una topologia che colloca un Mediation Server in ogni Front End Server o server Standard Edition, è possibile ignorare il seguente contenuto, in quanto la distribuzione guidata ha già installato automaticamente i file per Mediation Server quando sono stati installati file per il pool Front End Server o il server Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="a6f14-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="a6f14-120">Configurazione di trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="a6f14-121">Se è stato utilizzato il generatore di topologie per definire e pubblicare un Mediation Server in un pool autonomo, è possibile utilizzare il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="a6f14-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="a6f14-122">Verificare che la topologia soddisfi i prerequisiti del software e dell'ambiente, come descritto in [Enterprise Voice Prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a6f14-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a6f14-123">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="a6f14-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="a6f14-124">Prerequisiti di VoIP aziendale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="a6f14-125">Distribuzione di Mediation Server e definizione di peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="a6f14-126">Configurazione di trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="a6f14-127">Configurazione di dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="a6f14-128">Configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="a6f14-129">Esportazione e importazione della configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="a6f14-130">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="a6f14-131">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="a6f14-132">Distribuzione della messaggistica unificata di Exchange locale per fornire la segreteria telefonica di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="a6f14-133">Fornire ai messaggi vocali di Lync Server 2013 utenti la messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="a6f14-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="a6f14-134">Configurazione dell'integrazione di Lync Server 2013 locale con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a6f14-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="a6f14-135">Distribuzione di funzionalità di VoIP aziendale avanzate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="a6f14-136">Informazioni su aree di rete, siti e subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="a6f14-137">Creare o modificare un'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="a6f14-138">Creare o modificare un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="a6f14-139">Associare una subnet a un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="a6f14-140">Configurare il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="a6f14-141">Configurare Enhanced 9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="a6f14-142">Configurare il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="a6f14-143">Abilitare gli utenti per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6f14-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6f14-144">See Also</span></span>


[<span data-ttu-id="a6f14-145">Distribuzione di siti di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="a6f14-146">Configurazione delle conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="a6f14-147">Configurazione del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="a6f14-148">Configurazione degli annunci per i numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="a6f14-149">Distribuzione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f14-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

