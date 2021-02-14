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
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Creare criteri tra siti di rete in Skype for Business Server
 
Creare criteri tra siti di rete, utilizzati VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server. 
  
Un criterio tra siti di rete definisce le limitazioni della larghezza di banda tra i siti che dispongono di collegamenti WAN diretti tra di essi.
  
> [!IMPORTANT]
> È necessario un criterio tra siti di rete solo  *se*  è presente un collegamento incrociato diretto tra due siti di rete.
  
Nell'area Nord America della topologia di esempio esiste un collegamento diretto tra i siti Reno e Albuquerque. Questi due siti richiedono un criterio tra siti che applica un profilo di criteri di larghezza di banda appropriato. Nell'esempio seguente viene applicato il profilo 20Mb_Link.
  
### <a name="to-create-a-network-inter-site-policy"></a>Per creare un criterio tra siti di rete

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
2. Eseguire il cmdlet New-CsNetworkInterSitePolicy per creare criteri tra siti di rete e applicare un profilo dei criteri di larghezza di banda appropriato per due siti con collegamento incrociato diretto. Ad esempio, eseguire:
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Ripetere il passaggio 2 in base alle esigenze per creare criteri tra siti di rete per tutte le coppie di siti di rete con un collegamento incrociato diretto.
    
## <a name="see-also"></a>Vedere anche

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
