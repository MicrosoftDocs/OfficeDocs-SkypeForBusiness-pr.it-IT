---
title: Abilitare il controllo di ammissione di chiamata in Skype for Business Server
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Abilitare il controllo di ammissione di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 2b8096a9223250cec88e57e68fdc201f5591fd92
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109862"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Abilitare il controllo di ammissione di chiamata in Skype for Business Server
 
Abilitare il controllo di ammissione di chiamata in Skype for Business Server VoIP aziendale. 
  
Dopo aver configurato le impostazioni di rete per la distribuzione del servizio Controllo di ammissione di chiamata, è necessario abilitare il servizio per rendere effettivi i criteri relativi alla larghezza di banda.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Per abilitare il controllo di ammissione di chiamata tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
2. Eseguire il cmdlet Set-CsNetworkConfiguration per abilitare il servizio Controllo di ammissione di chiamata nella rete. Ad esempio, eseguire:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Se si desidera disabilitare il servizio Controllo di ammissione di chiamata nella rete, eseguire quanto segue:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Per abilitare il controllo di ammissione di chiamata tramite il Pannello di controllo di Skype for Business Server

1. Aprire il Pannello di controllo di Skype for Business Server.
    
2. Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.
    
3. Fare clic sul pulsante di spostamento **Globale**.
    
4. Fare clic su **Globale** nell'elenco e quindi scegliere **Mostra dettagli** dal menu **Modifica**.
    
5. Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita il controllo di ammissione di chiamata**.
    
    > [!NOTE]
    > Se si desidera disabilitare il servizio Controllo di ammissione di chiamata in tutta la distribuzione, deselezionare questa casella di controllo. 
  
6. Fare clic su **Commit**. 
    
## <a name="see-also"></a>Vedere anche

[Get-CsNetworkConfiguration](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)