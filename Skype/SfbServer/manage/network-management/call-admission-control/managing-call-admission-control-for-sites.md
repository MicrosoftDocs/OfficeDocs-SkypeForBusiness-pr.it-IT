---
title: Gestione del controllo dell'ammissione delle chiamate per i siti
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
description: I siti di rete sono gli uffici o le posizioni all'interno di ogni area di rete delle distribuzioni di controllo di ammissione di chiamata (CAC), E9-1-1 e bypass multimediale.
ms.openlocfilehash: ec2a3dda70bdd4b952169ca663ca271b76f98481
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817515"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Gestione del controllo di ammissione di chiamata per i siti in Skype for Business Server

I siti di rete sono gli uffici o le posizioni all'interno di ogni area di rete delle distribuzioni di controllo di ammissione di chiamata (CAC), E9-1-1 e bypass multimediale. Usare le procedure descritte in questo articolo per configurare il controllo di ammissione delle chiamate per i siti di rete.

## <a name="configure-network-site-links"></a>Configurare i collegamenti ai siti di rete

All'interno di una configurazione di controllo di ammissione chiamata (CAC), è possibile creare criteri intersito di rete che definiscono le limitazioni della larghezza di banda tra i siti direttamente collegati. Quando i siti di rete condividono un collegamento diretto, è possibile definire limitazioni della larghezza di banda per le connessioni audio e video tra questi due siti. Non è possibile usare il pannello di controllo di Skype for Business Server per configurare i criteri del sito di rete, questo può essere eseguito solo usando i cmdlet di Skype for Business Server Management Shell. È possibile creare, modificare e rimuovere un collegamento al sito di rete (noto anche come criterio intersito di rete) da Skype for Business Server Management Shell.

### <a name="to-create-a-network-site-link"></a>Per creare un collegamento al sito di rete

1.  Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari.

2.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**server e quindi fare clic su **Skype for Business Server Management Shell**.

3.  Dal prompt dei comandi digitare il comando seguente, sostituendo i valori validi per la configurazione:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Questo esempio crea un nuovo collegamento di sito di rete\_denominato Reno Portland che imposta le limitazioni della larghezza di banda tra i siti di rete Reno e Portland. I siti di rete e il profilo dei criteri di larghezza di banda devono già esistere prima di eseguire questo comando.

Per una descrizione dettagliata dei parametri, vedere [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy). Per recuperare un elenco di profili dei criteri di larghezza di banda che possono essere applicati al collegamento al sito di rete, chiama il cmdlet **Get-CsNetworkBandwidthPolicyProfile** . Per informazioni dettagliate, vedere [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>Per modificare un collegamento al sito di rete

1.  Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari.

2.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**server e quindi fare clic su **Skype for Business Server Management Shell**.

3.  Utilizzare il cmdlet **set-CsNetworkInterSitePolicy** per modificare le proprietà di un collegamento al sito di rete specifico. È possibile modificare uno o entrambi i siti connessi e modificare il profilo dei criteri di larghezza di banda associato al collegamento. Ecco un esempio di modifica del profilo dei criteri di larghezza di banda di un collegamento\_di sito denominato Reno Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Per descrizioni dettagliate sui parametri, vedere [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>Per eliminare un collegamento al sito di rete

1.  Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari.

2.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**server e quindi fare clic su **Skype for Business Server Management Shell**.

3.  Utilizzare il cmdlet **Remove-CsNetworkInterSitePolicy** per rimuovere un collegamento al sito di rete. L'esempio seguente elimina il collegamento\_al sito network di Reno Portland:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Per descrizioni dettagliate dei parametri, vedere [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Visualizzare le informazioni sul sito di rete

I siti di rete sono gli uffici o i percorsi configurati in ogni area geografica di un controllo di ammissione alle chiamate (CAC) o una distribuzione avanzata di 9-1-1. È possibile visualizzare le informazioni sul sito di rete sia nel pannello di controllo di Skype for Business Server che in Skype for Business Server Management Shell. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Per visualizzare le informazioni sul sito di rete nel pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **sito**.

4.  Nella pagina del **sito** fare clic sul sito che si desidera visualizzare.
 
    > [!NOTE]  
    > È possibile visualizzare le informazioni solo per un sito alla volta.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sul sito di rete tramite i cmdlet di Windows PowerShell

È possibile visualizzare le informazioni sul sito di rete usando Windows PowerShell e il cmdlet Get-CsNetworkSite. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

### <a name="to-view-network-site-information"></a>Per visualizzare le informazioni sul sito di rete

  - Per visualizzare informazioni su tutti i siti di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkSite
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .


## <a name="create-or-modify-network-sites"></a>Creare o modificare siti di rete 

I siti di rete sono gli uffici o i percorsi configurati in ogni area geografica di un controllo di ammissione alle chiamate (CAC) o una distribuzione avanzata di 9-1-1. Puoi usare il pannello di controllo di Skype for Business Server per configurare i siti e associarli alle aree geografiche. Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di reti come Chicago, Redmond e Vancouver. È necessario creare un sito di rete CAC per ogni sito all'interno di un'organizzazione, anche se il sito non ha limitazioni di larghezza di banda. Nel pannello di controllo di Skype for Business Server è possibile creare, modificare ed eliminare siti di rete. Usare le procedure seguenti per creare o modificare un sito di rete. 

### <a name="to-create-a-network-site"></a>Per creare un sito di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **sito**.

4.  Nella pagina del **sito** fare clic su **nuovo**.

5.  In **nuovo sito**Digitare un nome per il sito nel campo **nome** .

    > [!NOTE]  
    > I nomi dei siti devono essere univoci all'interno della distribuzione di Skype for Business Server.

6.  Nell'elenco a discesa **Region** selezionare un'area di rete da associare al sito.

7.  Opzionale Se si vogliono inserire limitazioni della larghezza di banda per le chiamate audio o video a questo sito, selezionare il profilo dei criteri di larghezza di banda con le impostazioni appropriate nell'elenco a discesa **criteri di larghezza** di banda.
 
    > [!NOTE]  
    > È possibile visualizzare i dettagli dei profili di criteri di larghezza di banda disponibili oppure creare un nuovo profilo per i criteri di larghezza di banda nella pagina **Profil Policy** del gruppo **configurazione di rete** . Per informazioni dettagliate, vedere [gestione dei profili di criteri di larghezza di banda di rete](managing-network-bandwidth-policy-profiles.md).

8.  Opzionale Per specificare le impostazioni di posizione per questo sito, selezionare un criterio di posizione dall'elenco a discesa **criteri di posizione** .

    > [!NOTE]  
    > Il criterio posizione assegna al sito specifiche impostazioni avanzate di 9-1-1 (E9-1-1) e di posizione del client. È possibile visualizzare i dettagli dei criteri di posizione disponibili oppure creare un nuovo criterio di posizione dalla pagina **criteri posizione** del gruppo Configurazione di **rete** . 

9.  Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni su questo sito che non possono essere espresse solo dal nome.

10. Fare clic su **Commit**.

    > [!NOTE]  
    > Quando si crea un nuovo sito di rete, non si usa la tabella **subnet associata** . Si associa una subnet a un sito quando si crea o si modifica la subnet. Per informazioni dettagliate, vedere [gestione delle subnet di rete](managing-network-subnets.md).

### <a name="to-modify-a-network-site"></a>Per modificare un sito di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **sito**.

4.  Nella pagina del **sito** fare clic sul sito che si desidera modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Nella pagina **modifica sito** è possibile modificare la descrizione, l'area geografica, il profilo dei criteri di larghezza di banda e i criteri di posizione associati al sito. Per informazioni dettagliate, vedere [creare un sito di rete](#to-create-a-network-site) sopra.

7.  Fare clic su **Commit**.

Non è possibile modificare la tabella **subnet associata** in questa pagina. L'elenco delle subnet associate viene fornito come riferimento in modo da essere a conoscenza delle subnet che verranno modificate quando si modificano le impostazioni del sito.


## <a name="delete-an-existing-network-site"></a>Eliminare un sito di rete esistente

I siti di rete sono gli uffici o i percorsi configurati in ogni area geografica di un controllo di ammissione alle chiamate (CAC) o una distribuzione avanzata di 9-1-1. Puoi usare il pannello di controllo di Skype for Business Server per configurare i siti e associarli alle aree geografiche. Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di reti come Chicago, Redmond e Vancouver. È necessario creare un sito di rete CAC per ogni sito all'interno di un'organizzazione, anche se il sito non ha limitazioni di larghezza di banda. Nel pannello di controllo di Skype for Business Server è possibile creare, modificare ed eliminare siti di rete. Usare la procedura seguente per eliminare un sito di rete esistente. Per informazioni dettagliate sulla creazione o la modifica di siti di rete, vedere [gestione del controllo dell'ammissione delle chiamate per i siti](managing-call-admission-control-for-sites.md).


### <a name="to-delete-a-network-site"></a>Per eliminare un sito di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **sito**.

4.  Nella pagina del **sito** fare clic sul sito che si desidera eliminare.

    > [!NOTE]  
    > È possibile eliminare più di un sito alla volta. Per eseguire questa operazione, premere CTRL e selezionare più siti tenendo premuto il tasto CTRL. In alternativa, per selezionare tutti i siti, fare clic su **Seleziona tutto** dal menu **modifica** .

5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.
    

    > [!WARNING]  
    > Non è possibile rimuovere un sito di rete se associato a una subnet di rete. Se si tenta di rimuovere un sito associato a una subnet, viene visualizzato un messaggio di errore. Per verificare se un sito è associato a qualsiasi subnet, fare clic sul sito e quindi su **Mostra dettagli** dal menu **modifica** .


## <a name="see-also"></a>Vedere anche


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
