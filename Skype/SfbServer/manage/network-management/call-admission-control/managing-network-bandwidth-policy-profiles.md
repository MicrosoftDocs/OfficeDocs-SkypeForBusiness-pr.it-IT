---
title: Gestione dei profili di criteri di larghezza di banda di rete
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
description: Utilizzare le procedure descritte in questo articolo per visualizzare, creare, modificare o eliminare profili di criteri di larghezza di banda di rete.
ms.openlocfilehash: 69efe657b6df775b9e647a77bef2588cafdc5b03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816446"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Gestione dei profili di criteri di larghezza di banda di rete in Skype for Business Server

Utilizzare le procedure descritte in questo articolo per visualizzare, creare, modificare o eliminare profili di criteri di larghezza di banda di rete.

## <a name="view-network-bandwidth-policy-profile-information"></a>Visualizzare le informazioni sul profilo del criterio larghezza di banda di rete

In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità. In Skype for Business Server, solo le modalità audio e video possono essere assegnate alle limitazioni della larghezza di banda. È possibile impostare limitazioni della larghezza di banda globali o per le sessioni. È possibile utilizzare il pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Ogni profilo di criteri della larghezza di banda può essere associato a uno o più siti di rete. Utilizzare le procedure seguenti per visualizzare un profilo di criteri della larghezza di banda. 

### <a name="to-view-a-bandwidth-policy-profile"></a>Per visualizzare un profilo dei criteri di larghezza di banda

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 

3.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Criteri larghezza di banda**.

4.  Nella pagina **criteri larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera visualizzare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sul profilo dei criteri di larghezza di banda di rete tramite i cmdlet di Windows PowerShell

I profili di larghezza di banda di rete possono essere visualizzati utilizzando Windows PowerShell e il cmdlet Get-CsNetworkBandwidthPolicyProfile. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>Per visualizzare le informazioni sul profilo dei criteri di larghezza di banda

  - Per visualizzare informazioni su tutti i profili dei criteri di larghezza di banda di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


Per ulteriori informazioni, vedere l'argomento della Guida per il cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Creare o modificare i profili dei criteri di larghezza di banda

In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità. In Skype for Business Server, solo le modalità audio e video possono essere assegnate alle limitazioni della larghezza di banda. È possibile impostare limitazioni della larghezza di banda globali o per le sessioni. È possibile utilizzare il pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Ogni profilo di criteri della larghezza di banda può essere associato a uno o più siti di rete. Utilizzare le procedure seguenti per creare o modificare un profilo dei criteri di larghezza di banda. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Per creare un nuovo profilo di criteri di larghezza di banda

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri larghezza di banda**.

4.  Nella pagina **criteri larghezza di banda** fare clic su **nuovo**.

5.  In **nuovo profilo dei criteri di larghezza di banda** Digitare un nome nel campo **nome** . Questo nome deve essere univoco tra tutti i profili dei criteri di larghezza di banda.

6.  Nel campo **limite audio** Digitare un valore numerico. Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni audio espresse in kbps.

7.  Immettere un valore numerico nel campo **limite sessione audio** . Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione audio, espressa in kbps. Questo valore deve essere 40 o superiore.

8.  Immettere un valore numerico nel campo **limite video** . Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni video espresse in kbps.

9.  Immettere un valore numerico nel campo **limite sessione video** . Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione video, espressa in kbps. Questo valore deve essere 100 o superiore.

10. Optional Digitare un valore nel campo **Descrizione** per fornire ulteriori informazioni sul profilo dei criteri di larghezza di banda che non è possibile esprimere solo con il nome.

11. Fare clic su **Commit**.

    > [!NOTE]  
    > La creazione di un nuovo profilo di criteri di larghezza di banda non impone automaticamente restrizioni di larghezza di banda. È necessario innanzitutto associare il profilo dei criteri a un sito. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>Per modificare un profilo di criteri della larghezza di banda

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri larghezza di banda**.

4.  Nella pagina **Criteri larghezza di banda** fare clic sul profilo di criteri della larghezza di banda che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  Nella pagina **modifica profilo dei criteri di larghezza di banda** modificare i campi in base alle esigenze (per informazioni dettagliate, vedere [per creare un nuovo profilo dei criteri di larghezza di banda](#to-create-a-new-bandwidth-policy-profile)).

7.  Fare clic su **Commit**.

    > [!NOTE]  
    > Quando si modifica il profilo dei criteri di larghezza di banda, verranno aggiornate immediatamente le limitazioni della larghezza di banda di tutti i siti di rete associati al profilo del criterio di larghezza di banda.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Eliminare i profili dei criteri di larghezza di banda di rete

In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità. In Skype for Business Server, solo le modalità audio e video possono essere assegnate alle limitazioni della larghezza di banda. È possibile impostare limitazioni della larghezza di banda globali o per le sessioni. È possibile utilizzare il pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Usare le procedure seguenti per eliminare profili di criteri della larghezza di banda di rete. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>Per eliminare un profilo di criteri della larghezza di banda

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri larghezza di banda**.

4.  Nella pagina **Criteri larghezza di banda** fare clic sul profilo di criteri della larghezza di banda che si desidera eliminare.

    > [!NOTE]  
    > È possibile eliminare più profili contemporaneamente. A tale scopo, tenere premuto CTRL e selezionare i diversi profili. In alternativa, per selezionare tutti i profili, scegliere **Seleziona tutto** dal menu **Modifica**.

5.  Scegliere **Elimina** dal menu **Modifica**.
   

    > [!WARNING]  
    > Non è possibile eliminare un profilo di criteri della larghezza di banda associato a un sito di rete. È necessario rimuovere l'associazione al sito di rete prima di poter eliminare il profilo. 


## <a name="see-also"></a>Vedere anche

[Gestione del controllo di ammissione di chiamata per i siti](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

