---
title: Creare profili dei criteri di larghezza di banda in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Creare o modificare i criteri di larghezza di banda usati dal controllo di ammissione alle chiamate vocali aziendali in Skype for Business Server.
ms.openlocfilehash: c7fecafe5f036405088a3c6c62b70774b779e266
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191342"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>Creare profili dei criteri di larghezza di banda in Skype for Business Server 
 
Creare o modificare i criteri di larghezza di banda usati dal controllo di ammissione alle chiamate vocali aziendali in Skype for Business Server. 
  
I criteri di larghezza di banda definiscono le limitazioni dell'utilizzo della larghezza di banda per le modalità audio e video in tempo reale. I criteri di larghezza di banda vengono applicati ai profili dei criteri di larghezza di banda, che possono essere applicati a più siti di rete per il controllo ammissione chiamata.
  
Per linee guida sui limiti della larghezza di banda da impostare nella distribuzione di CAC, vedere [pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
I criteri di esempio creati nella procedura seguente impostano i limiti per il traffico audio globale, le singole sessioni audio, il traffico video complessivo e le singole sessioni video. Ad esempio, il profilo dei criteri di larghezza di banda 5Mb_Link imposta i limiti seguenti: 
  
- Limite audio: 2.000 Kbps
    
- Limite della sessione audio: 200 Kbps
    
- Limite video: 1.400 kbps
    
- Limite sessione video: 700 Kbps
    
> [!NOTE]
> Il valore limite minimo della sessione audio è 40 Kbps. Il valore limite minimo della sessione video è di 100 kbps. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>Per creare profili dei criteri di larghezza di banda tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Per ogni profilo dei criteri di larghezza di banda che si vuole creare, eseguire il cmdlet New-CsNetworkBandwidthPolicyProfile. Ad esempio, eseguire:
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>Per creare profili dei criteri di larghezza di banda tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.
    
2. Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.
    
3. Fare clic sul pulsante di spostamento del **profilo dei criteri** .
    
4. Fare clic su **nuovo**.
    
5. Nella pagina **nuovo profilo dei criteri** fare clic su **nome** e quindi digitare un nome per il profilo dei criteri di larghezza di banda.
    
6. Fare clic su **limite audio**e quindi digitare il numero massimo di kbps da consentire per tutte le sessioni audio combinate.
    
7. Fare clic su **limite sessione audio**e quindi digitare il numero massimo di kbps da consentire per ogni singola sessione audio.
    
8. Fare clic su **limite video**e quindi digitare il numero massimo di kbps da consentire per tutte le sessioni video combinate.
    
9. Fare clic su **limite sessione video**e quindi digitare il numero massimo di kbps da consentire per ogni singola sessione video.
    
10. Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere il profilo dei criteri di larghezza di banda.
    
11. Fare clic su **Commit**.
    
12. Per completare la creazione di profili dei criteri di larghezza di banda per la topologia, ripetere i passaggi da 4 a 11 con impostazioni per altri profili dei criteri di larghezza
    
## <a name="see-also"></a>Vedere anche

[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
