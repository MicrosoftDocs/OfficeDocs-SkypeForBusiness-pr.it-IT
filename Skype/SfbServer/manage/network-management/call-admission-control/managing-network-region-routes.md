---
title: Gestione delle route dell'area di rete
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
description: Una route area di rete definisce la route tra una coppia di aree di rete. Ogni coppia di aree di rete nella distribuzione del servizio Controllo di ammissione di chiamata richiede una route di questo tipo.
ms.openlocfilehash: c91f46ff45dd50f638cdb4f256fb93f2d33781ec
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118555"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Gestione delle route delle aree di rete in Skype for Business Server

Una *route area di rete* definisce la route tra una coppia di aree di rete. Ogni coppia di aree di rete nella distribuzione del servizio Controllo di ammissione di chiamata richiede una route di questo tipo. In tal modo ogni area di rete della distribuzione può accedere a tutte le altre aree. Utilizzare le procedure descritte in questa procedura per visualizzare, creare, modificare o eliminare route dell'area di rete.

## <a name="view-network-region-route-information"></a>Visualizzare le informazioni sulle route dell'area di rete 

Ogni area di una configurazione di controllo di ammissione di chiamata deve in qualche modo poter accedere a tutte le altre aree. Mentre i collegamenti area impostano limitazioni della larghezza di banda nelle connessioni tra aree e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione per passare da un'area all'altra. Utilizzare le procedure seguenti per visualizzare le route dell'area di rete esistenti nel Pannello di controllo di Skype for Business Server o In Skype for Business Server Management Shell. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Per visualizzare le informazioni sulla route dell'area di rete nel Pannello di controllo di Skype for Business Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Route **area.**

4.  Nella pagina **Route area** fare clic sulla route area che si vuole visualizzare.


    > [!NOTE]  
    > È possibile visualizzare una sola route area per volta.


5.  Scegliere **Mostra dettagli** dal menu **Modifica**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sulle route dell'area di rete tramite Windows PowerShell cmdlet

Le informazioni sulla route dell'area di rete possono essere visualizzate Windows PowerShell e il cmdlet Get-CsNetworkInterRegionRoute rete. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>Per visualizzare le informazioni sulle route dell'area di rete

  - Per visualizzare informazioni su tutte le route dell'area di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkInterRegionRoute
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute).


## <a name="create-or-modify-network-region-routes"></a>Creare o modificare route area di rete

Ogni area di una configurazione di controllo di ammissione di chiamata deve in qualche modo poter accedere a tutte le altre aree. Mentre i collegamenti area impostano limitazioni della larghezza di banda nelle connessioni tra aree e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione per passare da un'area all'altra. Puoi usare il Pannello di controllo di Skype for Business Server per configurare le route dell'area di rete. Dal Pannello di controllo di Skype for Business Server puoi creare, modificare o eliminare una route dell'area di rete. Utilizzare questo argomento per creare o modificare una nuova route area di rete. 

### <a name="to-create-a-network-region-route"></a>Per creare una route area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Route **area.**

4.  Nella pagina **Route area** fare clic su **Nuovo**.

5.  In **Nuova route area** digitare un valore nel campo **Nome**.
   
    > [!NOTE]  
    > Questo valore deve essere univoco all'interno della distribuzione di Skype for Business Server.

6.  Nell'elenco a discesa Area di rete **\# 1** selezionare una delle due aree da collegare tramite questa route.

7.  Nell'elenco a discesa Area di rete **\# 2** selezionare l'altra area per la route. Questa area deve essere diversa dall'area selezionata per Area di rete \# 1.

8.  Utilizzare la casella di riepilogo **Collegamenti aree di rete** per aggiungere collegamenti area di rete alla route. Fare clic sul pulsante **Aggiungi** per visualizzare la pagina **Collegamento area**. Fare clic su un collegamento area da aggiungere alla route e quindi fare clic su **OK**.
    
    > [!NOTE]  
    > Continuare a fare clic sul pulsante **Aggiungi** per aggiungere altri collegamenti oppure selezionare un collegamento e fare clic su **Rimuovi** per rimuoverlo.

9.  Fare clic su **Commit**.


### <a name="to-modify-a-network-region-route"></a>Per modificare una route area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Route **area.**

4.  Nella pagina **Route area** fare clic sulla route area che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  In **Modifica route area** è possibile modificare le aree unite dalla route e i collegamenti area associati alla route.

7.  Fare clic su **Commit**.


## <a name="delete-existing-network-region-routes"></a>Eliminare route area di rete esistenti

Ogni area di una configurazione di controllo di ammissione di chiamata deve in qualche modo poter accedere a tutte le altre aree. Mentre i collegamenti area impostano limitazioni della larghezza di banda nelle connessioni tra aree e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione per passare da un'area all'altra. Puoi usare il Pannello di controllo di Skype for Business Server per configurare le route dell'area di rete. Dal Pannello di controllo di Skype for Business Server puoi creare, modificare o eliminare una route dell'area di rete. Utilizzare questo argomento per informazioni su come eliminare le route area di rete. 

### <a name="to-delete-a-network-region-route"></a>Per eliminare una route area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Route **area.**

4.  Nella pagina **Route area** fare clic sulla route area che si desidera eliminare.

    > [!NOTE]  
    > È possibile eliminare più di una route area per volta. A tale scopo, selezionare più route area tenendo premuto CTRL oppure, per selezionare tutte le route area, scegliere **Seleziona tutto** dal menu **Modifica**.

5.  Scegliere **Elimina** dal menu **Modifica**.

6.  Fare clic su **OK**.



## <a name="see-also"></a>Vedere anche

[Gestione delle aree di rete in Skype for Business Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute)