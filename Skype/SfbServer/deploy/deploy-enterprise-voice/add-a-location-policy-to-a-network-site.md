---
title: Aggiungere un criterio percorso a un sito di rete in Skype for Business Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Assegnare i criteri percorso E9-1-1 ai siti di rete in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 887c2fcab63acd5d143ba80f6be6976e8fe2b39f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804276"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Aggiungere un criterio percorso a un sito di rete in Skype for Business Server
 
Assegnare i criteri percorso E9-1-1 ai siti di rete in Skype for Business Server VoIP aziendale. 
  
Negli esempi seguenti viene illustrato come aggiungere il criterio percorso **Redmond** definito in [create location Policies in Skype for Business Server](create-location-policies.md) a un sito di rete esistente e come creare un nuovo sito di rete in cui viene utilizzato il criterio percorso **Redmond** .
  
Per informazioni dettagliate sull'utilizzo dei siti di rete, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Per assegnare un criterio percorso a un sito di rete esistente

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
2. Eseguire i cmdlet seguenti per modificare un sito di rete esistente.
    
    Assegnare il criterio percorso con tag **Redmond** a un sito di rete esistente denominato **Redmond**.
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Per assegnare un criterio percorso a un nuovo sito di rete

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet seguente per creare un nuovo sito di rete.
    
    Creare un nuovo sito di rete nell'area di rete e assegnare il criterio percorso contrassegnato come **Redmond**.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


