---
title: Creare percorsi interregionali di rete in Skype for Business Server
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Creare o modificare le route interregionali di rete, che vengono utilizzate dal controllo di ammissione di chiamata VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: 86b7cf9e41cb20d82f0c3c6edd6bcbd74331d553
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822496"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Creare percorsi interregionali di rete in Skype for Business Server
 
Creare o modificare le route interregionali di rete, che vengono utilizzate dal controllo di ammissione di chiamata VoIP aziendale in Skype for Business Server. 
  
Una route interregionale di rete definisce la route tra una coppia di aree di rete. Ogni coppia di aree di rete nella distribuzione del controllo di ammissione di chiamata richiede una route interregionale di rete. In tal modo ogni area di rete della distribuzione può accedere a tutte le altre aree.
  
Se i collegamenti di area impostano limitazioni della larghezza di banda per le connessioni tra le aree geografiche, una route interregionale determina il percorso collegato che la connessione attraverserà da un'area all'altra.
  
Nella topologia di esempio, le route interregionali di rete devono essere definite per ognuna delle tre coppie di aree geografiche: Nord America/EMEA, EMEA/APAC e Nord America/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Per creare route interregionali di rete tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet **New-CsNetworkInterRegionRoute** per definire le route richieste. Ad esempio, eseguire:
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > La route interregionale di rete Nord America/APAC richiede due collegamenti tra aree di rete perché non è presente alcun collegamento tra l'area di rete diretta. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Per creare route interregionali di rete utilizzando il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.
    
2. Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.
    
3. Fare clic sul pulsante di spostamento **Route area**.
    
4. Fare clic su **Nuovo**.
    
5. Nella pagina **nuova route area** fare clic su **nome** e quindi digitare un nome per la route interregionale di rete.
    
6. Fare clic su **Area di rete 1** e quindi fare clic su un'area di rete nell'elenco per il routing all'area di rete 2.
    
7. Fare clic su **Area di rete 2** e quindi fare clic su un'area di rete nell'elenco per il routing all'area di rete 1.
    
8. Fare clic su **Aggiungi** accanto al campo **collegamenti area di rete** e quindi aggiungere un collegamento area di rete che verrà utilizzato nella route interregionale di rete.
    
    > [!NOTE]
    > Se si crea una route per due aree di rete tra le quali non esiste un collegamento diretto, è necessario aggiungere tutti i collegamenti necessari per completare la route. Ad esempio, la route interregionale di rete Nord America/APAC richiede due collegamenti tra aree di rete perché non è presente alcun collegamento tra l'area di rete diretta. 
  
9. Fare clic su **Commit**.
    
10. Per completare la creazione di route interregionali di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per le altre route interregionali di rete.
    
## <a name="see-also"></a>Vedere anche

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
