---
title: 'Lync Server 2013: aggiungere un criterio di posizione a un sito di rete'
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
ms.openlocfilehash: bd5e0247ccdff82737c2ed7ed830b0a99b7da1f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="d2e27-102">Aggiungere un criterio di posizione a un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2e27-102">Add a location policy to a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2e27-103">_**Argomento Ultima modifica:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="d2e27-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="d2e27-104">Gli esempi seguenti illustrano come aggiungere i criteri di posizione di **Redmond** definiti nei [criteri di creazione della posizione in Lync Server 2013](lync-server-2013-create-location-policies.md) in un sito di rete esistente e come creare un nuovo sito di rete che usa il criterio di posizione **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="d2e27-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="d2e27-105">Per informazioni dettagliate sull'uso dei siti di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2e27-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="d2e27-106">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d2e27-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="d2e27-107">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d2e27-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="d2e27-108">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d2e27-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="d2e27-109">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d2e27-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="d2e27-110">Per assegnare un criterio di posizione a un sito di rete esistente</span><span class="sxs-lookup"><span data-stu-id="d2e27-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="d2e27-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2e27-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d2e27-112">Eseguire i cmdlet seguenti per modificare un sito di rete esistente.</span><span class="sxs-lookup"><span data-stu-id="d2e27-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="d2e27-113">Assegnare i criteri di posizione Tagged **Redmond** a un sito di rete esistente denominato **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="d2e27-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="d2e27-114">Per assegnare un criterio di posizione a un nuovo sito di rete</span><span class="sxs-lookup"><span data-stu-id="d2e27-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="d2e27-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2e27-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d2e27-116">Eseguire il cmdlet seguente per creare un nuovo sito di rete.</span><span class="sxs-lookup"><span data-stu-id="d2e27-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="d2e27-117">Creare un nuovo sito di rete nell'area di rete e assegnare il criterio di posizione Tagged **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="d2e27-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

