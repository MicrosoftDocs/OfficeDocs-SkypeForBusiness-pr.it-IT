---
title: 'Lync Server 2013: trunking SIP del sito di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b0e24a0260e6be0bea8d23158f07ffcffcb53cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="9052a-102">Trunking SIP del sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9052a-102">Branch site SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9052a-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9052a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9052a-104">In alcuni casi, potrebbe essere necessario implementare il trunking SIP distribuito in siti di succursale selezionati.</span><span class="sxs-lookup"><span data-stu-id="9052a-104">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="9052a-105">Per determinare se è necessario un trunk SIP per un sito di succursale, esaminare le informazioni in [come implementare il trunking SIP in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="9052a-105">To determine whether a SIP trunk is needed for a branch site, review the information in [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="9052a-106">Per informazioni dettagliate sulle opzioni di topologia supportate per la distribuzione di trunk SIP nei siti di succursale, vedere [soluzioni di resilienza dei siti di succursale in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="9052a-106">For details about the supported topology options for deploying SIP trunks in branch sites, see [Branch-site resiliency solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span></span>

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="9052a-107">Analisi dei requisiti di un trunk SIP per un sito di succursale di esempio</span><span class="sxs-lookup"><span data-stu-id="9052a-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="9052a-108">Quando si decide di distribuire un trunk SIP di un sito di succursale, è necessario eseguire un'analisi costi specifica del sito.</span><span class="sxs-lookup"><span data-stu-id="9052a-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="9052a-109">Ad esempio, un'organizzazione che dispone di un sito centrale a Redmond, Washington e di un sito di succursale di New York dovrebbe eseguire un'analisi per determinare se implementare un trunk SIP dal sito di New York a un provider di servizi locale.</span><span class="sxs-lookup"><span data-stu-id="9052a-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>

<span data-ttu-id="9052a-110">Per stabilire se l'implementazione nel sito di Roma di un trunk SIP distribuito è una soluzione conveniente, identificare i numeri DID (Direct Inward Dialing) che utilizzeranno il trunk SIP e quindi analizzare il numero di chiamate effettuate dal sito di Roma ad aree diverse da Milano.</span><span class="sxs-lookup"><span data-stu-id="9052a-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="9052a-111">È possibile disporre di una terminazione per il sito di succursale nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="9052a-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="9052a-112">Ad esempio, il sito centrale Redmond può ospitare numeri DID per il sito di succursale di New York.</span><span class="sxs-lookup"><span data-stu-id="9052a-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="9052a-113">Se il costo di implementazione di un trunk SIP distribuito è inferiore al costo di tali chiamate, è consigliabile implementare un trunk SIP nel sito di succursale di New York.</span><span class="sxs-lookup"><span data-stu-id="9052a-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span>

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="9052a-114">Altri requisiti per il trunk SIP di un sito di succursale</span><span class="sxs-lookup"><span data-stu-id="9052a-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="9052a-115">La scelta tra la distribuzione di un trunk SIP anziché di un gateway si basa sulla differenza tra i costi delle chiamate interurbane PSTN per ogni opzione.</span><span class="sxs-lookup"><span data-stu-id="9052a-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="9052a-116">Se si distribuisce un trunk SIP di un sito di succursale, è inoltre necessario determinare la resilienza e i requisiti di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="9052a-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="9052a-117">Se il collegamento tra il sito di succursale e il sito centrale è resiliente e dispone di larghezza di banda sufficiente, è possibile distribuire un trunk SIP o un gateway.</span><span class="sxs-lookup"><span data-stu-id="9052a-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="9052a-118">Non è necessario distribuire un Survivable Branch Appliance nel sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="9052a-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="9052a-119">Se il collegamento tra il sito di succursale e il sito centrale non è resiliente, distribuire un Survivable Branch Appliance o distribuire un Survivable Branch Server con un gateway o un trunk SIP nel sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="9052a-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

