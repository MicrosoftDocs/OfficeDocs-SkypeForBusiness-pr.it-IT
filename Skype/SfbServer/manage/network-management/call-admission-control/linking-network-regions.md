---
title: Collegamento tra aree di rete
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: "È possibile configurare i collegamenti tra due aree di rete nell'ambito del controllo di ammissione di chiamata (CAC). "
ms.openlocfilehash: b9ffa45c8a0a09ba4a7f9f0ebf6402b87116f01f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188585"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>Collegamento delle aree di rete in Skype for Business Server

È possibile configurare i collegamenti tra due aree di rete nell'ambito del controllo di ammissione di chiamata (CAC). Usare le sezioni di questo articolo per visualizzare le informazioni sul collegamento all'area del Tritone o per configurare o eliminare i collegamenti all'area geografica di netwrok. 

## <a name="view-network-region-link-information"></a>Visualizzare le informazioni sul collegamento all'area di rete 

È possibile visualizzare i collegamenti tra due aree di rete come parte del controllo di ammissione di chiamata (CAC). Le aree all'interno di una rete sono collegate tramite connettività WAN (Physical Wide Area Network). Puoi usare il pannello di controllo di Skype for Business Server per visualizzare un collegamento esistente tra due aree di rete. 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>Per visualizzare un collegamento all'area di rete nel pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su collegamento all'area geografica. ****

4.  Nella pagina **collegamento all'area geografica** fare clic sul collegamento all'area che si desidera visualizzare.
    
    > [!NOTE]  
    > Puoi visualizzare solo le informazioni su un collegamento all'area geografica alla volta.

5.  Nel menu **modifica** selezionare **Mostra dettagli**.

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Visualizzare le informazioni sul collegamento all'area di rete tramite i cmdlet di Windows PowerShell

È possibile visualizzare i collegamenti all'area di rete usando Windows PowerShell e il cmdlet **Get-CsNetworkRegionLink** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


### <a name="to-view-network-region-link-information"></a>Per visualizzare le informazioni sul collegamento all'area di rete

  - Per visualizzare informazioni su tutti i collegamenti dell'area geografica di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkRegionLink
    
    Questo comando restituisce informazioni simili a quelle seguenti:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


Per informazioni dettagliate, vedere [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="configure-network-region-links"></a>Configurare i collegamenti dell'area di rete 

È possibile configurare i collegamenti tra due aree di rete nell'ambito del controllo di ammissione di chiamata (CAC). Le aree all'interno di una rete sono collegate tramite connettività WAN (Physical Wide Area Network). È possibile usare il pannello di controllo di Skype for Business Server per definire un collegamento tra due aree di rete e impostare le limitazioni della larghezza di banda per le connessioni audio e video tra queste aree geografiche.

### <a name="to-create-a-network-region-link"></a>Per creare un collegamento all'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su collegamento all'area geografica. ****

4.  Nella pagina **collegamento all'area geografica** fare clic su **nuovo**.

5.  Nel **collegamento New Region**Digitare un valore nel campo **nome** .
 
    > [!NOTE]  
    > Questo valore deve essere univoco all'interno della distribuzione di Skype for Business Server.

6.  Nell'elenco a discesa **Network Region \#1** Selezionare una delle due aree geografiche da collegare.

7.  Nell'elenco a discesa **Network Region \#2** Selezionare l'altra area da collegare. L'area geografica deve essere diversa da quella selezionata per l' \#area geografica di rete 1.

8.  Opzionale Se si desidera inserire limitazioni della larghezza di banda per le chiamate audio o video tra queste aree geografiche, selezionare un profilo dei criteri di larghezza di banda nell'elenco a discesa **criteri di larghezza** di banda.

9.  Fare clic su **Commit**.

### <a name="to-modify-a-network-region-link"></a>Per modificare un collegamento all'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su collegamento all'area geografica. ****

4.  Nella pagina **collegamento all'area geografica** fare clic sul collegamento all'area che si desidera modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  In **Modifica collegamento area**è possibile modificare le aree collegate o il profilo dei criteri di larghezza di banda per questo collegamento.

7.  Fare clic su **Commit**.


## <a name="delete-network-region-links"></a>Eliminare i collegamenti all'area di rete

È possibile configurare i collegamenti tra due aree di rete nell'ambito del controllo di ammissione di chiamata (CAC). Le aree all'interno di una rete sono collegate tramite connettività WAN (Physical Wide Area Network). È possibile usare il pannello di controllo di Skype for Business Server per eliminare un collegamento esistente tra due aree di rete. 

### <a name="to-delete-a-network-region-link"></a>Per eliminare un collegamento all'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su collegamento all'area geografica. ****

4.  Nella pagina **collegamento all'area geografica** fare clic sul collegamento all'area che si desidera eliminare.
 
    > [!NOTE]  
    > Puoi eliminare più di un collegamento all'area geografica alla volta. Per eseguire questa operazione, premere CTRL e selezionare più collegamenti all'area geografica tenendo premuto CTRL. In alternativa, per selezionare tutti i collegamenti all'area geografica, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .

5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.


## <a name="see-also"></a>Vedere anche

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
