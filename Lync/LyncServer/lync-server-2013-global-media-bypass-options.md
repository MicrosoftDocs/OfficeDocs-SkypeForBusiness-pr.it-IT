---
title: 'Lync Server 2013: opzioni di bypass multimediale globale'
description: 'Lync Server 2013: opzioni di bypass multimediale globale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e69a776c13171d74666a202108fa4b5c72e224d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554552"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="5257d-103">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5257d-103">Global media bypass options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5257d-104">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="5257d-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5257d-105">In questo argomento si presuppone che sia già stato configurato il bypass multimediale per qualsiasi trunk a un peer (un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un session border controller (SBC) su un provider di servizi di telefonia Internet per un sito o un servizio specifico per il quale si desidera ignorare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="5257d-105">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="5257d-106">Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer, è necessario abilitarlo globalmente.</span><span class="sxs-lookup"><span data-stu-id="5257d-106">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="5257d-107">Le impostazioni globali di bypass multimediale possono specificare che il bypass multimediale viene sempre tentato per le chiamate alla rete PSTN oppure che il bypass multimediale viene utilizzato utilizzando il mapping delle subnet ai siti di rete e alle aree di rete, analogamente a quanto avviene tramite il controllo di ammissione di chiamata, un'altra funzionalità avanzata vocale.</span><span class="sxs-lookup"><span data-stu-id="5257d-107">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="5257d-108">Quando il bypass multimediale e il controllo di ammissione di chiamata sono entrambi abilitati, vengono utilizzate automaticamente le informazioni relative all'area di rete, al sito di rete e alla subnet specificate per il controllo di ammissione di chiamata quando si determina se utilizzare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="5257d-108">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="5257d-109">Ciò significa che non è possibile specificare che il bypass multimediale venga sempre tentato per le chiamate alla rete PSTN quando è abilitato il controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5257d-109">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="5257d-110">In questo argomento viene descritto come utilizzare il pannello di controllo di Lync Server e Lync Server Management Shell insieme per configurare le impostazioni di bypass multimediale globale.</span><span class="sxs-lookup"><span data-stu-id="5257d-110">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5257d-111">Quando si utilizzano queste procedure per configurare il bypass multimediale, si presuppone che si disponga di una buona connettività tra i client e il peer Mediation Server, ad esempio un gateway PSTN, un sistema IP-PBX o un SBC (Session Border Controller) in un provider di trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="5257d-111">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="5257d-112">Se sono previsti limiti di larghezza di banda sul collegamento, non è possibile applicare il bypass multimediale alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="5257d-112">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="5257d-113">Il bypass multimediale non funziona con tutti i gateway PSTN, i sistemi IP-PBX e i Session Border Controller.</span><span class="sxs-lookup"><span data-stu-id="5257d-113">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="5257d-114">Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco.</span><span class="sxs-lookup"><span data-stu-id="5257d-114">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="5257d-115">Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="5257d-115">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="5257d-116">Passaggi successivi: scegliere le impostazioni di bypass multimediale globali</span><span class="sxs-lookup"><span data-stu-id="5257d-116">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="5257d-117">Dopo aver abilitato il bypass multimediale sulle connessioni trunk a un peer per siti o servizi specifici, utilizzare il contenuto indicato di seguito per eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5257d-117">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="5257d-118">Abilitare il bypass multimediale sempre, come descritto in [Configure Media Bypass in Lync server 2013 per ignorare sempre il](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="5257d-118">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="5257d-119">In alternativa, configurare il bypass multimediale per l'utilizzo delle informazioni sui siti e sulle aree geografiche, come descritto in [Configure Media Bypass Global Settings in Lync Server 2013 per l'utilizzo di informazioni sul sito e sulla regione](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span><span class="sxs-lookup"><span data-stu-id="5257d-119">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5257d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5257d-120">See Also</span></span>


[<span data-ttu-id="5257d-121">Configurare un trunk con bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5257d-121">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="5257d-122">Associare una subnet a un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5257d-122">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="5257d-123">Configurare il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5257d-123">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="5257d-124">Bypass multimediale e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5257d-124">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

