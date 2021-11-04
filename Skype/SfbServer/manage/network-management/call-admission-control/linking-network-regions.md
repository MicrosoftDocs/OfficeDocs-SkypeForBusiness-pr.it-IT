---
title: Collegamento di aree di rete
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: "È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. "
ms.openlocfilehash: d194daf8e35a3e4b6b23c1c34fc8b4d4c2fea14f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746892"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Collegamento delle aree di rete in Skype for Business Server

È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. Utilizzare le sezioni di questo articolo per visualizzare le informazioni sui collegamenti all'area di lavoro oppure configurare o eliminare i collegamenti di area di rete. 

## <a name="view-network-region-link-information"></a>Visualizzare le informazioni sui collegamenti dell'area di rete 

È possibile visualizzare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. Le aree di una rete sono collegate mediante una connettività WAN fisica. Puoi usare il Pannello di controllo Skype for Business Server per visualizzare un collegamento esistente tra due aree di rete. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Per visualizzare un collegamento a un'area di rete Skype for Business Server Pannello di controllo

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Collegamento **area.**

4.  Nella pagina **Collegamento area** fare clic sul collegamento area che si desidera visualizzare.
    
    > [!NOTE]
    > È possibile visualizzare informazioni su un collegamento aree alla volta.

5.  Scegliere **Elimina** dal menu **Mostra dettagli**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Visualizzare le informazioni sui collegamenti dell'area di rete Windows PowerShell cmdlet

È possibile visualizzare i collegamenti di area di rete utilizzando Windows PowerShell e il cmdlet **Get-CsNetworkRegionLink.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Per visualizzare informazioni su un collegamento area di rete

  - Per visualizzare informazioni su tutti i collegamenti dell'area di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
    **Get-CsNetworkRegionLink**
    
    Il comando restituisce informazioni simili a quelle riportate di seguito:
    
       Identity : NorthwestToCalifornia BWPolicyProfileID : NetworkRegionLinkID : NorthwestToCalifornia NetworkRegionID1 : Pacific Northwest NetworkRegionID2 : California


Per informazioni dettagliate, vedere [Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurare i collegamenti di area di rete 

È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. Le aree di una rete sono collegate mediante una connettività WAN fisica. Puoi usare il Pannello di controllo Skype for Business Server per definire un collegamento tra due aree di rete e impostare i limiti di larghezza di banda per le connessioni audio e video tra queste aree.

### <a name="to-create-a-network-region-link"></a>Per creare un collegamento a un'area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Collegamento **area.**

4.  Nella pagina **Collegamento area** fare clic su **Nuovo.**

5.  In **Nuovo collegamento area** digitare un valore nel **campo** Nome.
 
    > [!NOTE]  
    > Questo valore deve essere univoco all'interno della Skype for Business Server distribuzione.

6.  Nell'elenco a discesa Area di rete **\# 1** selezionare una delle due aree da collegare.

7.  Nell'elenco a discesa Area di rete **\# 2** selezionare l'altra area da collegare. Questa area deve essere diversa dall'area selezionata per Area di rete \# 1.

8.  (Facoltativo) Se si desidera impostare limitazioni di larghezza di banda per le chiamate  audio o video tra queste aree, selezionare un profilo di criteri di larghezza di banda nell'elenco a discesa Criteri larghezza di banda.

9.  Fare clic su **Commit**.

### <a name="to-modify-a-network-region-link"></a>Per modificare un collegamento a un'area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Collegamento **area.**

4.  Nella pagina **Collegamento area** fare clic sul collegamento area che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  In **Modifica collegamento area** è possibile modificare le aree collegate o il profilo dei criteri di larghezza di banda per questo collegamento.

7.  Fare clic su **Commit**.


## <a name="delete-network-region-links"></a>Eliminare collegamenti di area di rete

È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. Le aree di una rete sono collegate mediante una connettività WAN fisica. Puoi usare il Pannello di controllo Skype for Business Server per eliminare un collegamento esistente tra due aree di rete. 

### <a name="to-delete-a-network-region-link"></a>Per eliminare un collegamento area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Collegamento **area.**

4.  Nella pagina **Collegamento area** fare clic sul collegamento area che si desidera eliminare.
 
    > [!NOTE]  
    > È possibile eliminare più collegamenti aree contemporaneamente. A tale scopo, premere CTRL e selezionare più collegamenti aree tenendo premuto CTRL. Per selezionare tutti i collegamenti aree, scegliere <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>Modifica</STRONG>.

5.  Scegliere **Elimina** dal menu **Modifica**.

6.  Fare clic su **OK**.


## <a name="see-also"></a>Vedere anche

[New-CsNetworkRegionLink](/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink)