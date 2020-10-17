---
title: 'Lync Server 2013: componenti di connettività PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa82336ed96c61315da4c25a0152ba75d15d7b6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531743"
---
# <a name="pstn-connectivity-components-in-lync-server-2013"></a><span data-ttu-id="3d401-102">Componenti di connettività PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d401-102">PSTN connectivity components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d401-103">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="3d401-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="3d401-p101">Una soluzione VoIP di livello aziendale deve essere in grado di garantire le chiamate da e verso la rete PSTN (Public Switched Telephone Network) senza alcun decadimento della qualità del servizio (QoS). Gli utenti non devono inoltre preoccuparsi della tecnologia sottostante quando effettuano e ricevono chiamate. Dal punto di vista dell'utente, una chiamata tra l'infrastruttura VoIP aziendale e la rete PSTN deve risultare del tutto analoga a qualsiasi altra sessione SIP.</span><span class="sxs-lookup"><span data-stu-id="3d401-p101">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS). In addition, users should not be aware of the underlying technology when they place and receive calls. From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>

<span data-ttu-id="3d401-107">Per le connessioni PSTN, è possibile distribuire un trunk SIP o un gateway PSTN (con un sistema PBX, noto anche come collegamento SIP diretto o senza PBX).</span><span class="sxs-lookup"><span data-stu-id="3d401-107">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>

<div>

## <a name="sip-trunking"></a><span data-ttu-id="3d401-108">Trunking SIP</span><span class="sxs-lookup"><span data-stu-id="3d401-108">SIP Trunking</span></span>

<span data-ttu-id="3d401-p102">Come alternativa all'utilizzo di gateway PSTN, è possibile connettere la soluzione VoIP aziendale alla rete PSTN tramite trunking SIP. Il trunking SIP consente gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d401-p102">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking. SIP trunking enables the following scenarios:</span></span>

  - <span data-ttu-id="3d401-111">Un utente aziendale interno o esterno al firewall aziendale può effettuare una chiamata locale o interurbana tramite un numero compatibile con E.164, che viene terminata nella rete PSTN come servizio del provider di servizi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3d401-111">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="3d401-112">Qualsiasi sottoscrittore PSTN può contattare un utente aziendale interno o esterno al firewall aziendale componendo un numero DID (Direct Inward Dialing) associato a tale utente.</span><span class="sxs-lookup"><span data-stu-id="3d401-112">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>

<span data-ttu-id="3d401-113">Per l'utilizzo di questa soluzione di distribuzione è necessario un provider di servizi di trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="3d401-113">The use of this deployment solution requires a SIP trunking service provider.</span></span>

</div>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="3d401-114">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="3d401-114">PSTN gateways</span></span>

<span data-ttu-id="3d401-115">I gateway PSTN sono dispositivi di terze parti che convertono i segnali e i contenuti multimediali tra l'infrastruttura VoIP aziendale e una rete PSTN o un PBX.</span><span class="sxs-lookup"><span data-stu-id="3d401-115">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="3d401-116">I gateway PSTN operano con Mediation Server per presentare una chiamata PSTN o PBX a un client VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="3d401-116">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="3d401-117">Mediation Server presenta inoltre le chiamate da client VoIP aziendale al gateway PSTN per il routing alla rete PSTN o al PBX.</span><span class="sxs-lookup"><span data-stu-id="3d401-117">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="3d401-118">Per un elenco dei partner che collaborano con Microsoft per fornire dispositivi che funzionano con Lync Server, vedere il sito Web Microsoft Unified Communications Partners all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="3d401-118">For a list of partners who work with Microsoft to provide devices that work with Lync Server, see the Microsoft Unified Communications Partners website at [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

<div>

## <a name="private-branch-exchanges"></a><span data-ttu-id="3d401-119">Centralini</span><span class="sxs-lookup"><span data-stu-id="3d401-119">Private Branch Exchanges</span></span>

<span data-ttu-id="3d401-120">Se si dispone di un'infrastruttura vocale esistente che utilizza un sistema PBX (Private Branch Exchange), è possibile utilizzare il PBX con Lync Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="3d401-120">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Lync Server Enterprise Voice.</span></span>

<span data-ttu-id="3d401-121">Gli scenari di integrazione tra VoIP aziendale e PBX supportati sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d401-121">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>

  - <span data-ttu-id="3d401-122">IP-PBX che supporta Media Bypass, con un server Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="3d401-122">IP-PBX that supports media bypass, with a Mediation Server.</span></span>

  - <span data-ttu-id="3d401-123">IP-PBX che richiede un gateway PSTN autonomo.</span><span class="sxs-lookup"><span data-stu-id="3d401-123">IP-PBX that requires a stand-alone PSTN gateway.</span></span>

  - <span data-ttu-id="3d401-124">PBX TDM (Time Division Multiplexing), con un gateway PSTN autonomo.</span><span class="sxs-lookup"><span data-stu-id="3d401-124">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d401-125">Media Bypass non funziona con tutti i gateway PSTN, i sistemi IP-PBX e i servizi SBC.</span><span class="sxs-lookup"><span data-stu-id="3d401-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="3d401-126">Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco.</span><span class="sxs-lookup"><span data-stu-id="3d401-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="3d401-127">Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="3d401-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="3d401-128">Per informazioni dettagliate sui partner che offrono soluzioni VoIP aziendale, vedere il sito Web Microsoft Unified Communications Partners all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="3d401-128">For details about partners who offer Enterprise Voice solutions, see the Microsoft Unified Communications Partners website at [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

<span data-ttu-id="3d401-129">Per informazioni dettagliate sui partner che offrono soluzioni hardware VoIP aziendale, tra cui i gateway PSTN, vedere il sito Web Microsoft Unified Communications Partners [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="3d401-129">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the Microsoft Unified Communications Partners website [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

