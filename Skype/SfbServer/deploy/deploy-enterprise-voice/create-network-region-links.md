---
title: Creare collegamenti all'area di rete in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Creare o modificare collegamenti all'area di rete, che vengono usati dal controllo di ammissione delle chiamate vocali aziendali in Skype for Business Server.
ms.openlocfilehash: 2b2eb99fa59125c93d97b902b6fbaad122ffdcdf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233692"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="5b6f3-103">Creare collegamenti all'area di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5b6f3-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="5b6f3-104">Creare o modificare collegamenti all'area di rete, che vengono usati dal controllo di ammissione delle chiamate vocali aziendali in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="5b6f3-105">Le aree all'interno di una rete sono collegate tramite connettività WAN fisica.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="5b6f3-106">Un collegamento all'area di rete crea un collegamento tra due aree geografiche configurate per il controllo di ammissione alle chiamate (CAC) e imposta le limitazioni della larghezza di banda per il traffico audio e video tra queste aree.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="5b6f3-107">La topologia di esempio include un collegamento tra le aree Nord America e APAC e un collegamento tra le aree EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="5b6f3-108">Ognuno di questi collegamenti di area geografica è vincolato dalla larghezza di banda WAN, come descritto nella tabella informazioni sulla larghezza di banda del collegamento di area, ad [esempio: requisiti per la raccolta del controllo di ammissione di chiamata in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="5b6f3-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5b6f3-109">Per creare collegamenti all'area geografica di rete tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="5b6f3-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="5b6f3-110">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5b6f3-111">Eseguire il cmdlet New-CsNetworkRegionLink per creare i collegamenti all'area geografica e applicare i profili dei criteri di larghezza di banda appropriati.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="5b6f3-112">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="5b6f3-112">For example, run:</span></span>
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5b6f3-113">Per creare collegamenti all'area geografica di rete tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5b6f3-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="5b6f3-114">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="5b6f3-115">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="5b6f3-116">Fare clic sul pulsante di spostamento **collegamento area geografica** .</span><span class="sxs-lookup"><span data-stu-id="5b6f3-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="5b6f3-117">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-117">Click **New**.</span></span>
    
5. <span data-ttu-id="5b6f3-118">Nella pagina **New Region link** fare clic su **nome** e quindi digitare un nome per il collegamento all'area di rete.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="5b6f3-119">Fare clic su **area di rete #1**e quindi sull'area di rete nell'elenco che si desidera collegare all'area di rete #2.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="5b6f3-120">Fare clic su **area di rete #2**e quindi fare clic su un'area di rete nell'elenco che si vuole collegare a #1 dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="5b6f3-121">Facoltativamente, fare clic su **criteri di larghezza di banda**e quindi selezionare il profilo dei criteri di larghezza di banda che si vuole applicare al collegamento all'area di rete.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5b6f3-122">Applicare un criterio di larghezza di banda solo se il collegamento all'area di rete è vincolato dalla larghezza di banda e si vuole usare CAC per controllare il traffico multimediale sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="5b6f3-123">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="5b6f3-124">Per completare la creazione di collegamenti di area di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="5b6f3-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5b6f3-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b6f3-125">See also</span></span>

[<span data-ttu-id="5b6f3-126">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5b6f3-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="5b6f3-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5b6f3-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="5b6f3-128">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5b6f3-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="5b6f3-129">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5b6f3-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
