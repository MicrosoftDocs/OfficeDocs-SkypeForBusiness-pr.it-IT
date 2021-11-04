---
title: Aggiungere criteri percorso a un sito di rete in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Assegnare criteri percorso E9-1-1 ai siti di rete in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 9d248d91703284d58b27e5fd593af95ddf4edaf3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765954"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Aggiungere criteri percorso a un sito di rete in Skype for Business Server
 
Assegnare criteri percorso E9-1-1 ai siti di rete in Skype for Business Server VoIP aziendale. 
  
Negli esempi seguenti viene illustrato come aggiungere il criterio percorso **di Redmond** definito in Creare criteri percorso [in Skype for Business Server a](create-location-policies.md) un sito di rete esistente e come creare un nuovo sito di rete che utilizza il criterio percorso **redmond.**
  
Per informazioni dettagliate sull'utilizzo dei siti di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Per assegnare un criterio percorso a un sito di rete esistente

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
2. Eseguire i cmdlet seguenti per modificare un sito di rete esistente.
    
    Assegnare il criterio Percorso con tag **Redmond** a un sito di rete esistente denominato **Redmond.**
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Per assegnare un criterio percorso a un nuovo sito di rete

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
2. Eseguire il cmdlet seguente per creare un nuovo sito di rete.
    
    Creare un nuovo sito di rete nell'area di rete e assegnare il criterio percorso contrassegnato come **Redmond**.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


