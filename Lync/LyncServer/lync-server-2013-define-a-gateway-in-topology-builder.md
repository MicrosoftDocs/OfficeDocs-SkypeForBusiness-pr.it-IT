---
title: 'Lync Server 2013: definire un gateway in Generatore di topologie'
description: 'Lync Server 2013: definire un gateway in Generatore di topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f8bf09f06f54d8988c8c9a9e385ef251a960bd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567802"
---
# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="c6b9a-103">Definire un gateway in Generatore di topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6b9a-103">Define a gateway in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6b9a-104">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="c6b9a-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="c6b9a-105">Eseguire la procedura seguente per utilizzare il generatore di topologie per definire un *peer* con cui è possibile associare un Mediation Server per fornire la connettività alla rete PSTN (Public Switched Telephone Network) per gli utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-105">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="c6b9a-106">Un peer per il Mediation Server può essere un gateway PSTN, un IP-PBX o un session border controller (SBC) per un provider di servizi di telefonia Internet (ITSP) a cui si effettua la connessione configurando un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c6b9a-107">In questo argomento si presuppone che sia stato configurato almeno un pool Front End interno o un server Standard Edition in almeno un sito centrale con un Mediation Server collocato o autonomo, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and Configure a front end pool or Standard Edition server in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-107">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="c6b9a-108">In questo argomento si presuppone inoltre che sia stata verificata la conformità dell'infrastruttura ai prerequisiti descritti nei prerequisiti <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">software per VoIP aziendale in Lync server 2013</A> e <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">ai prerequisiti di configurazione e sicurezza per VoIP aziendale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-108">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="c6b9a-109">Per definire un peer per il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="c6b9a-109">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="c6b9a-110">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="c6b9a-111">In Lync Server 2013, nome del sito, componenti condivisi fare clic con il pulsante destro del mouse sul nodo **gateway PSTN** e quindi scegliere **nuovo gateway PSTN**.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-111">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="c6b9a-112">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="c6b9a-112">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="c6b9a-113">Nella finestra **Definisci nuovo gateway IP/PSTN** digitare il nome di dominio completo (FQDN) o l'indirizzo IP del peer e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-113">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="c6b9a-114">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="c6b9a-114">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6b9a-115">Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="c6b9a-116">Definire la modalità di attesa (IPv4 o IPv6) dell'indirizzo IP del nuovo gateway PSTN e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-116">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="c6b9a-117">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="c6b9a-117">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="c6b9a-118">Definire un *trunk radice* per il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-118">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="c6b9a-119">Un trunk è una connessione logica tra un Mediation Server e un gateway identificato in modo univoco dalla tupla.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-119">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="c6b9a-120">{FQDN Mediation Server, porta di attesa Mediation Server (TLS o TCP): IP e FQDN del gateway, porta di attesa del gateway}</span><span class="sxs-lookup"><span data-stu-id="c6b9a-120">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="c6b9a-121">Quando si definisce un gateway PSTN in Generatore di topologie, è necessario definire un trunk radice per aggiungere correttamente il gateway PSTN alla topologia.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-121">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="c6b9a-122">Il trunk radice non può essere rimosso se non si rimuove prima il gateway PSTN associato.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-122">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="c6b9a-123">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="c6b9a-123">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="c6b9a-124">In **porta di attesa per gateway IP/PSTN**Digitare la porta di attesa che il gateway, il sistema PBX o l'SBC utilizzerà per i messaggi SIP provenienti dal Mediation Server che verranno associati al trunk radice del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-124">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="c6b9a-125">Per impostazione predefinita, vengono utilizzate la porta 5066 per TCP (Transmission Control Protocol) e la porta 5067 per TLS (Transport Layer Security) in un gateway PSTN, un PBX o un sistema SBC.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-125">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="c6b9a-126">In un Survivable Branch Appliance in un sito di succursale, le porte predefinite sono 5081 per TCP e 5082 per TLS.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-126">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="c6b9a-127">In **Protocollo trasporto SIP** fare clic sul tipo di trasporto utilizzato dal peer e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-127">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6b9a-128">Per motivi di sicurezza, è consigliabile distribuire un peer al Mediation Server in grado di utilizzare TLS.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-128">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="c6b9a-129">In **Mediation Server associato**selezionare il pool di Mediation Server da associare al trunk radice di questo gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-129">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="c6b9a-130">In **porta Mediation Server associato**Digitare la porta di attesa che verrà utilizzata dal Mediation Server per i messaggi SIP provenienti dal gateway.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-130">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6b9a-131">Con il supporto di più trunk in Lync Server 2013, è possibile definire più porte di segnalazione SIP sul Mediation Server da utilizzare per la comunicazione con più gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="c6b9a-132">Quando si definisce un trunk, la <STRONG>porta del Mediation Server associata</STRONG> deve trovarsi all'interno dell'intervallo delle porte di attesa per il rispettivo protocollo consentito dal Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="c6b9a-133">Questo intervallo di porte è definito in Lync Server 2013 e Mediation pool.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-133">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="c6b9a-134">Fare clic con il pulsante destro del mouse sul pool di Mediation Server di interesse e scegliere <STRONG>modifica proprietà</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-134">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="c6b9a-135">Specificare l'intervallo di porte nel campo <STRONG>Porte di attesa</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="c6b9a-136">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-136">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c6b9a-137">Prima di completare questo passaggio, verificare che il peer definito sia in esecuzione e utilizzi l'FQDN o l'indirizzo IP specificato.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-137">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="c6b9a-138">Successivamente, per aggiungere il peer alla topologia, seguire le procedure illustrate in [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-138">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="c6b9a-139">È necessario pubblicare la topologia ogni volta che si utilizza Generatore di topologie per creare o modificare la topologia, in modo che i dati possano essere utilizzati per installare i file per i server che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6b9a-139">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6b9a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6b9a-140">See Also</span></span>


[<span data-ttu-id="c6b9a-141">Modificare un trunk in Generatore di topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6b9a-141">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

