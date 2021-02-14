---
title: Gestione dei profili dei criteri di larghezza di banda di rete
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
description: Utilizzare le procedure descritte in questo articolo per visualizzare, creare, modificare o eliminare i profili dei criteri di larghezza di banda di rete.
ms.openlocfilehash: 69efe657b6df775b9e647a77bef2588cafdc5b03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816446"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Gestione dei profili di criteri di larghezza di banda di rete in Skype for Business Server

Utilizzare le procedure descritte in questo articolo per visualizzare, creare, modificare o eliminare i profili dei criteri di larghezza di banda di rete.

## <a name="view-network-bandwidth-policy-profile-information"></a>Visualizzare le informazioni sul profilo dei criteri di larghezza di banda di rete

In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità. In Skype for Business Server, solo le modalità audio e video possono essere assegnate limitazioni della larghezza di banda. È possibile impostare limitazioni della larghezza di banda globali o per le sessioni. Puoi usare il Pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Ogni profilo di criteri della larghezza di banda può essere associato a uno o più siti di rete. Utilizzare le procedure seguenti per visualizzare un profilo di criteri della larghezza di banda. 

### <a name="to-view-a-bandwidth-policy-profile"></a>Per visualizzare un profilo di criteri di larghezza di banda

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Criteri larghezza di banda**.

4.  Nella pagina **Criteri larghezza di** banda fare clic sul profilo dei criteri di larghezza di banda che si desidera visualizzare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sui profili dei criteri di larghezza di banda di rete Windows PowerShell cmdlet

I profili di larghezza di banda di rete possono essere visualizzati Windows PowerShell e il cmdlet Get-CsNetworkBandwidthPolicyProfile rete. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>Per visualizzare le informazioni sul profilo dei criteri di larghezza di banda di rete

  - Per visualizzare informazioni su tutti i profili dei criteri di larghezza di banda di rete, digitare il comando seguente in Skype for Business Server Management Shell, quindi premere INVIO:
    
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

In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità. In Skype for Business Server, solo le modalità audio e video possono essere assegnate limitazioni della larghezza di banda. È possibile impostare limitazioni della larghezza di banda globali o per le sessioni. Puoi usare il Pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Ogni profilo di criteri della larghezza di banda può essere associato a uno o più siti di rete. Utilizzare le procedure seguenti per creare o modificare un profilo di criteri di larghezza di banda. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Per creare un nuovo profilo di criteri di larghezza di banda

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Criteri larghezza di **banda.**

4.  Nella pagina **Criteri larghezza di** banda fare clic su **Nuovo.**

5.  In **Nuovo profilo criteri larghezza di** banda digitare un nome nel **campo** Nome. Questo nome deve essere univoco tra tutti i profili dei criteri di larghezza di banda.

6.  Nel campo **Limite audio** digitare un valore numerico. Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni audio, espressa in kbps.

7.  Immettere un valore numerico nel campo **Limite sessione** audio. Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione audio, espressa in kbps. Questo valore deve essere 40 o superiore.

8.  Immettere un valore numerico nel campo **Limite video.** Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni video, espressa in kbps.

9.  Immettere un valore numerico nel campo **Limite sessioni** video. Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione video, espressa in kbps. Questo valore deve essere 100 o superiore.

10. (Facoltativo) Digitare un valore nel campo **Descrizione** per fornire ulteriori informazioni su questo profilo di criteri di larghezza di banda che non può essere espresso solo dal nome.

11. Fare clic su **Commit**.

    > [!NOTE]  
    > La creazione di un nuovo profilo di criteri di larghezza di banda non applica automaticamente restrizioni di larghezza di banda. È innanzitutto necessario associare il profilo dei criteri a un sito. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>Per modificare un profilo di criteri della larghezza di banda

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Criteri larghezza di **banda.**

4.  Nella pagina **Criteri larghezza di banda** fare clic sul profilo di criteri della larghezza di banda che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  Nella pagina **Modifica profilo criteri larghezza di** banda modificare i campi in base alle esigenze (per informazioni dettagliate, vedere Per creare un nuovo profilo di criteri di larghezza di [banda).](#to-create-a-new-bandwidth-policy-profile)

7.  Fare clic su **Commit**.

    > [!NOTE]  
    > Quando si modifica il profilo dei criteri di larghezza di banda, vengono immediatamente aggiornate le limitazioni della larghezza di banda di tutti i siti di rete associati a questo profilo di criteri di larghezza di banda.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Eliminare i profili dei criteri di larghezza di banda di rete

In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità. In Skype for Business Server, solo le modalità audio e video possono essere assegnate limitazioni della larghezza di banda. È possibile impostare limitazioni della larghezza di banda globali o per le sessioni. Puoi usare il Pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Usare le procedure seguenti per eliminare profili di criteri della larghezza di banda di rete. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>Per eliminare un profilo di criteri della larghezza di banda

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Criteri larghezza di **banda.**

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
  

