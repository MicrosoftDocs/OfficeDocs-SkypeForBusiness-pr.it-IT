---
title: 'Lync Server 2013: configurazione di trunk'
description: 'Lync Server 2013: configurazione di trunk.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07d9503cd38419a7145796a6edf8484a14cdeb53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544152"
---
# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="98c36-103">Configurazione di trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-103">Configuring trunks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98c36-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="98c36-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="98c36-105">Nell'ambito della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più dei seguenti peer per fornire la connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi Enterprise Voice nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="98c36-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="98c36-106">Connessione con trunk SIP a un provider di servizi di telefonia Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="98c36-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="98c36-107">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="98c36-107">PSTN gateway</span></span>

  - <span data-ttu-id="98c36-108">Centralino (PBX)</span><span class="sxs-lookup"><span data-stu-id="98c36-108">Private branch exchange (PBX)</span></span>

<span data-ttu-id="98c36-109">Per informazioni dettagliate, vedere [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="98c36-109">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="98c36-110">Prima di iniziare la configurazione del trunk, verificare che la topologia sia stata creata e che il Mediation Server e il relativo peer siano stati configurati e associati l'uno all'altro.</span><span class="sxs-lookup"><span data-stu-id="98c36-110">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="98c36-111">Per informazioni dettagliate, vedere <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">define a gateway in Generatore di topologie in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="98c36-111">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="98c36-112">Come parte della configurazione trunk, è possibile abilitare la funzionalità di bypass multimediale di Lync Server 2013, che consente di bypassare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="98c36-112">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="98c36-113">I trunk possono essere configurati con o senza il bypass multimediale abilitato, ma è consigliabile abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="98c36-113">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="98c36-114">Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-media-bypass.md">Planning for Media Bypass in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="98c36-114">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="98c36-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="98c36-115">In This Section</span></span>

  - [<span data-ttu-id="98c36-116">Supporto per più trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-116">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="98c36-117">Routing tra trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-117">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="98c36-118">Visualizzare le informazioni di configurazione del trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-118">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="98c36-119">Configurare un trunk con bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-119">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="98c36-120">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-120">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="98c36-121">Creare una nuova raccolta di impostazioni di configurazione trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-121">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="98c36-122">Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-122">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="98c36-123">Modificare le impostazioni di configurazione del trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-123">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="98c36-124">Testare le impostazioni di configurazione del trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-124">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="98c36-125">Visualizzare informazioni sui singoli trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-125">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98c36-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98c36-126">See Also</span></span>


[<span data-ttu-id="98c36-127">Definire un gateway in Generatore di topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-127">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="98c36-128">Pianificazione della connettività PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-128">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="98c36-129">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c36-129">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

