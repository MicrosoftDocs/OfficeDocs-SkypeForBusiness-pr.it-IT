---
title: 'Lync Server 2013: creare criteri di rete tra siti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6309b27ddedb37c2c38e7d40e74e427f61b904a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="ca01f-102">Creare criteri di intersito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca01f-102">Create network intersite policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca01f-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ca01f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ca01f-104">Un *criterio intersito di rete* definisce le limitazioni della larghezza di banda tra i siti con collegamenti WAN diretti tra di essi.</span><span class="sxs-lookup"><span data-stu-id="ca01f-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="ca01f-105">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca01f-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="ca01f-106">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ca01f-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="ca01f-107">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ca01f-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="ca01f-108">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ca01f-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="ca01f-109">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ca01f-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca01f-110">È necessario un criterio intersito di rete <EM>solo</EM> se esiste un collegamento incrociato diretto tra due siti di rete.</span><span class="sxs-lookup"><span data-stu-id="ca01f-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="ca01f-111">Nella topologia di esempio dell'area Nord America esiste un collegamento diretto tra i siti Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="ca01f-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="ca01f-112">Questi due siti richiedono un criterio intersito che applica un profilo dei criteri di larghezza di banda appropriato.</span><span class="sxs-lookup"><span data-stu-id="ca01f-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="ca01f-113">L'esempio seguente applica il profilo\_del collegamento 20MB.</span><span class="sxs-lookup"><span data-stu-id="ca01f-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="ca01f-114">Per creare un criterio intersito di rete</span><span class="sxs-lookup"><span data-stu-id="ca01f-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="ca01f-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ca01f-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ca01f-116">Eseguire il cmdlet New-CsNetworkInterSitePolicy per creare criteri di intersito di rete e applicare un profilo dei criteri di larghezza di banda appropriato per due siti che hanno un collegamento incrociato diretto.</span><span class="sxs-lookup"><span data-stu-id="ca01f-116">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="ca01f-117">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ca01f-117">For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="ca01f-118">Ripetere il passaggio 2 in base alle esigenze per creare criteri di intersito di rete per tutte le coppie di siti di rete con un collegamento incrociato diretto.</span><span class="sxs-lookup"><span data-stu-id="ca01f-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

