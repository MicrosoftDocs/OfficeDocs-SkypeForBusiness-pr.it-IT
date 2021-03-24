---
title: Creare criteri tra siti di rete in Skype for Business Server
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Creare criteri tra siti di rete, utilizzati VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server.
ms.openlocfilehash: 7c0ca45c691ab1ef70d3660c3d49a08c40bdd40d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093084"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="629e6-103">Creare criteri tra siti di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="629e6-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="629e6-104">Creare criteri tra siti di rete, utilizzati VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="629e6-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="629e6-105">Un criterio tra siti di rete definisce le limitazioni della larghezza di banda tra i siti che dispongono di collegamenti WAN diretti tra di essi.</span><span class="sxs-lookup"><span data-stu-id="629e6-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="629e6-106">Un criterio tra siti di rete è  *obbligatorio solo*  se è presente un collegamento incrociato diretto tra due siti di rete.</span><span class="sxs-lookup"><span data-stu-id="629e6-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="629e6-107">Nell'area Nord America della topologia di esempio esiste un collegamento diretto tra i siti Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="629e6-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="629e6-108">Questi due siti richiedono un criterio tra siti che applica un profilo di criteri di larghezza di banda appropriato.</span><span class="sxs-lookup"><span data-stu-id="629e6-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="629e6-109">Nell'esempio seguente viene applicato il profilo 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="629e6-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="629e6-110">Per creare un criterio tra siti di rete</span><span class="sxs-lookup"><span data-stu-id="629e6-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="629e6-111">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="629e6-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="629e6-112">Eseguire il cmdlet New-CsNetworkInterSitePolicy per creare criteri tra siti di rete e applicare un profilo di criteri di larghezza di banda appropriato per due siti con un collegamento incrociato diretto.</span><span class="sxs-lookup"><span data-stu-id="629e6-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="629e6-113">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="629e6-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="629e6-114">Ripetere il passaggio 2 in base alle esigenze per creare criteri tra siti di rete per tutte le coppie di siti di rete che hanno un collegamento incrociato diretto.</span><span class="sxs-lookup"><span data-stu-id="629e6-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="629e6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="629e6-115">See also</span></span>

[<span data-ttu-id="629e6-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="629e6-116">New-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="629e6-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="629e6-117">Get-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="629e6-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="629e6-118">Set-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="629e6-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="629e6-119">Remove-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)