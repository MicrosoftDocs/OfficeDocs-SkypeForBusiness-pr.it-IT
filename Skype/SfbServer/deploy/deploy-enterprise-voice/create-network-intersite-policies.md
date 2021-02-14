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
ms.openlocfilehash: 69609da75fdfa87309743920eace59892a440f2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822476"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="ae452-103">Creare criteri tra siti di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ae452-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="ae452-104">Creare criteri tra siti di rete, utilizzati VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ae452-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="ae452-105">Un criterio tra siti di rete definisce le limitazioni della larghezza di banda tra i siti che dispongono di collegamenti WAN diretti tra di essi.</span><span class="sxs-lookup"><span data-stu-id="ae452-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ae452-106">È necessario un criterio tra siti di rete solo  *se*  è presente un collegamento incrociato diretto tra due siti di rete.</span><span class="sxs-lookup"><span data-stu-id="ae452-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="ae452-107">Nell'area Nord America della topologia di esempio esiste un collegamento diretto tra i siti Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="ae452-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="ae452-108">Questi due siti richiedono un criterio tra siti che applica un profilo di criteri di larghezza di banda appropriato.</span><span class="sxs-lookup"><span data-stu-id="ae452-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="ae452-109">Nell'esempio seguente viene applicato il profilo 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="ae452-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="ae452-110">Per creare un criterio tra siti di rete</span><span class="sxs-lookup"><span data-stu-id="ae452-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="ae452-111">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="ae452-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ae452-112">Eseguire il cmdlet New-CsNetworkInterSitePolicy per creare criteri tra siti di rete e applicare un profilo dei criteri di larghezza di banda appropriato per due siti con collegamento incrociato diretto.</span><span class="sxs-lookup"><span data-stu-id="ae452-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="ae452-113">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ae452-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="ae452-114">Ripetere il passaggio 2 in base alle esigenze per creare criteri tra siti di rete per tutte le coppie di siti di rete con un collegamento incrociato diretto.</span><span class="sxs-lookup"><span data-stu-id="ae452-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ae452-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae452-115">See also</span></span>

[<span data-ttu-id="ae452-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ae452-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="ae452-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ae452-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="ae452-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ae452-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="ae452-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ae452-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
