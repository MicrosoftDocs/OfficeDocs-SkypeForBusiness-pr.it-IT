---
title: Abilitare il controllo di ammissione alle chiamate in Skype for Business Server
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Abilitare il controllo di ammissione alle chiamate in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: ed770a79a7237de682822e8280a13de4516921ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192077"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Abilitare il controllo di ammissione alle chiamate in Skype for Business Server
 
Abilitare il controllo di ammissione alle chiamate in Skype for Business Server VoIP aziendale. 
  
Dopo aver configurato le impostazioni di rete per la distribuzione del controllo di ammissione alle chiamate, è necessario abilitare CAC per applicare i criteri di larghezza di banda.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Per abilitare il controllo dell'ammissione alle chiamate usando Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet Set-CsNetworkConfiguration per abilitare CAC nella rete. Ad esempio, eseguire:
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Se si vuole disabilitare CAC nella rete, eseguire le operazioni seguenti:
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Per abilitare il controllo dell'ammissione tramite chiamata tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.
    
2. Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.
    
3. Fare clic sul pulsante di spostamento **globale** .
    
4. Fare clic su **globale** nell'elenco e quindi selezionare **Mostra dettagli** dal menu **modifica** .
    
5. Nella pagina **Modifica impostazioni globali** selezionare la casella di **controllo Abilita l'ammissione alle chiamate** .
    
    > [!NOTE]
    > Se si vuole disabilitare il controllo di ammissione delle chiamate durante la distribuzione, deselezionare questa casella di controllo. 
  
6. Fare clic su **Commit**. 
    
## <a name="see-also"></a>Vedere anche

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
