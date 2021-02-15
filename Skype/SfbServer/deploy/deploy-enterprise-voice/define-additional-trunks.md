---
title: Definire trunk aggiuntivi in Generatore di topologie in Skype for Business Server
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Riepilogo: informazioni su come definire un trunk aggiuntivo tra un Mediation Server e un peer gateway in Generatore di topologie in Skype for Business Server.'
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836996"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="def00-103">Definire trunk aggiuntivi in Generatore di topologie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="def00-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="def00-104">**Riepilogo:** Informazioni su come definire un trunk aggiuntivo tra un Mediation Server e un peer gateway in Generatore di topologie in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="def00-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="def00-105">Eseguire la procedura seguente per definire un trunk aggiuntivo a cui è possibile associare un peer a un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="def00-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="def00-106">Un peer fornisce agli utenti abilitati VoIP aziendale la connettività alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="def00-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="def00-107">Un peer può essere un gateway PSTN, un IP-PBX, o un SBC (Session Border Controller) per un provider di servizi di telefonia Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="def00-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="def00-108">Un trunk è una connessione logica tra un Mediation Server e un gateway.</span><span class="sxs-lookup"><span data-stu-id="def00-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="def00-109">In questo argomento si presuppone che sia stato configurato un gateway PSTN e un trunk radice con almeno un Mediation Server o un pool autonomo collocato, come descritto [in Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="def00-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="def00-110">Per definire un trunk aggiuntivo tra un Mediation Server e un peer gateway</span><span class="sxs-lookup"><span data-stu-id="def00-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="def00-111">Avviare Generatore di topologie: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server 2015** e quindi **Skype for Business Server 2015 Generatore** di topologie.</span><span class="sxs-lookup"><span data-stu-id="def00-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="def00-112">In Skype for Business Server, il nome del sito, **Componenti condivisi,** fare clic con il pulsante destro del mouse sul nodo **Trunk e** quindi scegliere **Nuovo trunk.**</span><span class="sxs-lookup"><span data-stu-id="def00-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="def00-113">In **Definisci nuovo trunk**, specificare un nome descrittivo per identificare in modo univoco il trunk.</span><span class="sxs-lookup"><span data-stu-id="def00-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="def00-114">Non è possibile definire due trunk con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="def00-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="def00-115">Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="def00-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="def00-116">In **Gateway PSTN associato** selezionare il peer gateway PSTN da associare al trunk.</span><span class="sxs-lookup"><span data-stu-id="def00-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="def00-117">In Porta di attesa per **gateway PSTN** digitare la porta di attesa che il peer (gateway PSTN, IP-PBX o SBC) riceverà i messaggi SIP dal Mediation Server da associare a questo trunk.</span><span class="sxs-lookup"><span data-stu-id="def00-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="def00-118">Le porte predefinite per il peer sono 5066 per TCP (Transmission Control Protocol) e 5067 per TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="def00-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="def00-119">Le porte predefinite del Survivable Branch Appliance sono 5081 per TCP e 5082 per TLS.</span><span class="sxs-lookup"><span data-stu-id="def00-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="def00-120">In **Protocollo trasporto SIP** fare clic sul tipo di di trasporto utilizzato dal peer.</span><span class="sxs-lookup"><span data-stu-id="def00-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="def00-121">Per motivi di sicurezza, è consigliabile distribuire un peer nel Mediation Server in grado di utilizzare TLS.</span><span class="sxs-lookup"><span data-stu-id="def00-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="def00-122">In **Mediation Server associato** selezionare il pool Mediation Server da associare al trunk radice del peer</span><span class="sxs-lookup"><span data-stu-id="def00-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="def00-123">In **Porta Mediation Server associata** digitare la porta di attesa che il Mediation Server riceverà i messaggi SIP dal peer.</span><span class="sxs-lookup"><span data-stu-id="def00-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="def00-124">Con il supporto di più trunk in Skype for Business Server, non è possibile configurare due trunk con nomi trunk diversi con la stessa porta **Mediation Server** associata e la stessa porta di attesa per il **gateway IP/PSTN**</span><span class="sxs-lookup"><span data-stu-id="def00-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="def00-125">Con il supporto di più trunk in Skype for Business Server, è possibile definire più porte di segnalazione SIP nel Mediation Server per la comunicazione con più peer.</span><span class="sxs-lookup"><span data-stu-id="def00-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="def00-126">Quando si definisce un trunk, il numero di porta **del Mediation Server** associato deve essere compreso nell'intervallo delle porte di attesa per il rispettivo protocollo consentito dal Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="def00-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="def00-127">Questo intervallo di porte è definito in pool di Skype for Business Server e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="def00-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="def00-128">Fare clic con il pulsante destro del mouse sul pool Mediation Server pertinente e **scegliere Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="def00-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="def00-129">Specificare l'intervallo di porte nel campo **Porte di attesa**.</span><span class="sxs-lookup"><span data-stu-id="def00-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="def00-130">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="def00-130">Click **OK**.</span></span> 
    

