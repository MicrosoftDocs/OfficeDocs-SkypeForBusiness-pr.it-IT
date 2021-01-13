---
title: Definire un gateway in Generatore di topologie in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Riepilogo: informazioni su come definire un gateway PSTN in Generatore di topologie in Skype for Business Server.'
ms.openlocfilehash: be68c853cdcd530b05ad4b0949f722788e77d0df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837026"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="40623-103">Definire un gateway in Generatore di topologie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40623-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="40623-104">**Riepilogo:** Informazioni su come definire un gateway PSTN in Generatore di topologie in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="40623-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="40623-105">Eseguire la procedura seguente per utilizzare il generatore di topologie per definire un peer con cui è possibile associare un Mediation Server per fornire la connettività alla rete PSTN (Public Switched Telephone Network) per gli utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="40623-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="40623-106">Un peer per il Mediation Server può essere un gateway PSTN, un IP-PBX o un session border controller (SBC) per un provider di servizi di telefonia Internet (ITSP) a cui si effettua la connessione configurando un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="40623-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="40623-107">Per definire un peer per il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="40623-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="40623-108">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015** e quindi su **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="40623-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="40623-109">In Skype for Business Server, nome del sito, componenti condivisi, fare clic con il pulsante destro del mouse sul nodo **gateway PSTN** e quindi scegliere **nuovo gateway PSTN**.</span><span class="sxs-lookup"><span data-stu-id="40623-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="40623-110">Nella finestra **Definisci nuovo gateway IP/PSTN** digitare il nome di dominio completo (FQDN) o l'indirizzo IP del peer e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="40623-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40623-111">Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="40623-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="40623-112">Definire la modalità di attesa (IPv4 o IPv6) dell'indirizzo IP del nuovo gateway PSTN e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="40623-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="40623-113">Definire un trunk radice per il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="40623-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="40623-114">Un trunk è una connessione logica tra un Mediation Server e un gateway identificato in modo univoco dalla tupla.</span><span class="sxs-lookup"><span data-stu-id="40623-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="40623-115">{FQDN Mediation Server, porta di attesa Mediation Server (TLS o TCP): IP e FQDN del gateway, porta di attesa del gateway}</span><span class="sxs-lookup"><span data-stu-id="40623-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="40623-116">Quando si definisce un gateway PSTN in Generatore di topologie, è necessario definire un trunk radice per aggiungere correttamente il gateway PSTN alla topologia.</span><span class="sxs-lookup"><span data-stu-id="40623-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="40623-117">Il trunk radice non può essere rimosso se non si rimuove prima il gateway PSTN associato.</span><span class="sxs-lookup"><span data-stu-id="40623-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="40623-118">In **porta di attesa per gateway IP/PSTN** Digitare la porta di attesa che il gateway, il sistema PBX o l'SBC utilizzerà per i messaggi SIP provenienti dal Mediation Server che verranno associati al trunk radice del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="40623-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="40623-119">Per impostazione predefinita, vengono utilizzate la porta 5066 per TCP (Transmission Control Protocol) e la porta 5067 per TLS (Transport Layer Security) in un gateway PSTN, un PBX o un sistema SBC.</span><span class="sxs-lookup"><span data-stu-id="40623-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="40623-120">In un Survivable Branch Appliance in un sito di succursale, le porte predefinite sono 5081 per TCP e 5082 per TLS.</span><span class="sxs-lookup"><span data-stu-id="40623-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="40623-121">In **Protocollo trasporto SIP** fare clic sul tipo di trasporto utilizzato dal peer e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="40623-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40623-122">Per motivi di sicurezza, è consigliabile distribuire un peer al Mediation Server in grado di utilizzare TLS.</span><span class="sxs-lookup"><span data-stu-id="40623-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="40623-123">In **Mediation Server associato** selezionare il pool di Mediation Server da associare al trunk radice di questo gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="40623-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="40623-124">In **porta Mediation Server associato** Digitare la porta di attesa che verrà utilizzata dal Mediation Server per i messaggi SIP provenienti dal gateway.</span><span class="sxs-lookup"><span data-stu-id="40623-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40623-125">Con il supporto per più trunk in Skype for Business Server, è possibile definire più porte di segnalazione SIP sul Mediation Server per la comunicazione con più gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="40623-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="40623-126">Quando si definisce un trunk, la **porta del Mediation Server associata** deve trovarsi all'interno dell'intervallo delle porte di attesa per il rispettivo protocollo consentito dal Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="40623-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="40623-127">Questo intervallo di porte è definito in Skype for Business Server e Mediation pools.</span><span class="sxs-lookup"><span data-stu-id="40623-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="40623-128">Fare clic con il pulsante destro del mouse sul pool di Mediation Server di interesse e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="40623-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="40623-129">Specificare l'intervallo di porte nel campo **Porte di attesa**.</span><span class="sxs-lookup"><span data-stu-id="40623-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="40623-130">Verificare che il peer definito sia in esecuzione e che utilizzi il nome di dominio completo o l'indirizzo IP specificato.</span><span class="sxs-lookup"><span data-stu-id="40623-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="40623-131">Quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="40623-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="40623-132">Fare clic con il pulsante destro del mouse sul nodo **di Skype for Business Server** , quindi fare clic su **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="40623-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

