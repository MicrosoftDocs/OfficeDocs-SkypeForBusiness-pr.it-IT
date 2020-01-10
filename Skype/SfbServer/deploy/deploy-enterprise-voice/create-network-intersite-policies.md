---
title: Creare criteri di rete tra siti in Skype for Business Server
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Creare criteri inter-sito di rete, che vengono usati dal controllo di ammissione alle chiamate vocali aziendali in Skype for Business Server.
ms.openlocfilehash: ce1826a1205216791f056a46fa625d26e0362f1f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001746"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="e8dde-103">Creare criteri di rete tra siti in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8dde-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="e8dde-104">Creare criteri inter-sito di rete, che vengono usati dal controllo di ammissione alle chiamate vocali aziendali in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8dde-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="e8dde-105">Un criterio intersito di rete definisce le limitazioni della larghezza di banda tra i siti con collegamenti WAN diretti tra di essi.</span><span class="sxs-lookup"><span data-stu-id="e8dde-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e8dde-106">È necessario un criterio intersito di rete *solo* se esiste un collegamento incrociato diretto tra due siti di rete.</span><span class="sxs-lookup"><span data-stu-id="e8dde-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="e8dde-107">Nella topologia di esempio dell'area Nord America esiste un collegamento diretto tra i siti Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="e8dde-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="e8dde-108">Questi due siti richiedono un criterio tra siti che applica un profilo dei criteri di larghezza di banda appropriato.</span><span class="sxs-lookup"><span data-stu-id="e8dde-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="e8dde-109">L'esempio seguente applica il profilo 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="e8dde-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="e8dde-110">Per creare un criterio inter-sito di rete</span><span class="sxs-lookup"><span data-stu-id="e8dde-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="e8dde-111">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e8dde-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="e8dde-112">Eseguire il cmdlet New-CsNetworkInterSitePolicy per creare criteri inter-sito di rete e applicare un profilo dei criteri di larghezza di banda appropriato per due siti che hanno un collegamento incrociato diretto.</span><span class="sxs-lookup"><span data-stu-id="e8dde-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="e8dde-113">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="e8dde-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="e8dde-114">Ripetere il passaggio 2 in base alle esigenze per creare criteri inter-sito di rete per tutte le coppie di siti di rete con un collegamento incrociato diretto.</span><span class="sxs-lookup"><span data-stu-id="e8dde-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e8dde-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8dde-115">See also</span></span>

[<span data-ttu-id="e8dde-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e8dde-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="e8dde-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e8dde-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="e8dde-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e8dde-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="e8dde-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e8dde-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
