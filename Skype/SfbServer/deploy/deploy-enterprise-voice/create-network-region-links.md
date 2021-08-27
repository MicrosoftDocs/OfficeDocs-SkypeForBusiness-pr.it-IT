---
title: Creare collegamenti di area di rete in Skype for Business Server
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Creare o modificare collegamenti di area di rete, utilizzati VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server.
ms.openlocfilehash: bea44eaabf94c2b37db4d9e50f9266744670fb2a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594164"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Creare collegamenti di area di rete in Skype for Business Server
 
Creare o modificare collegamenti di area di rete, utilizzati VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server. 
  
Le aree all'interno di una rete sono collegate tramite connettività fisica WAN. Un collegamento di area di rete crea un collegamento tra due aree configurate per il servizio Controllo di ammissione di chiamata e imposta le limitazioni di larghezza di banda per il traffico audio e video tra queste aree.
  
Nella topologia di esempio è presente un collegamento tra il Nord America e le aree APAC e un collegamento tra le aree EMEA e APAC. Ognuno di questi collegamenti di area è vincolato dalla larghezza di banda WAN, come descritto nella tabella Region Link Bandwidth Information in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Per creare collegamenti di area di rete tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic **su Skype for Business Server Management Shell.**
    
2. Eseguire il cmdlet New-CsNetworkRegionLink per creare i collegamenti area di rete e applicare i profili di criteri di larghezza di banda appropriati. Ad esempio, eseguire:
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Per creare collegamenti di area di rete tramite il Skype for Business Server Pannello di controllo

1. Apri Skype for Business Server Pannello di controllo.
    
2. Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.
    
3. Fare clic sul pulsante di spostamento **Collegamento area**.
    
4. Fare clic su **Nuovo**.
    
5. Nella pagina **Nuovo collegamento area di rete** fare clic su **Nome** e quindi digitare un nome per il collegamento area di rete.
    
6. Fare clic su **Area di rete 1** e quindi fare clic sull'area di rete nell'elenco che si desidera collegare all'Area di rete 2.
    
7. Fare clic su **Area di rete 2** e quindi fare clic su un'area di rete nell'elenco che si desidera collegare all'Area di rete 1.
    
8. Facoltativamente, fare clic su **Criteri larghezza di banda** e selezionare il profilo di criteri di larghezza di banda che si desidera applicare al collegamento area di rete.
    
    > [!NOTE]
    > Applicare criteri di larghezza di banda solo se il collegamento area di rete è vincolato dalla larghezza di banda e si desidera utilizzare CAC per controllare il traffico multimediale su tale collegamento. 
  
9. Fare clic su **Commit**.
    
10. Per completare la creazione dei collegamenti area di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per le altre aree.
    
## <a name="see-also"></a>Vedere anche

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)