---
title: Creare collegamenti area di rete in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Creare o modificare i collegamenti delle aree di rete, utilizzati dal controllo di ammissione di chiamata VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: 1b891a299e85836e4a69b4a6c6e9df9a52cb0cdc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822466"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="0f5ee-103">Creare collegamenti area di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f5ee-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="0f5ee-104">Creare o modificare i collegamenti delle aree di rete, utilizzati dal controllo di ammissione di chiamata VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="0f5ee-105">Le aree all'interno di una rete sono collegate tramite connettività fisica WAN.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="0f5ee-106">Un collegamento area di rete crea un collegamento tra due aree configurate per il controllo di ammissione di chiamata e imposta le limitazioni della larghezza di banda per il traffico audio e video tra queste aree.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="0f5ee-107">Nella topologia di esempio è presente un collegamento tra il Nord America e le aree APAC e un collegamento tra le aree EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="0f5ee-108">Ognuno di questi collegamenti tra aree geografiche è vincolato dalla larghezza di banda della WAN, come descritto nella tabella informazioni sulla larghezza di banda del collegamento regionale, ad [esempio: raccolta dei requisiti per il controllo di ammissione di chiamata in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="0f5ee-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0f5ee-109">Per creare collegamenti area di rete utilizzando Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="0f5ee-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="0f5ee-110">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="0f5ee-111">Eseguire il cmdlet New-CsNetworkRegionLink per creare i collegamenti area di rete e applicare i profili di criteri di larghezza di banda appropriati.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="0f5ee-112">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="0f5ee-112">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0f5ee-113">Per creare collegamenti area di rete utilizzando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f5ee-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0f5ee-114">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="0f5ee-115">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="0f5ee-116">Fare clic sul pulsante di spostamento **Collegamento area**.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="0f5ee-117">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-117">Click **New**.</span></span>
    
5. <span data-ttu-id="0f5ee-118">Nella pagina **Nuovo collegamento area di rete** fare clic su **Nome** e quindi digitare un nome per il collegamento area di rete.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="0f5ee-119">Fare clic su **Area di rete 1** e quindi fare clic sull'area di rete nell'elenco che si desidera collegare all'Area di rete 2.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="0f5ee-120">Fare clic su **Area di rete 2** e quindi fare clic su un'area di rete nell'elenco che si desidera collegare all'Area di rete 1.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="0f5ee-121">Facoltativamente, fare clic su **Criteri larghezza di banda** e selezionare il profilo di criteri di larghezza di banda che si desidera applicare al collegamento area di rete.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0f5ee-122">Applicare criteri di larghezza di banda solo se il collegamento area di rete è vincolato dalla larghezza di banda e si desidera utilizzare CAC per controllare il traffico multimediale su tale collegamento.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="0f5ee-123">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="0f5ee-124">Per completare la creazione dei collegamenti area di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per le altre aree.</span><span class="sxs-lookup"><span data-stu-id="0f5ee-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0f5ee-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f5ee-125">See also</span></span>

[<span data-ttu-id="0f5ee-126">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="0f5ee-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="0f5ee-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="0f5ee-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="0f5ee-128">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="0f5ee-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="0f5ee-129">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="0f5ee-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
