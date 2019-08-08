---
title: Definire un gateway in Generatore di topologie in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Riepilogo: informazioni su come definire un gateway PSTN in Generatore di topologie in Skype for Business Server.'
ms.openlocfilehash: 322c526c87c3a354f11fd0c906256b36e6df526e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233532"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="9ca7f-103">Definire un gateway in Generatore di topologie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9ca7f-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="9ca7f-104">**Riepilogo:** Informazioni su come definire un gateway PSTN in Generatore di topologie in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="9ca7f-105">Seguire questa procedura per usare generatore di topologia per definire un peer con cui è possibile associare un Mediation Server per consentire la connettività alla rete PSTN (Public Switched Telephone Network) per gli utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="9ca7f-106">Un peer per il Mediation Server può essere un gateway PSTN, un IP-PBX o un SBC (Session Border Controller) per un provider di servizi di telefonia Internet (ITSP) a cui ci si connette configurando un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="9ca7f-107">Per definire un peer per il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="9ca7f-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="9ca7f-108">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi su **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="9ca7f-109">In Skype for Business Server, il nome del sito, i componenti condivisi, fare clic con il pulsante destro del mouse sul nodo **gateway PSTN** e quindi scegliere **nuovo gateway PSTN**.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="9ca7f-110">In **Definisci nuovo gateway IP/PSTN**Digitare il nome di dominio completo (FQDN) o l'indirizzo IP del peer e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9ca7f-111">Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="9ca7f-112">Definire la modalità di ascolto (IPv4 o IPv6) dell'indirizzo IP del nuovo gateway PSTN e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="9ca7f-113">Definire un trunk radice per il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="9ca7f-114">Un trunk è una connessione logica tra un Mediation Server e un gateway identificato in modo univoco dalla tupla.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="9ca7f-115">{Nome completo di Mediation Server, porta di attesa di Mediation Server (TLS o TCP): IP gateway e FQDN, porta di ascolto del gateway}</span><span class="sxs-lookup"><span data-stu-id="9ca7f-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="9ca7f-116">Quando si definisce un gateway PSTN in Generatore di topologie, è necessario definire un trunk radice per aggiungere correttamente il gateway PSTN alla topologia.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="9ca7f-117">Il trunk radice non può essere rimosso finché non viene rimosso il gateway PSTN associato.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="9ca7f-118">In **porta di ascolto per gateway IP/PSTN**Digitare la porta di attesa che il gateway, il PBX o il SBC utilizzerà per i messaggi SIP provenienti dal server di mediazione che verranno associati al trunk radice del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="9ca7f-119">Per impostazione predefinita, le porte sono 5066 per TCP (Transmission Control Protocol) e 5067 per Transport Layer Security (TLS) in un gateway PSTN, un PBX o un SBC.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="9ca7f-120">In un Survivable Branch Appliance in un sito di succursale, le porte predefinite sono 5081 per TCP e 5082 per TLS.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="9ca7f-121">In **protocollo di trasporto SIP**fare clic sul tipo di trasporto usato dal peer e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9ca7f-122">Per motivi di sicurezza, ti consigliamo vivamente di distribuire un peer al Mediation Server che può usare TLS.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="9ca7f-123">In **Mediation Server associato**selezionare il pool di Mediation Server da associare al trunk radice di questo gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="9ca7f-124">In **porta Mediation Server associata**Digitare la porta di ascolto che il server di mediazione userà per i messaggi SIP dal gateway.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9ca7f-125">Con il supporto per più trunk in Skype for Business Server, puoi definire più porte di segnalazione SIP nel Mediation Server per la comunicazione con più gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="9ca7f-126">Quando si definisce un trunk, la **porta del server di mediazione associata** deve essere compresa nell'intervallo delle porte in attesa per il rispettivo protocollo consentito dal server Mediation.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="9ca7f-127">Questo intervallo di porte è definito in Skype for Business Server e nei pool di mediazione.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="9ca7f-128">Fare clic con il pulsante destro del mouse sul pool di Mediation Server di interesse e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="9ca7f-129">Specificare l'intervallo di porte nel campo **porte in attesa** .</span><span class="sxs-lookup"><span data-stu-id="9ca7f-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="9ca7f-130">Verificare che il peer definito sia in uso e che usi il nome di dominio completo o l'indirizzo IP specificato.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="9ca7f-131">Quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="9ca7f-132">Fare clic con il pulsante destro del mouse sul nodo **di Skype for Business Server** e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="9ca7f-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

