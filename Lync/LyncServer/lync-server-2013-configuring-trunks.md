---
title: 'Lync Server 2013: Configurazione di trunk'
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
ms.openlocfilehash: f1021295b375e4f28294ffb1ca5738d651f9ced2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="1fdb1-102">Configurazione di trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fdb1-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1fdb1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1fdb1-104">Come parte della distribuzione VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più dei peer seguenti per consentire la connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendali nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="1fdb1-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="1fdb1-105">Connessione trunk SIP a un provider di servizi di telefonia Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="1fdb1-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="1fdb1-106">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="1fdb1-106">PSTN gateway</span></span>

  - <span data-ttu-id="1fdb1-107">PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="1fdb1-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="1fdb1-108">Per informazioni dettagliate, vedere [pianificazione della connettività PSTN in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1fdb1-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1fdb1-109">Prima di iniziare la configurazione del trunk, verificare che la topologia sia stata creata e che il Mediation Server e il relativo peer siano stati configurati e associati tra loro.</span><span class="sxs-lookup"><span data-stu-id="1fdb1-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="1fdb1-110">Per informazioni dettagliate, vedere <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definire un gateway in Generatore di topologia in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1fdb1-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1fdb1-111">Come parte della configurazione trunk, è possibile abilitare la caratteristica di bypass multimediale di Lync Server 2013, che consente di ignorare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="1fdb1-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="1fdb1-112">I trunk possono essere configurati con o senza bypass multimediale abilitato, ma ti consigliamo vivamente di abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="1fdb1-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="1fdb1-113">Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-media-bypass.md">pianificazione di un bypass multimediale in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1fdb1-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1fdb1-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1fdb1-114">In This Section</span></span>

  - [<span data-ttu-id="1fdb1-115">Supporto per più trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="1fdb1-116">Routing tra trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="1fdb1-117">Visualizzare le informazioni di configurazione del trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="1fdb1-118">Configurare un trunk con il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="1fdb1-119">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="1fdb1-120">Creare una nuova raccolta di impostazioni di configurazione trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="1fdb1-121">Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="1fdb1-122">Modificare le impostazioni di configurazione del trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="1fdb1-123">Verificare le impostazioni di configurazione del trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="1fdb1-124">Visualizzare informazioni sui singoli trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1fdb1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fdb1-125">See Also</span></span>


[<span data-ttu-id="1fdb1-126">Definire un gateway in Generatore di topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="1fdb1-127">Pianificazione della connettività PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="1fdb1-128">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fdb1-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

