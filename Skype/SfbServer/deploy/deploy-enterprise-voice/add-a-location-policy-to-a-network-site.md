---
title: Aggiungere un criterio di posizione a un sito di rete in Skype for Business Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Assegnare i criteri di posizione E9-1-1 ai siti di rete in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 3653811298e7ce5659d4d416798010b3ac427732
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195833"
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


