---
title: Aggiungere un criterio di posizione a un sito di rete in Skype for Business Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Assegnare i criteri di posizione E9-1-1 ai siti di rete in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 4a74b1ee44d1e2f34a51d7859235e10649d0e2ee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234058"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Aggiungere un criterio di posizione a un sito di rete in Skype for Business Server
 
Assegnare i criteri di posizione E9-1-1 ai siti di rete in Skype for Business Server VoIP aziendale. 
  
Gli esempi seguenti illustrano come aggiungere i criteri di posizione di **Redmond** definiti in [creare criteri di posizione in Skype for Business Server](create-location-policies.md) in un sito di rete esistente e come creare un nuovo sito di rete che usa il criterio di posizione **Redmond** .
  
Per informazioni dettagliate sull'uso dei siti di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Per assegnare un criterio di posizione a un sito di rete esistente

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire i cmdlet seguenti per modificare un sito di rete esistente.
    
    Assegnare i criteri di posizione Tagged **Redmond** a un sito di rete esistente denominato **Redmond**.
    
   ```
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Per assegnare un criterio di posizione a un nuovo sito di rete

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet seguente per creare un nuovo sito di rete.
    
    Creare un nuovo sito di rete nell'area di rete e assegnare il criterio di posizione Tagged **Redmond** .
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


