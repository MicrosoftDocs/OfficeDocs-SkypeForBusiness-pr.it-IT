---
title: 'Lync Server 2013: Configurare il bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8be022e5b1b16bff432873e27ddda5f388db02f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="e59d4-102">Configurare il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e59d4-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e59d4-103">_**Argomento Ultima modifica:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="e59d4-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="e59d4-104">In questa sezione si presuppone che sia già stato pubblicato e configurato almeno uno o più server di mediazione (come descritto in [definire un Mediation Server in Generatore di topologie in Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) e [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md)oppure in [definire e configurare un pool Front end o un server Standard Edition in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) e [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md), nella documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e59d4-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="e59d4-105">Questa sezione presuppone inoltre che sia stato definito almeno un peer del gateway per specificare la connettività PSTN, come descritto in [definire un gateway in Generatore di topologia in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e59d4-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="e59d4-106">Se il peer a cui si connette è il SBC di un provider di trunking SIP, verificare che il provider sia un provider qualificato e che il provider supporti il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="e59d4-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="e59d4-107">Ad esempio, molti provider di trunking SIP consentiranno solo a SBC di ricevere il traffico dal Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="e59d4-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="e59d4-108">In caso affermativo, l'esclusione non deve essere abilitata per il trunk in questione.</span><span class="sxs-lookup"><span data-stu-id="e59d4-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="e59d4-109">Non è inoltre possibile abilitare il bypass multimediale a meno che l'organizzazione non riveli gli indirizzi IP di rete interni al provider di trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="e59d4-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e59d4-110">Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="e59d4-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="e59d4-111">Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="e59d4-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="e59d4-112">Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program-Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>at.</span><span class="sxs-lookup"><span data-stu-id="e59d4-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="e59d4-113">Questa sezione descrive come abilitare il bypass multimediale per ridurre l'elaborazione necessaria per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="e59d4-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="e59d4-114">Prima di abilitare il bypass multimediale, verificare che l'ambiente soddisfi le condizioni necessarie per supportare il bypass multimediale, come descritto in [pianificazione per il bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e59d4-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="e59d4-115">Verificare inoltre di aver usato le informazioni in [pianificazione per il bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) per decidere se abilitare le impostazioni globali di bypass multimediale per ignorare sempre il Mediation Server o per usare le informazioni sul sito e le aree geografiche per determinare se ignorare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="e59d4-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="e59d4-116">Se è già stato configurato facoltativamente il controllo di ammissione alle chiamate (CAC), un'altra funzionalità di VoIP aziendale avanzata, si noti che la prenotazione di larghezza di banda eseguita tramite il controllo di ammissione delle chiamate non si applica alle chiamate per cui è impiegato il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="e59d4-116">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed.</span></span> <span data-ttu-id="e59d4-117">La verifica dell'uso del bypass multimediale viene eseguita per prima e, se il bypass multimediale viene impiegato, il controllo di ammissione delle chiamate non viene usato per la chiamata; solo se il controllo del bypass multimediale non riesce, viene eseguito il controllo per l'ammissione alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="e59d4-117">The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control.</span></span> <span data-ttu-id="e59d4-118">Le due caratteristiche si escludono quindi a vicenda per qualsiasi chiamata specifica indirizzata alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="e59d4-118">The two features are thus mutually exclusive for any particular call that is routed to the PSTN.</span></span> <span data-ttu-id="e59d4-119">Questa è la logica perché il bypass multimediale presuppone che i vincoli di larghezza di banda non esistano tra gli endpoint multimediali di una chiamata; il bypass multimediale non può essere eseguito sui collegamenti con larghezza di banda limitata.</span><span class="sxs-lookup"><span data-stu-id="e59d4-119">This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth.</span></span> <span data-ttu-id="e59d4-120">Di conseguenza, una delle operazioni seguenti verrà applicata a una chiamata PSTN: a) l'elemento multimediale ignora il Mediation Server e il controllo di ammissione delle chiamate non riserva la larghezza di banda per la chiamata; o b) il controllo dell'ammissione alle chiamate applica la prenotazione della larghezza di banda alla chiamata e il supporto viene elaborato dal Mediation Server coinvolto nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="e59d4-120">As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="e59d4-121">Passaggi successivi: abilitare il bypass multimediale nella connessione trunk</span><span class="sxs-lookup"><span data-stu-id="e59d4-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="e59d4-122">Dopo aver configurato le impostazioni iniziali per la connettività PSTN (dial plan, criteri vocali, record di utilizzo PSTN, route di chiamata in uscita e regole di traduzione), avviare il processo di abilitazione del bypass multimediale tramite la procedura descritta in [configurare un trunk con il bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="e59d4-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e59d4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e59d4-123">See Also</span></span>


[<span data-ttu-id="e59d4-124">Configurare un trunk con il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e59d4-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="e59d4-125">Configurare il bypass multimediale in Lync Server 2013 per ignorare sempre il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="e59d4-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="e59d4-126">Configurare le impostazioni globali di bypass multimediale in Lync Server 2013 per l'uso delle informazioni sul sito e sull'area geografica</span><span class="sxs-lookup"><span data-stu-id="e59d4-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="e59d4-127">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e59d4-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="e59d4-128">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e59d4-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

