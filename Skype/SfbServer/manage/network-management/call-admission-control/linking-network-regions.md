---
title: Collegamento di aree di rete
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: "È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. "
ms.openlocfilehash: 0a4f5c63b4470fbfe6d2677f0e9e6f52841f7ebb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816466"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Collegamento delle aree di rete in Skype for Business Server

È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. Utilizzare le sezioni di questo articolo per visualizzare le informazioni sui collegamenti dell'area di lavoro oppure configurare o eliminare i collegamenti dell'area netwrok. 

## <a name="view-network-region-link-information"></a>Visualizzare le informazioni sul collegamento dell'area di rete 

È possibile visualizzare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. Le aree di una rete sono collegate mediante una connettività WAN fisica. È possibile utilizzare il Pannello di controllo di Skype for Business Server per visualizzare un collegamento esistente tra due aree di rete. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Per visualizzare un collegamento area di rete nel Pannello di controllo di Skype for Business Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Collegamento **area.**

4.  Nella pagina **Collegamento area** fare clic sul collegamento area che si desidera visualizzare.
    
    > [!NOTE]  
    > È possibile visualizzare informazioni su un collegamento aree alla volta.

5.  Scegliere **Elimina** dal menu **Mostra dettagli**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Visualizzare le informazioni sul collegamento dell'area di rete Windows PowerShell cmdlet

È possibile visualizzare i collegamenti delle aree di rete utilizzando Windows PowerShell e il cmdlet **Get-CsNetworkRegionLink.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Per visualizzare informazioni su un collegamento area di rete

  - To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:
    
        Get-CsNetworkRegionLink
    
    Il comando restituisce informazioni simili a quelle riportate di seguito:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Per informazioni dettagliate, vedere [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurare i collegamenti delle aree di rete 

È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. Le aree di una rete sono collegate mediante una connettività WAN fisica. È possibile utilizzare il Pannello di controllo di Skype for Business Server per definire un collegamento tra due aree di rete e impostare le limitazioni della larghezza di banda per le connessioni audio e video tra queste aree.

### <a name="to-create-a-network-region-link"></a>Per creare un collegamento area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Collegamento **area.**

4.  Nella pagina **Collegamento area** fare clic su **Nuovo.**

5.  In **Collegamento nuova area** digitare un valore nel **campo** Nome.
 
    > [!NOTE]  
    > Questo valore deve essere univoco all'interno della distribuzione di Skype for Business Server.

6.  Nell'elenco a discesa Area di rete **\# 1** selezionare una delle due aree da collegare.

7.  Nell'elenco a discesa **\# Area di rete 2** selezionare l'altra area da collegare. Questa area deve essere diversa dall'area selezionata per Area di rete \# 1.

8.  (Facoltativo) Se si desidera impostare limitazioni della larghezza di banda per le chiamate  audio o video tra queste aree, selezionare un profilo di criteri di larghezza di banda nell'elenco a discesa Criteri larghezza di banda.

9.  Fare clic su **Commit**.

### <a name="to-modify-a-network-region-link"></a>Per modificare un collegamento area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Collegamento **area.**

4.  Nella pagina **Collegamento area** fare clic sul collegamento dell'area che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  In **Modifica collegamento area** è possibile modificare le aree collegate o il profilo dei criteri di larghezza di banda per questo collegamento.

7.  Fare clic su **Commit**.


## <a name="delete-network-region-links"></a>Eliminare collegamenti area di rete

È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. Le aree di una rete sono collegate mediante una connettività WAN fisica. È possibile utilizzare il Pannello di controllo di Skype for Business Server per eliminare un collegamento esistente tra due aree di rete. 

### <a name="to-delete-a-network-region-link"></a>Per eliminare un collegamento area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Collegamento **area.**

4.  Nella pagina **Collegamento area** fare clic sul collegamento area che si desidera eliminare.
 
    > [!NOTE]  
    > È possibile eliminare più collegamenti aree contemporaneamente. A tale scopo, premere CTRL e selezionare più collegamenti aree tenendo premuto CTRL. Per selezionare tutti i collegamenti aree, scegliere <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>Modifica</STRONG>.

5.  Scegliere **Elimina** dal menu **Modifica**.

6.  Fare clic su **OK**.


## <a name="see-also"></a>Vedere anche

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
