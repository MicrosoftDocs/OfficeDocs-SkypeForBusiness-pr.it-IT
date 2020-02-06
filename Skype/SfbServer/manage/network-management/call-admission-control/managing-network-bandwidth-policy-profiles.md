---
title: Gestione dei profili di criteri di larghezza di banda di rete
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
description: Usare le procedure descritte in questo articolo per visualizzare, creare, modificare o eliminare i profili dei criteri di larghezza di banda di rete.
ms.openlocfilehash: a9203c0935673e0dfd12d052876f06583c7c92c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817505"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Gestione dei profili di criteri di larghezza di banda di rete in Skype for Business Server

Usare le procedure descritte in questo articolo per visualizzare, creare, modificare o eliminare i profili dei criteri di larghezza di banda di rete.

## <a name="view-network-bandwidth-policy-profile-information"></a>Visualizzare informazioni sul profilo dei criteri di larghezza di banda di rete

Nell'ambito del controllo di ammissione di chiamata (CAC) viene usato un criterio di larghezza di banda per definire le limitazioni della larghezza di banda per determinate modalità. In Skype for Business Server è possibile assegnare limitazioni della larghezza di banda solo alle modalità audio e video. Puoi impostare limitazioni generali della larghezza di banda e limitazioni della sessione. Puoi usare il pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Ogni profilo dei criteri di larghezza di banda può essere associato a uno o più siti di rete. Usare le procedure seguenti per visualizzare un profilo dei criteri di larghezza di banda. 

### <a name="to-view-a-bandwidth-policy-profile"></a>Per visualizzare un profilo dei criteri di larghezza di banda

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri larghezza di banda**.

4.  Nella pagina **criteri di larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera visualizzare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni del profilo dei criteri di larghezza di banda di rete tramite i cmdlet di Windows PowerShell

I profili di larghezza di banda di rete possono essere visualizzati usando Windows PowerShell e il cmdlet Get-CsNetworkBandwidthPolicyProfile. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>Per visualizzare le informazioni sul profilo dei criteri di larghezza di banda

  - Per visualizzare informazioni su tutti i profili dei criteri di larghezza di banda della rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Creare o modificare i profili dei criteri di larghezza di banda

Nell'ambito del controllo di ammissione di chiamata (CAC) viene usato un criterio di larghezza di banda per definire le limitazioni della larghezza di banda per determinate modalità. In Skype for Business Server è possibile assegnare limitazioni della larghezza di banda solo alle modalità audio e video. Puoi impostare limitazioni generali della larghezza di banda e limitazioni della sessione. Puoi usare il pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Ogni profilo dei criteri di larghezza di banda può essere associato a uno o più siti di rete. Usare le procedure seguenti per creare o modificare un profilo dei criteri di larghezza di banda. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Per creare un nuovo profilo dei criteri di larghezza di banda

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **criteri larghezza di banda**.

4.  Nella pagina **criteri di larghezza di banda** fare clic su **nuovo**.

5.  In **nuovo profilo dei criteri di larghezza di banda**Digitare un nome nel campo **nome** . Questo nome deve essere univoco tra tutti i profili dei criteri di larghezza di banda.

6.  Nel campo **limite audio** Digitare un valore numerico. Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni audio espresse in kbps.

7.  Immettere un valore numerico nel campo **limite della sessione audio** . Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione audio, espressa in kbps. Questo valore deve essere 40 o superiore.

8.  Immettere un valore numerico nel campo **limite video** . Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni video espresse in kbps.

9.  Immettere un valore numerico nel campo **limite sessione video** . Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione video, espressa in kbps. Questo valore deve essere 100 o superiore.

10. Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni su questo profilo dei criteri di larghezza di banda che non può essere espresso solo dal nome.

11. Fare clic su **Commit**.

    > [!NOTE]  
    > La creazione di un nuovo profilo dei criteri di larghezza di banda non applica automaticamente restrizioni della larghezza di banda. È prima di tutto necessario associare il profilo dei criteri a un sito. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>Per modificare un profilo dei criteri di larghezza di banda

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **criteri larghezza di banda**.

4.  Nella pagina **criteri di larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Nella pagina **modifica profilo dei criteri di larghezza di banda** modificare i campi in modo necessario (per informazioni dettagliate, vedere [per creare un nuovo profilo dei criteri di larghezza di banda](#to-create-a-new-bandwidth-policy-profile)).

7.  Fare clic su **Commit**.

    > [!NOTE]  
    > Quando si modifica il profilo dei criteri di larghezza di banda, verranno immediatamente aggiornate le limitazioni della larghezza di banda di tutti i siti di rete associati al profilo del criterio di larghezza di banda.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Eliminare i profili dei criteri di larghezza di banda di rete

Nell'ambito del controllo di ammissione di chiamata (CAC) viene usato un criterio di larghezza di banda per definire le limitazioni della larghezza di banda per determinate modalità. In Skype for Business Server è possibile assegnare limitazioni della larghezza di banda solo alle modalità audio e video. Puoi impostare limitazioni generali della larghezza di banda e limitazioni della sessione. Puoi usare il pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Usare le procedure seguenti per eliminare i profili dei criteri di larghezza di banda di rete. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>Per eliminare un profilo dei criteri di larghezza di banda

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **criteri larghezza di banda**.

4.  Nella pagina **criteri di larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera eliminare.

    > [!NOTE]  
    > È possibile eliminare più di un profilo alla volta. Per eseguire questa operazione, premere CTRL e selezionare più profili tenendo premuto il tasto CTRL. In alternativa, per selezionare tutti i profili, fare clic su **Seleziona tutto** dal menu **modifica** .

5.  Scegliere **Elimina**dal menu **modifica** .
   

    > [!WARNING]  
    > Non è possibile eliminare un profilo dei criteri di larghezza di banda associato a un sito di rete. Prima di poter eliminare il profilo, devi prima rimuovere l'associazione con il sito di rete. 


## <a name="see-also"></a>Vedere anche

[Gestione del controllo dell'ammissione delle chiamate per i siti](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

