---
title: Creare collegamenti area di rete in Skype for Business Server
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Creare o modificare i collegamenti delle aree di rete, utilizzati dal controllo di ammissione di chiamata VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: 1b891a299e85836e4a69b4a6c6e9df9a52cb0cdc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822466"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Creare collegamenti area di rete in Skype for Business Server
 
Creare o modificare i collegamenti delle aree di rete, utilizzati dal controllo di ammissione di chiamata VoIP aziendale in Skype for Business Server. 
  
Le aree all'interno di una rete sono collegate tramite connettività fisica WAN. Un collegamento area di rete crea un collegamento tra due aree configurate per il controllo di ammissione di chiamata e imposta le limitazioni della larghezza di banda per il traffico audio e video tra queste aree.
  
Nella topologia di esempio è presente un collegamento tra il Nord America e le aree APAC e un collegamento tra le aree EMEA e APAC. Ognuno di questi collegamenti tra aree geografiche è vincolato dalla larghezza di banda della WAN, come descritto nella tabella informazioni sulla larghezza di banda del collegamento regionale, ad [esempio: raccolta dei requisiti per il controllo di ammissione di chiamata in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Per creare collegamenti area di rete utilizzando Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet New-CsNetworkRegionLink per creare i collegamenti area di rete e applicare i profili di criteri di larghezza di banda appropriati. Ad esempio, eseguire:
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Per creare collegamenti area di rete utilizzando il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.
    
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

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
