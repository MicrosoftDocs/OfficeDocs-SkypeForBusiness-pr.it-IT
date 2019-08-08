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
ms.openlocfilehash: ac03057de5b6e25e2b9de812f0d53ae02811d456
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233702"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Creare criteri di rete tra siti in Skype for Business Server
 
Creare criteri inter-sito di rete, che vengono usati dal controllo di ammissione alle chiamate vocali aziendali in Skype for Business Server. 
  
Un criterio intersito di rete definisce le limitazioni della larghezza di banda tra i siti con collegamenti WAN diretti tra di essi.
  
> [!IMPORTANT]
> È necessario un criterio intersito di rete *solo* se esiste un collegamento incrociato diretto tra due siti di rete.
  
Nella topologia di esempio dell'area Nord America esiste un collegamento diretto tra i siti Reno e Albuquerque. Questi due siti richiedono un criterio tra siti che applica un profilo dei criteri di larghezza di banda appropriato. L'esempio seguente applica il profilo 20Mb_Link.
  
### <a name="to-create-a-network-inter-site-policy"></a>Per creare un criterio inter-sito di rete

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet New-CsNetworkInterSitePolicy per creare criteri inter-sito di rete e applicare un profilo dei criteri di larghezza di banda appropriato per due siti che hanno un collegamento incrociato diretto. Ad esempio, eseguire:
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Ripetere il passaggio 2 in base alle esigenze per creare criteri inter-sito di rete per tutte le coppie di siti di rete con un collegamento incrociato diretto.
    
## <a name="see-also"></a>Vedere anche

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
