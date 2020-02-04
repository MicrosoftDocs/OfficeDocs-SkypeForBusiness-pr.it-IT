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
ms.openlocfilehash: 63b5534b817477ea42dbefd5244c974fc70881f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a><span data-ttu-id="22632-102">Componenti di connettività PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22632-102">PSTN connectivity components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22632-103">_**Argomento Ultima modifica:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="22632-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="22632-104">Una soluzione VoIP di livello aziendale deve prevedere le chiamate da e verso la rete PSTN (Public Switched Telephone Network) senza alcun calo di qualità del servizio (QoS).</span><span class="sxs-lookup"><span data-stu-id="22632-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="22632-105">Inoltre, gli utenti non devono essere consapevoli della tecnologia sottostante quando effettuano e ricevono chiamate.</span><span class="sxs-lookup"><span data-stu-id="22632-105">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="22632-106">Dal punto di vista dell'utente, una chiamata tra l'infrastruttura VoIP aziendale e la rete PSTN dovrebbe sembrare solo un'altra sessione SIP.</span><span class="sxs-lookup"><span data-stu-id="22632-106">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>

<span data-ttu-id="22632-107">Per le connessioni PSTN, è possibile distribuire un trunk SIP o un gateway PSTN (con un PBX, noto anche come collegamento SIP diretto o senza PBX).</span><span class="sxs-lookup"><span data-stu-id="22632-107">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>

<div>

## <a name="sip-trunking"></a><span data-ttu-id="22632-108">Trunking SIP</span><span class="sxs-lookup"><span data-stu-id="22632-108">SIP Trunking</span></span>

<span data-ttu-id="22632-109">In alternativa all'uso di gateway PSTN, è possibile connettere la soluzione VoIP aziendale alla rete PSTN usando il trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="22632-109">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="22632-110">Il trunking SIP consente gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="22632-110">SIP trunking enables the following scenarios:</span></span>

  - <span data-ttu-id="22632-111">Un utente aziendale all'interno o all'esterno del firewall aziendale può effettuare una chiamata locale o interurbana specificata da un numero conforme E. 164 che viene terminato sulla rete PSTN come servizio del provider di servizi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="22632-111">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="22632-112">Qualsiasi abbonato PSTN può contattare un utente aziendale all'interno o all'esterno del firewall aziendale componendo un numero DID (Direct inwarded Dialing) associato all'utente aziendale.</span><span class="sxs-lookup"><span data-stu-id="22632-112">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>

<span data-ttu-id="22632-113">L'uso di questa soluzione di distribuzione richiede un provider di servizi di trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="22632-113">The use of this deployment solution requires a SIP trunking service provider.</span></span>

</div>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="22632-114">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="22632-114">PSTN gateways</span></span>

<span data-ttu-id="22632-115">I gateway PSTN sono dispositivi di terze parti che traducono segnali e elementi multimediali tra l'infrastruttura VoIP aziendale e una rete PSTN o PBX.</span><span class="sxs-lookup"><span data-stu-id="22632-115">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="22632-116">I gateway PSTN collaborano con il Mediation Server per presentare una chiamata PSTN o PBX a un client VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="22632-116">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="22632-117">Il Mediation Server presenta anche le chiamate dei client VoIP aziendale al gateway PSTN per il routing alla rete PSTN o PBX.</span><span class="sxs-lookup"><span data-stu-id="22632-117">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="22632-118">Per un elenco dei partner che collaborano con Microsoft per la fornitura di dispositivi compatibili con Lync Server, vedere il sito Web Microsoft Unified Communications [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)Partners.</span><span class="sxs-lookup"><span data-stu-id="22632-118">For a list of partners who work with Microsoft to provide devices that work with Lync Server, see the Microsoft Unified Communications Partners website at [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

<div>

## <a name="private-branch-exchanges"></a><span data-ttu-id="22632-119">Scambi di branch privati</span><span class="sxs-lookup"><span data-stu-id="22632-119">Private Branch Exchanges</span></span>

<span data-ttu-id="22632-120">Se si dispone di un'infrastruttura vocale esistente che usa un PBX (Private Branch Exchange), è possibile usare il PBX con Lync Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="22632-120">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Lync Server Enterprise Voice.</span></span>

<span data-ttu-id="22632-121">Gli scenari di integrazione Voice-PBX supportati di Enterprise sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="22632-121">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>

  - <span data-ttu-id="22632-122">IP-PBX che supporta il bypass multimediale, con un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="22632-122">IP-PBX that supports media bypass, with a Mediation Server.</span></span>

  - <span data-ttu-id="22632-123">IP-PBX che richiede un gateway PSTN autonomo.</span><span class="sxs-lookup"><span data-stu-id="22632-123">IP-PBX that requires a stand-alone PSTN gateway.</span></span>

  - <span data-ttu-id="22632-124">PBX TDM (Time Division Multiplexing) con un gateway PSTN autonomo.</span><span class="sxs-lookup"><span data-stu-id="22632-124">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22632-125">Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="22632-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="22632-126">Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="22632-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="22632-127">Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program-Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>at.</span><span class="sxs-lookup"><span data-stu-id="22632-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="22632-128">Per informazioni dettagliate sui partner che offrono soluzioni VoIP aziendale, vedere il sito Web Microsoft Unified Communications Partners [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span><span class="sxs-lookup"><span data-stu-id="22632-128">For details about partners who offer Enterprise Voice solutions, see the Microsoft Unified Communications Partners website at [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

<span data-ttu-id="22632-129">Per informazioni dettagliate sui partner che offrono soluzioni hardware VoIP aziendale, inclusi i gateway PSTN, vedere il sito Web [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)Microsoft Unified Communications Partners.</span><span class="sxs-lookup"><span data-stu-id="22632-129">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the Microsoft Unified Communications Partners website [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

