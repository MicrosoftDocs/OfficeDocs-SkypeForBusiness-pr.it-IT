---
title: 'Lync Server 2013: definire un gateway in Generatore di topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c9e57ad4e3d8c1692731bcfd4a56dc5c3d05bda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="922bc-102">Definire un gateway in Generatore di topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922bc-102">Define a gateway in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="922bc-103">_**Argomento Ultima modifica:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="922bc-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="922bc-104">Seguire questa procedura per usare generatore di topologia per definire un *peer* con cui è possibile associare un Mediation Server per consentire la connettività alla rete PSTN (Public Switched Telephone Network) per gli utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="922bc-104">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="922bc-105">Un peer per il Mediation Server può essere un gateway PSTN, un IP-PBX o un SBC (Session Border Controller) per un provider di servizi di telefonia Internet (ITSP) a cui ci si connette configurando un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="922bc-105">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="922bc-106">Questo argomento presuppone che sia stato configurato almeno un pool Front-End interno o un server Standard Edition in almeno un sito centrale con un Mediation Server collocato o autonomo, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definire e configurare un pool Front-end o un server Standard Edition in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="922bc-106">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="922bc-107">Questo argomento presuppone inoltre che l'infrastruttura soddisfi i prerequisiti descritti in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">prerequisiti software per VoIP aziendale in Lync server 2013</A> e <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">prerequisiti per la sicurezza e la configurazione di VoIP aziendale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="922bc-107">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="922bc-108">Per definire un peer per il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="922bc-108">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="922bc-109">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="922bc-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="922bc-110">In Lync Server 2013, il nome del sito, i componenti condivisi, fare clic con il pulsante destro del mouse sul nodo **gateway PSTN** e quindi scegliere **nuovo gateway PSTN**.</span><span class="sxs-lookup"><span data-stu-id="922bc-110">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="922bc-111">![d898c3c1-8798-4b74-8F02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8F02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="922bc-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="922bc-112">In **Definisci nuovo gateway IP/PSTN**Digitare il nome di dominio completo (FQDN) o l'indirizzo IP del peer e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="922bc-112">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="922bc-113">![8017ba5e-41bc-48D4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48D4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="922bc-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="922bc-114">Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="922bc-114">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="922bc-115">Definire la modalità di ascolto (IPv4 o IPv6) dell'indirizzo IP del nuovo gateway PSTN e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="922bc-115">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="922bc-116">![c7fc0d12-adc8-45A7-ACA1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45A7-ACA1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="922bc-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="922bc-117">Definire un *trunk radice* per il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="922bc-117">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="922bc-118">Un trunk è una connessione logica tra un Mediation Server e un gateway identificato in modo univoco dalla tupla.</span><span class="sxs-lookup"><span data-stu-id="922bc-118">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="922bc-119">{Nome completo di Mediation Server, porta di attesa di Mediation Server (TLS o TCP): IP gateway e FQDN, porta di ascolto del gateway}</span><span class="sxs-lookup"><span data-stu-id="922bc-119">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="922bc-120">Quando si definisce un gateway PSTN in Generatore di topologie, è necessario definire un trunk radice per aggiungere correttamente il gateway PSTN alla topologia.</span><span class="sxs-lookup"><span data-stu-id="922bc-120">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="922bc-121">Il trunk radice non può essere rimosso finché non viene rimosso il gateway PSTN associato.</span><span class="sxs-lookup"><span data-stu-id="922bc-121">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="922bc-122">![3b030757-EB35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-EB35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="922bc-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="922bc-123">In **porta di ascolto per gateway IP/PSTN**Digitare la porta di attesa che il gateway, il PBX o il SBC utilizzerà per i messaggi SIP provenienti dal server di mediazione che verranno associati al trunk radice del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="922bc-123">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="922bc-124">Per impostazione predefinita, le porte sono 5066 per TCP (Transmission Control Protocol) e 5067 per Transport Layer Security (TLS) in un gateway PSTN, un PBX o un SBC.</span><span class="sxs-lookup"><span data-stu-id="922bc-124">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="922bc-125">In un Survivable Branch Appliance in un sito di succursale, le porte predefinite sono 5081 per TCP e 5082 per TLS.</span><span class="sxs-lookup"><span data-stu-id="922bc-125">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="922bc-126">In **protocollo di trasporto SIP**fare clic sul tipo di trasporto usato dal peer e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="922bc-126">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="922bc-127">Per motivi di sicurezza, ti consigliamo vivamente di distribuire un peer al Mediation Server che può usare TLS.</span><span class="sxs-lookup"><span data-stu-id="922bc-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="922bc-128">In **Mediation Server associato**selezionare il pool di Mediation Server da associare al trunk radice di questo gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="922bc-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="922bc-129">In **porta Mediation Server associata**Digitare la porta di ascolto che il server di mediazione userà per i messaggi SIP dal gateway.</span><span class="sxs-lookup"><span data-stu-id="922bc-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="922bc-130">Con il supporto di più trunk in Lync Server 2013, è possibile definire più porte di segnalazione SIP nel server Mediation da usare per la comunicazione con più gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="922bc-130">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="922bc-131">Quando si definisce un trunk, la <STRONG>porta del server di mediazione associata</STRONG> deve essere compresa nell'intervallo delle porte in attesa per il rispettivo protocollo consentito dal server Mediation.</span><span class="sxs-lookup"><span data-stu-id="922bc-131">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="922bc-132">Questo intervallo di porte è definito in Lync Server 2013 e nei pool di mediazione.</span><span class="sxs-lookup"><span data-stu-id="922bc-132">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="922bc-133">Fare clic con il pulsante destro del mouse sul pool di Mediation Server di interesse e scegliere <STRONG>modifica proprietà</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="922bc-133">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="922bc-134">Specificare l'intervallo di porte nel campo <STRONG>porte in attesa</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="922bc-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="922bc-135">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="922bc-135">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="922bc-136">Prima di completare questo passaggio, assicurarsi che il peer definito sia in uso e usare il nome di dominio completo o l'indirizzo IP specificato.</span><span class="sxs-lookup"><span data-stu-id="922bc-136">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="922bc-137">Per aggiungere quindi il peer alla topologia, seguire le procedure descritte in [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="922bc-137">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="922bc-138">È necessario pubblicare la topologia ogni volta che si usa generatore di topologia per compilare o modificare la topologia, in modo che i dati possano essere usati per installare i file per i server che esegue Lync Server.</span><span class="sxs-lookup"><span data-stu-id="922bc-138">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="922bc-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="922bc-139">See Also</span></span>


[<span data-ttu-id="922bc-140">Modificare un trunk in Generatore di topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922bc-140">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

