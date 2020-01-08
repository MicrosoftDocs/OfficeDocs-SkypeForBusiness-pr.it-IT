---
title: 'Lync Server 2013: Controllo di ammissione di chiamata in un trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36734aa67e350b6c6f5ea5e9da57ce47f57e3d46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="3f07c-102">Controllo di ammissione di chiamata in un trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f07c-102">Call admission control on a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f07c-103">_**Argomento Ultima modifica:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="3f07c-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="3f07c-104">Per distribuire il controllo di ammissione di chiamata (CAC) in un trunk SIP, è possibile creare un sito di rete per rappresentare il provider del servizio di telefonia Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="3f07c-104">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP).</span></span> <span data-ttu-id="3f07c-105">Per applicare i valori dei criteri di larghezza di banda nel trunk SIP, è possibile creare un criterio tra siti tra il sito di rete dell'organizzazione e il sito di rete creato per rappresentare il ITSP.</span><span class="sxs-lookup"><span data-stu-id="3f07c-105">To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="3f07c-106">La figura seguente mostra un esempio di distribuzione di CAC in un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="3f07c-106">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="3f07c-107">**Configurazione di CAC in un trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="3f07c-107">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="3f07c-108">![Controllo dell'ammissione alle chiamate schema del trunking SIP](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "controllo di ammissione di chiamata")</span><span class="sxs-lookup"><span data-stu-id="3f07c-108">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="3f07c-109">Per configurare CAC in un trunk SIP, sarà necessario eseguire le attività seguenti durante la distribuzione di CAC:</span><span class="sxs-lookup"><span data-stu-id="3f07c-109">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="3f07c-110">Creare un sito di rete per rappresentare il ITSP.</span><span class="sxs-lookup"><span data-stu-id="3f07c-110">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="3f07c-111">Associa il sito di rete a un'area di rete appropriata e assegna la larghezza di banda pari a zero per l'audio e il video per questo sito di rete.</span><span class="sxs-lookup"><span data-stu-id="3f07c-111">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="3f07c-112">Per informazioni dettagliate, vedere [configurare i siti di rete per CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3f07c-112">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f07c-113">Per ITSP, questa configurazione del sito di rete non è funzionale.</span><span class="sxs-lookup"><span data-stu-id="3f07c-113">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="3f07c-114">I valori dei criteri di larghezza di banda vengono effettivamente applicati nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="3f07c-114">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="3f07c-115">Creare un collegamento tra siti per il trunk SIP usando i valori di parametro rilevanti per il sito creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="3f07c-115">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="3f07c-116">Ad esempio, usa il nome del sito di rete nell'organizzazione come valore del parametro NetworkSiteID1 e il sito di rete ITSP come valore del parametro NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="3f07c-116">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="3f07c-117">Per informazioni dettagliate, vedere [creare criteri di intersito di rete in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3f07c-117">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="3f07c-118">Vedere anche la documentazione di Lync Server Management Shell per il cmdlet New-CsNetworkInterSitePolicy.</span><span class="sxs-lookup"><span data-stu-id="3f07c-118">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="3f07c-119">Ottenere l'indirizzo IP del punto di terminazione multimediale della sessione (SCB) del controller di bordo del ITSP.</span><span class="sxs-lookup"><span data-stu-id="3f07c-119">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="3f07c-120">Aggiungere l'indirizzo IP con una subnet mask di 32 al sito di rete che rappresenta il ITSP.</span><span class="sxs-lookup"><span data-stu-id="3f07c-120">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="3f07c-121">Per informazioni dettagliate, vedere [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="3f07c-121">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

