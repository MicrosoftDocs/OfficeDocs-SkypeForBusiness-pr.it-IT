---
title: Creare profili dei criteri di larghezza di banda in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Creare o modificare i criteri di larghezza di banda utilizzati VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server.
---

# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>Creare profili dei criteri di larghezza di banda in Skype for Business Server 
 
Creare o modificare i criteri di larghezza di banda utilizzati VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server. 
  
I criteri di larghezza di banda definiscono restrizioni per l'utilizzo della larghezza di banda per le modalità audio e video in tempo reale. I criteri di larghezza di banda vengono applicati ai profili dei criteri di larghezza di banda, che possono essere applicati a più siti di rete per il controllo di ammissione di chiamata.
  
Per linee guida sui limiti di larghezza di banda da impostare nella distribuzione del servizio Controllo di ammissione di chiamata, vedere [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
I criteri di esempio creati nella procedura seguente impostano limiti per il traffico audio e il traffico video complessivi e per le sessioni audio e le sessioni video individuali. Ad esempio, il profilo di criteri di larghezza di banda 5Mb_Link imposta i limiti seguenti: 
  
- Limite audio: 2.000 kbps
    
- Limite sessione audio: 200 kbps
    
- Limite video: 1.400 kbps
    
- Limite sessione video: 700 kbps
    
> [!NOTE]
> Il valore minimo per il limite di una sessione audio è 40 kbps. Il valore minimo per il limite di una sessione video è 100 kbps. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>Per creare profili di criteri di larghezza di banda tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start****, scegliere** Tutti i programmi, **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Per ogni profilo di criteri di larghezza di banda che si desidera creare eseguire il cmdlet New-CsNetworkBandwidthPolicyProfile. Ad esempio, eseguire:
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>Per creare profili di criteri di larghezza di banda tramite Skype for Business Server pannello di controllo

1. Aprire Skype for Business Server Pannello di controllo.
    
2. Sulla barra di spostamento sinistra fare clic su **Configurazione rete**.
    
3. Fare clic sul pulsante di spostamento **Profilo criteri**.
    
4. Fare clic su **Nuovo**.
    
5. Nella pagina **Nuovo profilo criteri** fare clic su **Nome** e quindi digitare un nome per il profilo di criteri di larghezza di banda.
    
6. Fare clic su **Limite audio** e quindi digitare il numero massimo di kbps consentiti per tutte le sessioni audio nel loro insieme.
    
7. Fare clic su **Limite sessione audio** e quindi digitare il numero massimo di kbps consentiti per ogni singola sessione audio.
    
8. Fare clic su **Limite video** e quindi digitare il numero massimo di kbps consentiti per tutte le sessioni video nel loro insieme.
    
9. Fare clic su **Limite sessione video** e quindi digitare il numero massimo di kbps consentiti per ogni singola sessione video.
    
10. Se si desidera, fare clic su **Descrizione** e quindi digitare ulteriori informazioni per descrivere il profilo di criteri di larghezza di banda.
    
11. Fare clic su **Commit**.
    
12. Per completare la creazione dei profili di criteri di larghezza di banda, ripetere i passaggi da 4 a 11 con le impostazioni per gli altri profili.
    
## <a name="see-also"></a>Vedere anche

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)