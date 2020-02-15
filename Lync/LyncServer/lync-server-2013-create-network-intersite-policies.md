---
title: 'Lync Server 2013: creare criteri di rete tra siti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 072dcf4cbb8f04a2db3e4b930eeaf666a031e94e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="0b9c5-102">Creare criteri intersito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b9c5-102">Create network intersite policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b9c5-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0b9c5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0b9c5-104">Un *criterio intersito di rete* definisce limiti di larghezza di banda tra i siti collegati direttamente tramite WAN.</span><span class="sxs-lookup"><span data-stu-id="0b9c5-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="0b9c5-105">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b9c5-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="0b9c5-106">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="0b9c5-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="0b9c5-107">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="0b9c5-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="0b9c5-108">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="0b9c5-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="0b9c5-109">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="0b9c5-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0b9c5-110">Un criterio intersito di rete è necessario <EM>solo</EM> se è presente un collegamento incrociato diretto tra due siti di rete.</span><span class="sxs-lookup"><span data-stu-id="0b9c5-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="0b9c5-111">Nell'area Nord America della topologia di esempio esiste un collegamento diretto tra i siti Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="0b9c5-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="0b9c5-112">Questi due siti richiedono un criterio intersito che applica un profilo dei criteri di larghezza di banda appropriato.</span><span class="sxs-lookup"><span data-stu-id="0b9c5-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="0b9c5-113">Nell'esempio seguente viene applicato il\_profilo di collegamento di 20MB.</span><span class="sxs-lookup"><span data-stu-id="0b9c5-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="0b9c5-114">Per creare un criterio intersito di rete</span><span class="sxs-lookup"><span data-stu-id="0b9c5-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="0b9c5-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0b9c5-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0b9c5-p102">Eseguire il cmdlet New-CsNetworkInterSitePolicy per creare i criteri intersito di rete e applicare un profilo dei criteri di larghezza di banda appropriato per due siti con collegamento incrociato diretto. Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="0b9c5-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="0b9c5-118">Ripetere il passaggio 2 in base alle specifiche esigenze per creare i criteri intersito di rete per tutte le coppie di siti di rete con collegamento incrociato diretto.</span><span class="sxs-lookup"><span data-stu-id="0b9c5-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

