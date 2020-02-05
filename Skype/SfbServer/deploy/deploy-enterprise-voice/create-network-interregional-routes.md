---
title: Creare route interregionali di rete in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Creare o modificare le route interregionali di rete, usate dal controllo di ammissione delle chiamate vocali aziendali in Skype for Business Server.
ms.openlocfilehash: 2a55e3e2028494a8bc9dc25164eaa67b08d35f83
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767929"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Creare route interregionali di rete in Skype for Business Server
 
Creare o modificare le route interregionali di rete, usate dal controllo di ammissione delle chiamate vocali aziendali in Skype for Business Server. 
  
Una route interregionale di rete definisce la route tra una coppia di aree della rete. Ogni coppia di aree di rete nella distribuzione del controllo di ammissione alle chiamate richiede una route interregionale di rete. In questo modo ogni area di rete della distribuzione consente di accedere a tutte le altre aree geografiche.
  
Mentre i collegamenti per le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni, una route interregionale determina il percorso collegato che la connessione attraverserà da un'area a un'altra.
  
Nella topologia di esempio è necessario definire le route interregionali di rete per ognuna delle tre coppie di aree geografiche: Nord America/EMEA, EMEA/APAC e Nord America/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Per creare route interregionali di rete tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet **New-CsNetworkInterRegionRoute** per definire le route necessarie. Ad esempio, eseguire:
    
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
    > La route Interregional Network Nord America/APAC richiede due collegamenti all'area geografica di rete perché non è presente un collegamento all'area di rete diretta. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Per creare route interregionali di rete tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.
    
2. Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.
    
3. Fare clic sul pulsante di spostamento della **Route geografica** .
    
4. Fare clic su **nuovo**.
    
5. Nella pagina **nuova route dell'area geografica** fare clic su **nome** e quindi digitare un nome per la route interregionale di rete.
    
6. Fare clic su **area geografica #1**e quindi fare clic su un'area di rete nell'elenco che si vuole instradare all'area geografica di rete #2.
    
7. Fare clic su **area geografica #2**e quindi fare clic su un'area di rete nell'elenco che si vuole instradare all'area geografica di rete #1.
    
8. Fare clic su **Aggiungi** accanto al campo **collegamenti area di rete** e quindi aggiungere un collegamento all'area di rete che verrà usato nella route interregionale di rete.
    
    > [!NOTE]
    > Se si sta creando una route per due aree di rete che non dispongono di un collegamento all'area di rete diretta, è necessario aggiungere tutti i collegamenti necessari per completare la route. Ad esempio, la route Interregional Network Nord America/APAC richiede due collegamenti all'area geografica di rete perché non è presente un collegamento all'area di rete diretta. 
  
9. Fare clic su **Commit**.
    
10. Per completare la creazione di route interregionali di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per altre route interregionali di rete.
    
## <a name="see-also"></a>Vedere anche

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
