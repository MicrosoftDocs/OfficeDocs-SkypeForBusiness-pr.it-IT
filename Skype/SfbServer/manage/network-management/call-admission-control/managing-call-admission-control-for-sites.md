---
title: Gestione del controllo di ammissione di chiamata per i siti
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
description: I siti di rete sono gli uffici o le postazioni in ogni area di rete delle distribuzioni del servizio Controllo di ammissione di chiamata (CAC, Call Admission Control), del servizio per chiamate di emergenza E9-1-1 e di bypass multimediale.
ms.openlocfilehash: 0b339f15e53dd94bda655884f70c041f9da9e5a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118565"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Gestione del controllo di ammissione di chiamata per i siti in Skype for Business Server

I siti di rete sono gli uffici o le postazioni in ogni area di rete delle distribuzioni del servizio Controllo di ammissione di chiamata (CAC, Call Admission Control), del servizio per chiamate di emergenza E9-1-1 e di bypass multimediale. Utilizzare le procedure descritte in questo articolo per configurare il controllo di ammissione di chiamata per i siti di rete.

## <a name="configure-network-site-links"></a>Configurare i collegamenti di sito di rete

All'interno di una configurazione del servizio Controllo di ammissione di chiamata è possibile creare criteri tra siti di rete che definiscono le limitazioni di larghezza di banda tra i siti direttamente collegati. Se due siti di rete condividono un collegamento diretto, è possibile definire dei limiti della larghezza di banda per le connessioni audio e video tra tali siti. Non è possibile utilizzare il Pannello di controllo di Skype for Business Server per configurare i criteri del sito di rete, ma è possibile farlo solo utilizzando i cmdlet di Skype for Business Server Management Shell. È possibile creare, modificare e rimuovere un collegamento di sito di rete (noto anche come criterio tra siti di rete) da Skype for Business Server Management Shell.

### <a name="to-create-a-network-site-link"></a>Per creare un collegamento di sito di rete

1.  Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari.

2.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server** e quindi Skype for Business Server Management **Shell.**

3.  Al prompt dei comandi digitare il comando seguente, utilizzando valori validi per la configurazione in uso:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    In questo esempio viene creato un nuovo collegamento di sito di rete denominato Reno Portland che imposta i limiti di larghezza di banda tra i siti di rete di Reno e \_ Portland. Il profilo dei criteri di larghezza di banda e siti di rete deve essere già presente prima dell'esecuzione di questo comando.

Per descrizioni dettagliate dei parametri, [vedere New-CsNetworkInterSitePolicy.](/powershell/module/skype/New-CsNetworkInterSitePolicy) Per ottenere un elenco dei profili dei criteri di larghezza di banda che è possibile applicare al collegamento di sito di rete, chiamare il cmdlet **Get-CsNetworkBandwidthPolicyProfile**. Per informazioni dettagliate, [vedere Get-CsNetworkBandwidthPolicyProfile.](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

### <a name="to-modify-a-network-site-link"></a>Per modificare un collegamento di sito di rete

1.  Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari.

2.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server** e quindi Skype for Business Server Management **Shell.**

3.  Utilizzare il cmdlet **CsNetworkInterSitePolicy Set** per modificare le proprietà di un collegamento di sito di rete specifico. È possibile modificare uno dei siti connessi o entrambi ed è possibile modificare il profilo dei criteri di larghezza di banda associato al collegamento. Ecco un esempio di modifica del profilo dei criteri di larghezza di banda di un collegamento di sito denominato Reno \_ Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Per descrizioni dettagliate dei parametri, [vedere Set-CsNetworkInterSitePolicy.](/powershell/module/skype/Set-CsNetworkInterSitePolicy)


### <a name="to-delete-a-network-site-link"></a>Per eliminare un collegamento di sito di rete

1.  Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari.

2.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server** e quindi Skype for Business Server Management **Shell.**

3.  Utilizzare il cmdlet **Remove-CsNetworkInterSitePolicy** per rimuovere un collegamento di sito di rete. Nell'esempio seguente viene eliminato il collegamento di sito di rete Reno \_ Portland:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Per descrizioni dettagliate dei parametri, [vedere Remove-CsNetworkInterSitePolicy.](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)


## <a name="view-network-site-information"></a>Visualizzare le informazioni sui siti di rete

I siti di rete sono gli uffici o le postazioni configurate in ogni area di una distribuzione del servizio Controllo di ammissione di chiamata (CAC) o del servizio per chiamate di emergenza Enhanced 9-1-1. È possibile visualizzare le informazioni sul sito di rete nel Pannello di controllo di Skype for Business Server o in Skype for Business Server Management Shell. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>Per visualizzare le informazioni sui siti di rete nel Pannello di controllo di Skype for Business Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Sito.**

4.  Nella pagina **Sito** fare clic sul sito che si desidera visualizzare.
 
    > [!NOTE]  
    > È possibile visualizzare informazioni per un solo sito alla volta.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sui siti di rete tramite Windows PowerShell cmdlet

È possibile visualizzare le informazioni sui siti di rete utilizzando Windows PowerShell e il cmdlet Get-CsNetworkSite rete. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

### <a name="to-view-network-site-information"></a>Per visualizzare informazioni sui siti di rete

  - Per visualizzare informazioni su tutti i siti di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkSite
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Per ulteriori informazioni, vedere l'argomento della guida relativo al cmdlet [Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite).


## <a name="create-or-modify-network-sites"></a>Creare o modificare siti di rete 

I siti di rete sono gli uffici o le postazioni configurate in ogni area di una distribuzione del servizio Controllo di ammissione di chiamata (CAC) o del servizio per chiamate di emergenza Enhanced 9-1-1. Puoi usare il Pannello di controllo di Skype for Business Server per configurare i siti e associarli alle aree geografiche. Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di rete come Chicago, Redmond e Vancouver. Deve essere creato un sito di rete del servizio Controllo di ammissione di chiamata per ogni sito di un'organizzazione, anche se tale sito non presenta limitazioni della larghezza di banda. Dal Pannello di controllo di Skype for Business Server è possibile creare, modificare ed eliminare siti di rete. Seguire le procedure seguenti per creare o modificare un sito di rete. 

### <a name="to-create-a-network-site"></a>Per creare un sito di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Sito.**

4.  Nella pagina **Sito** fare clic su **Nuovo**.

5.  In **Nuovo sito** digitare un nome per il sito nel campo **Nome**.

    > [!NOTE]  
    > I nomi dei siti devono essere univoci all'interno della distribuzione di Skype for Business Server.

6.  Nell'elenco a discesa **Area** selezionare un'area di rete da associare al sito.

7.  (Facoltativo) Se si desidera applicare limiti di larghezza di banda per le chiamate audio o video per il sito, selezionare il profilo del criterio larghezza di banda con le impostazioni appropriate nell'elenco a discesa **Criteri larghezza di banda**.
 
    > [!NOTE]  
    > È possibile visualizzare i dettagli dei profili dei criteri di larghezza  di banda disponibili o creare un nuovo profilo di criteri di larghezza di banda nella pagina Profilo criteri del **gruppo Configurazione di** rete. Per informazioni dettagliate, vedere [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).

8.  (Facoltativo) Se si desidera specificare impostazioni di posizione per questo sito, selezionare un criterio percorso nell'elenco a discesa **Criteri percorso**.

    > [!NOTE]  
    > Il criterio percorso assegna impostazioni specifiche di Enhanced 9-1-1 (E9-1-1) e delle posizioni client al sito. È possibile visualizzare i dettagli dei criteri percorso disponibili o creare un nuovo criterio percorso nella pagina **Criteri percorso** del gruppo **Configurazione di rete**. 

9.  (Facoltativo) Digitare un valore nel campo **Descrizione** per fornire ulteriori informazioni sul sito che non possono essere espresse utilizzando solo il nome.

10. Fare clic su **Commit**.

    > [!NOTE]  
    > Quando si crea un nuovo sito di rete, non si utilizza la tabella **Subnet associate**. L'associazione di una subnet a un sito viene effettuata quando si crea o si modifica la subnet. Per informazioni dettagliate, vedere [Managing network subnets](managing-network-subnets.md).

### <a name="to-modify-a-network-site"></a>Per modificare un sito di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Sito.**

4.  Nella pagina **Sito** fare clic sul sito che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  Nella pagina **Modifica sito** è possibile modificare la descrizione, l'area, il profilo del criterio larghezza di banda e il criterio percorso associati al sito. Per informazioni dettagliate, vedere [Per creare un sito di rete sopra.](#to-create-a-network-site)

7.  Fare clic su **Commit**.

Non è possibile modificare la tabella **Subnet associate** in questa pagina. L'elenco di subnet associate viene fornito come riferimento per indicare quali subnet saranno interessate in caso di modifica delle impostazioni del sito.


## <a name="delete-an-existing-network-site"></a>Eliminare un sito di rete esistente

I siti di rete sono gli uffici o le postazioni configurate in ogni area di una distribuzione del servizio Controllo di ammissione di chiamata (CAC) o del servizio per chiamate di emergenza Enhanced 9-1-1. Puoi usare il Pannello di controllo di Skype for Business Server per configurare i siti e associarli alle aree geografiche. Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di rete come Chicago, Redmond e Vancouver. Deve essere creato un sito di rete del servizio Controllo di ammissione di chiamata per ogni sito di un'organizzazione, anche se tale sito non presenta limitazioni della larghezza di banda. Dal Pannello di controllo di Skype for Business Server è possibile creare, modificare ed eliminare siti di rete. Per eliminare un sito di rete esistente, usare la procedura che segue. Per informazioni dettagliate sulla creazione o la modifica di siti di rete, vedere [Managing call admission control for sites](managing-call-admission-control-for-sites.md).


### <a name="to-delete-a-network-site"></a>Per eliminare un sito di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Sito.**

4.  Nella pagina **Sito** fare clic sul sito che si desidera eliminare.

    > [!NOTE]  
    > È possibile eliminare più siti contemporaneamente. A tale scopo, premere CTRL e selezionare più siti sempre tenendo premuto CTRL. In alternativa, per selezionare tutti i siti, scegliere **Seleziona tutto** dal menu **Modifica**.

5.  Scegliere **Elimina** dal menu **Modifica**.

6.  Fare clic su **OK**.
    

    > [!WARNING]  
    > Se un sito di rete è associato a una subnet di rete, non è possibile rimuoverlo. Se si tenta di rimuovere un sito associato a una subnet, verrà visualizzato un messaggio di errore. Per controllare se un sito è associato a eventuali subnet, fare clic sul sito e quindi scegliere **Mostra dettagli** dal menu **Modifica**.


## <a name="see-also"></a>Vedere anche


[New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite)