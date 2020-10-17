---
title: 'Lync Server 2013: aggiungere un criterio percorso a un sito di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95ca625746fc38d8cab9c25701a8bf22718e71e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529573"
---
# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="e4cac-102">Aggiungere un criterio percorso a un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4cac-102">Add a location policy to a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4cac-103">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="e4cac-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="e4cac-104">Negli esempi seguenti viene illustrato come aggiungere il criterio percorso **Redmond** definito in [create location Policies in Lync Server 2013](lync-server-2013-create-location-policies.md) a un sito di rete esistente e come creare un nuovo sito di rete in cui viene utilizzato il criterio percorso **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="e4cac-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="e4cac-105">Per informazioni dettagliate sull'utilizzo dei siti di rete, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4cac-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="e4cac-106">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="e4cac-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="e4cac-107">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="e4cac-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="e4cac-108">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="e4cac-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="e4cac-109">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="e4cac-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="e4cac-110">Per assegnare un criterio percorso a un sito di rete esistente</span><span class="sxs-lookup"><span data-stu-id="e4cac-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="e4cac-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e4cac-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e4cac-112">Eseguire i cmdlet seguenti per modificare un sito di rete esistente.</span><span class="sxs-lookup"><span data-stu-id="e4cac-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="e4cac-113">Assegnare il criterio percorso con tag **Redmond** a un sito di rete esistente denominato **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="e4cac-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="e4cac-114">Per assegnare un criterio percorso a un nuovo sito di rete</span><span class="sxs-lookup"><span data-stu-id="e4cac-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="e4cac-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e4cac-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e4cac-116">Eseguire il cmdlet seguente per creare un nuovo sito di rete.</span><span class="sxs-lookup"><span data-stu-id="e4cac-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="e4cac-117">Creare un nuovo sito di rete nell'area di rete e assegnare il criterio percorso contrassegnato come **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="e4cac-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

