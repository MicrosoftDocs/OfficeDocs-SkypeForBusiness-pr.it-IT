---
title: 'Lync Server 2013: controllo di ammissione di chiamata in un trunk SIP'
description: 'Lync Server 2013: controllo di ammissione di chiamata in un trunk SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3667ef4608b221a1607b6bbe0d89d390cb1dd402
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563158"
---
# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="ea5d9-103">Controllo di ammissione di chiamata in un trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea5d9-103">Call admission control on a SIP trunk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea5d9-104">_**Ultimo argomento modificato:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="ea5d9-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="ea5d9-p101">Per distribuire il servizio Controllo di ammissione di chiamata in un trunk SIP, creare un sito di rete per rappresentare il provider di servizi di telefonia Internet (ITSP). Per applicare i valori dei criteri di larghezza di banda nel trunk SIP, creare criteri tra siti tra il sito di rete dell'organizzazione e il sito di rete creato per rappresentare l'ITSP.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-p101">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="ea5d9-107">Nella figura seguente è illustrato un esempio di distribuzione del servizio Controllo di ammissione di chiamata in un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-107">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="ea5d9-108">**Configurazione del servizio Controllo di ammissione di chiamata in un trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="ea5d9-108">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="ea5d9-109">![Diagramma del trunking SIP del controllo di ammissione di chiamata](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Diagramma del trunking SIP del controllo di ammissione di chiamata")</span><span class="sxs-lookup"><span data-stu-id="ea5d9-109">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="ea5d9-110">Per configurare il servizio Controllo di ammissione di chiamata in un trunk SIP, è necessario eseguire le operazioni seguenti durante la distribuzione del servizio:</span><span class="sxs-lookup"><span data-stu-id="ea5d9-110">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="ea5d9-111">Creare un sito di rete per rappresentare l'ITSP.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-111">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="ea5d9-112">Associare il sito di rete a un'area di rete appropriata e allocare una larghezza di banda pari a zero per audio e video per il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-112">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="ea5d9-113">Per ulteriori informazioni, vedere [Configure Network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-113">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea5d9-114">Per l'ITSP, questa configurazione del sito di rete non è funzionale.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-114">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="ea5d9-115">I valori dei criteri di larghezza di banda vengono effettivamente applicati nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-115">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="ea5d9-116">Creare un collegamento tra siti per il trunk SIP utilizzando i valori dei parametri rilevanti per il sito creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-116">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="ea5d9-117">Utilizzare, ad esempio, il nome del sito di rete dell'organizzazione come valore del parametro NetworkSiteID1 e il sito di rete dell'ITSP come valore del parametro NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-117">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="ea5d9-118">Per informazioni dettagliate, vedere [create Network intersite Policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-118">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="ea5d9-119">Vedere anche la documentazione di Lync Server Management Shell per il cmdlet New-CsNetworkInterSitePolicy.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-119">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="ea5d9-120">Ottenere l'indirizzo IP del punto di terminazione multimediale SBC (Session Border Controller) dall'ITSP.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-120">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="ea5d9-121">Aggiungere tale indirizzo IP con una subnet mask di 32 al sito di rete che rappresenta l'ITSP.</span><span class="sxs-lookup"><span data-stu-id="ea5d9-121">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="ea5d9-122">Per ulteriori informazioni, vedere [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="ea5d9-122">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

