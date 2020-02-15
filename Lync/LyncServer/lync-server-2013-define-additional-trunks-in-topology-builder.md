---
title: 'Lync Server 2013: definire ulteriori trunk in Generatore di topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f88a292b11e617d1ae0d20f603ad53b2b2847e7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="52296-102">Definire ulteriori trunk in Generatore di topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52296-102">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52296-103">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="52296-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="52296-104">Eseguire la procedura seguente per utilizzare il generatore di topologie per definire un trunk aggiuntivo a cui è possibile associare un *peer* a un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="52296-104">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="52296-105">Un peer fornisce gli utenti abilitati per VoIP aziendale con connettività alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="52296-105">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="52296-106">Un peer può essere un gateway PSTN, un IP-PBX, o un SBC (Session Border Controller) per un provider di servizi di telefonia Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="52296-106">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="52296-107">Il trunk definisce la connessione tra il Mediation Server e il peer.</span><span class="sxs-lookup"><span data-stu-id="52296-107">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="52296-108">È possibile definire più trunk per Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="52296-108">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="52296-109">Un Mediation Server può essere associato a più peer.</span><span class="sxs-lookup"><span data-stu-id="52296-109">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="52296-110">Un trunk è una connessione logica tra un Mediation Server e un gateway identificato in modo univoco dalla tupla:</span><span class="sxs-lookup"><span data-stu-id="52296-110">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="52296-111">{FQDN Mediation Server, porta di attesa Mediation Server (TLS o TCP): IP e FQDN del gateway, porta di attesa del gateway}</span><span class="sxs-lookup"><span data-stu-id="52296-111">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52296-112">In questo argomento si presuppone che sia installato un gateway PSTN e un trunk radice con almeno un Mediation Server collocato o autonomo, come descritto in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">define a gateway in Generatore di topologie in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="52296-112">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="52296-113">In questo argomento si presuppone che sia stato configurato almeno un pool Front end o un server Standard Edition in almeno un sito centrale, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definire e configurare un pool Front end o un server Standard Edition in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="52296-113">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="52296-114">Per definire un ulteriore Trunk tra un Mediation Server e un peer gateway</span><span class="sxs-lookup"><span data-stu-id="52296-114">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="52296-115">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="52296-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="52296-116">In Lync Server 2013, nome del sito, **componenti condivisi**, fare clic con il pulsante destro del mouse sul nodo **Trunks** e quindi scegliere **nuovo trunk**.</span><span class="sxs-lookup"><span data-stu-id="52296-116">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="52296-117">![Schermata struttura file del generatore di topologie di Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Schermata struttura file del generatore di topologie di Lync Server")</span><span class="sxs-lookup"><span data-stu-id="52296-117">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="52296-118">In **Definisci nuovo trunk**, specificare un nome descrittivo per identificare in modo univoco il trunk.</span><span class="sxs-lookup"><span data-stu-id="52296-118">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="52296-119">Non è possibile definire due trunk con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="52296-119">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52296-120">Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="52296-120">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="52296-121">In **Gateway PSTN associato** selezionare il peer gateway PSTN da associare al trunk.</span><span class="sxs-lookup"><span data-stu-id="52296-121">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="52296-122">![Impostazioni delle proprietà per il peer gateway PSTN per trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Impostazioni delle proprietà per il peer gateway PSTN per trunk")</span><span class="sxs-lookup"><span data-stu-id="52296-122">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="52296-123">In **porta di attesa per gateway PSTN**Digitare la porta di attesa che il peer (gateway PSTN, IP-PBX o SBC) riceverà i messaggi SIP dal Mediation Server che deve essere associato a questo trunk.</span><span class="sxs-lookup"><span data-stu-id="52296-123">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="52296-124">Le porte predefinite per il peer sono 5066 per TCP (Transmission Control Protocol) e 5067 per TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="52296-124">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="52296-125">Le porte di Survivable Branch Appliance predefinite sono 5081 per TCP e 5082 per TLS.</span><span class="sxs-lookup"><span data-stu-id="52296-125">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="52296-126">In **Protocollo trasporto SIP** fare clic sul tipo di di trasporto utilizzato dal peer.</span><span class="sxs-lookup"><span data-stu-id="52296-126">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52296-127">Per motivi di sicurezza, è consigliabile distribuire un peer al Mediation Server in grado di utilizzare TLS.</span><span class="sxs-lookup"><span data-stu-id="52296-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="52296-128">In **Mediation Server associato**selezionare il pool di Mediation Server da associare al trunk radice di questo peer</span><span class="sxs-lookup"><span data-stu-id="52296-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="52296-129">In **porta Mediation Server associato**Digitare la porta di attesa che il Mediation Server riceverà messaggi SIP dal peer.</span><span class="sxs-lookup"><span data-stu-id="52296-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52296-130">Con il supporto per più trunk in Lync Server 2013, è possibile configurare due trunk con nomi trunk diversi con la stessa <STRONG>porta di Mediation Server associata</STRONG> e la <STRONG>porta di attesa per gateway IP/PSTN</STRONG></span><span class="sxs-lookup"><span data-stu-id="52296-130">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52296-131">Con il supporto di più trunk in Lync Server 2013, è possibile definire più porte di segnalazione SIP sul Mediation Server per la comunicazione con più peer.</span><span class="sxs-lookup"><span data-stu-id="52296-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="52296-132">Quando si definisce un trunk, il numero di <STRONG>porta del Mediation Server associato</STRONG> deve trovarsi all'interno dell'intervallo delle porte di attesa per il rispettivo protocollo consentito dal Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="52296-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="52296-133">Questo intervallo di porte è definito in Lync Server 2013 e nei pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="52296-133">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="52296-134">Fare clic con il pulsante destro del mouse sul pool di Mediation Server pertinente e scegliere <STRONG>modifica proprietà</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="52296-134">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="52296-135">Specificare l'intervallo di porte nel campo <STRONG>Porte di attesa</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="52296-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="52296-136">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="52296-136">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="52296-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52296-137">See Also</span></span>


[<span data-ttu-id="52296-138">Modificare un trunk in Generatore di topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52296-138">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

