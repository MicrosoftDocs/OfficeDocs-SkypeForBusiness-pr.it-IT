---
title: Gestione delle route dell'area di rete
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Una route dell'area di rete definisce la route tra una coppia di aree della rete. Ogni coppia di aree della rete nella distribuzione del controllo di ammissione alle chiamate richiede una route dell'area di rete.
ms.openlocfilehash: 5e0c099b8c461873b96963c721d835f1ccdf4705
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817495"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Gestione delle route delle aree di rete in Skype for Business Server

Una *route dell'area di rete* definisce la route tra una coppia di aree della rete. Ogni coppia di aree della rete nella distribuzione del controllo di ammissione alle chiamate richiede una route dell'area di rete. In questo modo ogni area di rete della distribuzione consente di accedere a tutte le altre aree geografiche. Usare le procedure descritte in questo artilce per visualizzare, creare, modificare o eliminare le route dell'area di rete.

## <a name="view-network-region-route-information"></a>Visualizzare le informazioni sulla route dell'area di rete 

Ogni area geografica in una configurazione di controllo di ammissione chiamata (CAC) deve avere un modo per accedere a tutte le altre aree geografiche. Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione da un'area a un'altra. Usare le procedure seguenti per visualizzare le route dell'area geografica esistenti in Skype for Business Server Control Panel o Skype for Business Server Management Shell. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Per visualizzare le informazioni sulla route dell'area di rete nel pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **area geografica**.

4.  Nella pagina **route dell'area geografica** fare clic sulla route dell'area geografica che si desidera visualizzare.


    > [!NOTE]  
    > È possibile visualizzare una sola route geografica alla volta.


5.  Nel menu **modifica** fare clic su **Mostra dettagli**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sulla route dell'area di rete tramite i cmdlet di Windows PowerShell

Le informazioni sulla route dell'area di rete possono essere visualizzate usando Windows PowerShell e il cmdlet Get-CsNetworkInterRegionRoute. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>Per visualizzare le informazioni sulla route dell'area di rete

  - Per visualizzare informazioni su tutte le route dell'area di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkInterRegionRoute
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .


## <a name="create-or-modify-network-region-routes"></a>Creare o modificare le route dell'area di rete

Ogni area geografica in una configurazione di controllo di ammissione chiamata (CAC) deve avere un modo per accedere a tutte le altre aree geografiche. Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione da un'area a un'altra. Puoi usare il pannello di controllo di Skype for Business Server per configurare le route dell'area di rete. Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una route dell'area di rete. Usare questo argomento per creare o modificare una route dell'area di rete. 

### <a name="to-create-a-network-region-route"></a>Per creare una route dell'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **area geografica**.

4.  Nella pagina **Route Region** fare clic su **nuovo**.

5.  Nella **Route New Region**Digitare un valore nel campo **nome** .
   
    > [!NOTE]  
    > Questo valore deve essere univoco all'interno della distribuzione di Skype for Business Server.

6.  Nell'elenco a discesa ** \#area di rete 1** Selezionare una delle due aree geografiche da connettere tramite questa route.

7.  Nell'elenco a discesa **Network Region \#2** Selezionare l'altra area per questa route. L'area geografica deve essere diversa da quella selezionata per l' \#area geografica di rete 1.

8.  Usare la casella di riepilogo **collegamenti area di rete** per aggiungere collegamenti all'area geografica. Fare clic sul pulsante **Aggiungi** per visualizzare la pagina del **collegamento all'area geografica** . Fare clic su un collegamento all'area da aggiungere alla route e quindi fare clic su **OK**.
    
    > [!NOTE]  
    > Continuare a fare clic sul pulsante **Aggiungi** per aggiungere altri collegamenti oppure selezionare un collegamento e fare clic su **Rimuovi** per rimuovere un collegamento.

9.  Fare clic su **Commit**.


### <a name="to-modify-a-network-region-route"></a>Per modificare una route dell'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **area geografica**.

4.  Nella pagina **Route Region** fare clic sulla route dell'area geografica che si desidera modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  In **modifica route area**è possibile modificare le aree affiancate da questa route e i collegamenti dell'area geografica associati alla route.

7.  Fare clic su **Commit**.


## <a name="delete-existing-network-region-routes"></a>Eliminare le route dell'area di rete esistenti

Ogni area geografica in una configurazione di controllo di ammissione chiamata (CAC) deve avere un modo per accedere a tutte le altre aree geografiche. Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione da un'area a un'altra. Puoi usare il pannello di controllo di Skype for Business Server per configurare le route dell'area di rete. Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una route dell'area di rete. Usare questo argomento per eliminare le route esistenti nell'area di rete. 

### <a name="to-delete-a-network-region-route"></a>Per eliminare una route dell'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **area geografica**.

4.  Nella pagina **route dell'area geografica** fare clic sulla route di area che si desidera eliminare.

    > [!NOTE]  
    > Puoi eliminare più di una route della regione alla volta. Per eseguire questa operazione, premere CTRL e selezionare più percorsi per le aree geografiche mentre si tiene premuto il tasto CTRL. In alternativa, per selezionare tutte le route dell'area geografica, fare clic su **Seleziona tutto** dal menu **modifica** .

5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.



## <a name="see-also"></a>Vedere anche

[Gestione delle aree di rete in Skype for Business Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
