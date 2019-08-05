---
title: Creare collegamenti all'area di rete in Skype for Business Server
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Creare o modificare collegamenti all'area di rete, che vengono usati dal controllo di ammissione delle chiamate vocali aziendali in Skype for Business Server.
ms.openlocfilehash: 60d4d6f1279e7f6ad3946a6b25fb32ecd589ab07
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190433"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Creare collegamenti all'area di rete in Skype for Business Server
 
Creare o modificare collegamenti all'area di rete, che vengono usati dal controllo di ammissione delle chiamate vocali aziendali in Skype for Business Server. 
  
Le aree all'interno di una rete sono collegate tramite connettività WAN fisica. Un collegamento all'area di rete crea un collegamento tra due aree geografiche configurate per il controllo di ammissione alle chiamate (CAC) e imposta le limitazioni della larghezza di banda per il traffico audio e video tra queste aree.
  
La topologia di esempio include un collegamento tra le aree Nord America e APAC e un collegamento tra le aree EMEA e APAC. Ognuno di questi collegamenti di area geografica è vincolato dalla larghezza di banda WAN, come descritto nella tabella informazioni sulla larghezza di banda del collegamento di area, ad [esempio: requisiti per la raccolta del controllo di ammissione di chiamata in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Per creare collegamenti all'area geografica di rete tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet New-CsNetworkRegionLink per creare i collegamenti all'area geografica e applicare i profili dei criteri di larghezza di banda appropriati. Ad esempio, eseguire:
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Per creare collegamenti all'area geografica di rete tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.
    
2. Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.
    
3. Fare clic sul pulsante di spostamento **collegamento area geografica** .
    
4. Fare clic su **nuovo**.
    
5. Nella pagina **New Region link** fare clic su **nome** e quindi digitare un nome per il collegamento all'area di rete.
    
6. Fare clic su **area di rete #1**e quindi sull'area di rete nell'elenco che si desidera collegare all'area di rete #2.
    
7. Fare clic su **area di rete #2**e quindi fare clic su un'area di rete nell'elenco che si vuole collegare a #1 dell'area di rete.
    
8. Facoltativamente, fare clic su **criteri di larghezza di banda**e quindi selezionare il profilo dei criteri di larghezza di banda che si vuole applicare al collegamento all'area di rete.
    
    > [!NOTE]
    > Applicare un criterio di larghezza di banda solo se il collegamento all'area di rete è vincolato dalla larghezza di banda e si vuole usare CAC per controllare il traffico multimediale sul collegamento. 
  
9. Fare clic su **Commit**.
    
10. Per completare la creazione di collegamenti di area di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per altre aree geografiche.
    
## <a name="see-also"></a>Vedere anche

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
