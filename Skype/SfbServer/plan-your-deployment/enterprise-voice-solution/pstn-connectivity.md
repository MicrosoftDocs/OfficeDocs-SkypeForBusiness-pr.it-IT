---
title: Componenti di connettività PSTN in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Informazioni sul trunking SIP e sui gateway PSTN per VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: 6261b95906699777e62c025889d23e03d381f09d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813536"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="1556d-103">Componenti di connettività PSTN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1556d-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="1556d-104">Informazioni sul trunking SIP e sui gateway PSTN per VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1556d-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="1556d-p101">Una soluzione VoIP di livello aziendale deve essere in grado di garantire le chiamate da e verso la rete PSTN (Public Switched Telephone Network) senza alcun decadimento della qualità del servizio (QoS). Gli utenti non devono inoltre preoccuparsi della tecnologia sottostante quando effettuano e ricevono chiamate. Dal punto di vista dell'utente, una chiamata tra l'infrastruttura VoIP aziendale e la rete PSTN deve risultare del tutto analoga a qualsiasi altra sessione SIP.</span><span class="sxs-lookup"><span data-stu-id="1556d-p101">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS). In addition, users should not be aware of the underlying technology when they place and receive calls. From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="1556d-108">Per le connessioni PSTN, è possibile distribuire un trunk SIP o un gateway PSTN (con un sistema PBX, noto anche come collegamento SIP diretto o senza PBX).</span><span class="sxs-lookup"><span data-stu-id="1556d-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="1556d-109">Trunking SIP</span><span class="sxs-lookup"><span data-stu-id="1556d-109">SIP Trunking</span></span>

<span data-ttu-id="1556d-p102">Come alternativa all'utilizzo di gateway PSTN, è possibile connettere la soluzione VoIP aziendale alla rete PSTN tramite trunking SIP. Il trunking SIP consente gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="1556d-p102">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking. SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="1556d-112">Un utente aziendale interno o esterno al firewall aziendale può effettuare una chiamata locale o interurbana tramite un numero compatibile con E.164, che viene terminata nella rete PSTN come servizio del provider di servizi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1556d-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="1556d-113">Qualsiasi sottoscrittore PSTN può contattare un utente aziendale interno o esterno al firewall aziendale componendo un numero DID (Direct Inward Dialing) associato a tale utente.</span><span class="sxs-lookup"><span data-stu-id="1556d-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="1556d-114">Per l'utilizzo di questa soluzione di distribuzione è necessario un provider di servizi di trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="1556d-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="1556d-115">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="1556d-115">PSTN gateways</span></span>

<span data-ttu-id="1556d-116">I gateway PSTN sono dispositivi di terze parti che convertono i segnali e i contenuti multimediali tra l'infrastruttura VoIP aziendale e una rete PSTN o un PBX.</span><span class="sxs-lookup"><span data-stu-id="1556d-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="1556d-117">I gateway PSTN operano con Mediation Server per presentare una chiamata PSTN o PBX a un client VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="1556d-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="1556d-118">Mediation Server presenta inoltre le chiamate da client VoIP aziendale al gateway PSTN per il routing alla rete PSTN o al PBX.</span><span class="sxs-lookup"><span data-stu-id="1556d-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="1556d-119">Per un elenco di partner che collaborano con Microsoft per fornire dispositivi che funzionano con Skype for Business Server, vedere  [il sito Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="1556d-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="1556d-120">Centralini</span><span class="sxs-lookup"><span data-stu-id="1556d-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="1556d-121">Se si dispone di un'infrastruttura vocale esistente che utilizza un sistema PBX (Private Branch Exchange), è possibile utilizzare il PBX con VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="1556d-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="1556d-122">Gli scenari di integrazione tra VoIP aziendale e PBX supportati sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="1556d-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="1556d-123">IP-PBX che supporta Media Bypass, con un server Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="1556d-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="1556d-124">IP-PBX che richiede un gateway PSTN autonomo.</span><span class="sxs-lookup"><span data-stu-id="1556d-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="1556d-125">PBX TDM (Time Division Multiplexing), con un gateway PSTN autonomo.</span><span class="sxs-lookup"><span data-stu-id="1556d-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1556d-126">Media Bypass non funziona con tutti i gateway PSTN, i sistemi IP-PBX e i servizi SBC.</span><span class="sxs-lookup"><span data-stu-id="1556d-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="1556d-127">Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco.</span><span class="sxs-lookup"><span data-stu-id="1556d-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="1556d-128">Il bypass multimediale è supportato solo con i prodotti e le versioni elencati nel [programma Unified Communications Open Interoperability Program-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span><span class="sxs-lookup"><span data-stu-id="1556d-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="1556d-129">Per informazioni dettagliate sui partner che offrono soluzioni VoIP aziendale, vedere il [sito Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="1556d-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="1556d-130">Per informazioni dettagliate sui partner che offrono soluzioni hardware VoIP aziendale, tra cui i gateway PSTN, vedere il [sito Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="1556d-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

