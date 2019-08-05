---
title: Componenti di connettività PSTN in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Informazioni sul trunking SIP e i gateway PSTN per VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: 6d11ea3204c9b924c9e700194ee04beb9a0df56c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187571"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="01298-103">Componenti di connettività PSTN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="01298-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="01298-104">Informazioni sul trunking SIP e i gateway PSTN per VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="01298-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="01298-105">Una soluzione VoIP di livello aziendale deve prevedere le chiamate da e verso la rete PSTN (Public Switched Telephone Network) senza alcun calo di qualità del servizio (QoS).</span><span class="sxs-lookup"><span data-stu-id="01298-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="01298-106">Inoltre, gli utenti non devono essere consapevoli della tecnologia sottostante quando effettuano e ricevono chiamate.</span><span class="sxs-lookup"><span data-stu-id="01298-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="01298-107">Dal punto di vista dell'utente, una chiamata tra l'infrastruttura VoIP aziendale e la rete PSTN dovrebbe sembrare solo un'altra sessione SIP.</span><span class="sxs-lookup"><span data-stu-id="01298-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="01298-108">Per le connessioni PSTN, è possibile distribuire un trunk SIP o un gateway PSTN (con un PBX, noto anche come collegamento SIP diretto o senza PBX).</span><span class="sxs-lookup"><span data-stu-id="01298-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="01298-109">Trunking SIP</span><span class="sxs-lookup"><span data-stu-id="01298-109">SIP Trunking</span></span>

<span data-ttu-id="01298-110">In alternativa all'uso di gateway PSTN, è possibile connettere la soluzione VoIP aziendale alla rete PSTN usando il trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="01298-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="01298-111">Il trunking SIP consente gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="01298-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="01298-112">Un utente aziendale all'interno o all'esterno del firewall aziendale può effettuare una chiamata locale o interurbana specificata da un numero conforme E. 164 che viene terminato sulla rete PSTN come servizio del provider di servizi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="01298-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="01298-113">Qualsiasi abbonato PSTN può contattare un utente aziendale all'interno o all'esterno del firewall aziendale componendo un numero DID (Direct inwarded Dialing) associato all'utente aziendale.</span><span class="sxs-lookup"><span data-stu-id="01298-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="01298-114">L'uso di questa soluzione di distribuzione richiede un provider di servizi di trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="01298-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="01298-115">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="01298-115">PSTN gateways</span></span>

<span data-ttu-id="01298-116">I gateway PSTN sono dispositivi di terze parti che traducono segnali e elementi multimediali tra l'infrastruttura VoIP aziendale e una rete PSTN o PBX.</span><span class="sxs-lookup"><span data-stu-id="01298-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="01298-117">I gateway PSTN collaborano con il Mediation Server per presentare una chiamata PSTN o PBX a un client VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="01298-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="01298-118">Il Mediation Server presenta anche le chiamate dei client VoIP aziendale al gateway PSTN per il routing alla rete PSTN o PBX.</span><span class="sxs-lookup"><span data-stu-id="01298-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="01298-119">Per un elenco dei partner che collaborano con Microsoft per la fornitura di dispositivi compatibili con Skype for Business Server, vedere [il sito Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="01298-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="01298-120">Scambi di branch privati</span><span class="sxs-lookup"><span data-stu-id="01298-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="01298-121">Se si ha un'infrastruttura vocale esistente che usa un PBX (Private Branch Exchange), è possibile usare il PBX con VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="01298-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="01298-122">Gli scenari di integrazione Voice-PBX supportati di Enterprise sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="01298-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="01298-123">IP-PBX che supporta il bypass multimediale, con un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="01298-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="01298-124">IP-PBX che richiede un gateway PSTN autonomo.</span><span class="sxs-lookup"><span data-stu-id="01298-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="01298-125">PBX TDM (Time Division Multiplexing) con un gateway PSTN autonomo.</span><span class="sxs-lookup"><span data-stu-id="01298-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="01298-126">Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="01298-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="01298-127">Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="01298-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="01298-128">Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in [Unified Communications Open Interoperability Program-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span><span class="sxs-lookup"><span data-stu-id="01298-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="01298-129">Per informazioni dettagliate sui partner che offrono soluzioni VoIP aziendale, vedere il [sito Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="01298-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="01298-130">Per informazioni dettagliate sui partner che offrono soluzioni hardware VoIP aziendale, inclusi i gateway PSTN, vedere il [sito Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="01298-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

