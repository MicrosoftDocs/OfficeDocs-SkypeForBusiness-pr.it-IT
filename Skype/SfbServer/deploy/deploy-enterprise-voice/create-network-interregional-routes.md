---
title: Creare route interregionali di rete in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Creare o modificare route interregionali di rete, utilizzate VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server.
ms.openlocfilehash: 0d4e4977cbd2aed82de9c8299f326f301551321a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594720"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Creare route interregionali di rete in Skype for Business Server
 
Creare o modificare route interregionali di rete, utilizzate VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server. 
  
Una route interregionale di rete definisce la route tra una coppia di aree di rete. Ogni coppia di aree di rete nella distribuzione del controllo di ammissione di chiamata richiede una route interregionale di rete. In tal modo ogni area di rete della distribuzione può accedere a tutte le altre aree.
  
Mentre i collegamenti area impostano limitazioni di larghezza di banda per le connessioni tra aree geografiche, una route interregionale determina il percorso collegato che la connessione attraverserà da un'area all'altra.
  
Nella topologia di esempio è necessario definire route interregionali di rete per ognuna delle tre coppie di aree: Nord America/EMEA, EMEA/APAC e Nord America/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Per creare route interregionali di rete tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic **su Skype for Business Server Management Shell.**
    
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
    > La route interregionale di rete Nord America/APAC richiede due collegamenti di area di rete perché non esiste un collegamento diretto tra le aree di rete. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Per creare route interregionali di rete tramite il Pannello Skype for Business Server di controllo

1. Apri Skype for Business Server Pannello di controllo.
    
2. Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.
    
3. Fare clic sul pulsante di spostamento **Route area**.
    
4. Fare clic su **Nuovo**.
    
5. Nella pagina **Nuova route area** fare clic su **Nome** e quindi digitare un nome per la route interregionale di rete.
    
6. Fare clic su **Area di rete 1** e quindi fare clic su un'area di rete nell'elenco per il routing all'area di rete 2.
    
7. Fare clic su **Area di rete 2** e quindi fare clic su un'area di rete nell'elenco per il routing all'area di rete 1.
    
8. Fare **clic su** Aggiungi accanto al **campo** Collegamenti area di rete e quindi aggiungere un collegamento di area di rete che verrà utilizzato nella route interregionale di rete.
    
    > [!NOTE]
    > Se si crea una route per due aree di rete tra le quali non esiste un collegamento diretto, è necessario aggiungere tutti i collegamenti necessari per completare la route. Ad esempio, la route interregionale di rete Nord America/APAC richiede due collegamenti di area di rete perché non esiste un collegamento diretto tra le aree di rete. 
  
9. Fare clic su **Commit**.
    
10. Per completare la creazione di route interregionali di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per altre route interregionali di rete.
    
## <a name="see-also"></a>Vedere anche

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)