---
title: Gestione delle aree di rete
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
description: Area di rete* sono gli hub di rete o backbone utilizzati nella configurazione del controllo di ammissione di chiamata, del servizio E9-1-1 e del bypass multimediale.
ms.openlocfilehash: 14c8004ddd14c0a37c25d700edae845ac9adfe29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816416"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Gestione delle aree di rete in Skype for Business Server

*Le aree di* rete sono hub di rete o backbone utilizzati nella configurazione del controllo di ammissione di chiamata, del servizio E9-1-1 e del bypass multimediale. Utilizzare le procedure seguenti per visualizzare, creare o modificare aree di rete. Ad esempio, se sono già state create aree di rete per una funzionalità vocale, non è necessario creare nuove aree di rete. altre funzionalità avanzate VoIP aziendale utilizzeranno le stesse aree di rete. Potrebbe tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche della caratteristica. Ad esempio, se sono state create aree di rete per il servizio E9-1-1 (che non richiedono un sito centrale associato) e quindi si distribuisce il controllo di ammissione di chiamata, è necessario modificare le definizioni delle aree di rete per specificare un sito centrale. 

Utilizzare le procedure descritte in questo articolo per visualizzare informazioni sulle aree di rete oppure per creare, modificare o eliminare aree di rete. 

## <a name="view-network-region-information"></a>Visualizzare le informazioni sull'area di rete 


Un'area di rete interconnette diverse parti di una rete dislocate su più aree geografiche. Ogni area di rete deve essere associata a un sito centrale. Il sito centrale è il sito del data center in cui è in esecuzione il servizio dei criteri di larghezza di banda del controllo di ammissione di chiamata. Puoi usare il Pannello di controllo di Skype for Business Server per visualizzare le aree di rete. Per le aree di rete sono disponibili impostazioni che determinano se sono consentiti percorsi alternativi attraverso Internet per le connessioni audio e video. Le informazioni in questo argomento descrivono come visualizzare le aree di rete esistenti. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Per visualizzare informazioni su un'area di rete con il Pannello di controllo di Skype for Business Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area.**

4.  Nella pagina **Area** fare clic sull'area che si desidera visualizzare.
  
    > [!NOTE]  
    > È possibile visualizzare una sola area alla volta.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sulle aree di rete tramite Windows PowerShell cmdlet

È possibile visualizzare le informazioni sulle aree di rete utilizzando Windows PowerShell e il cmdlet **Get-CsNetworkRegion.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

### <a name="to-view-network-region-information"></a>Per visualizzare le informazioni sulle aree di rete

  - Per visualizzare informazioni su tutte le aree di rete, digitare il comando seguente in Skype for Business Server Management Shell, quindi premere INVIO:
    
        Get-CsNetworkRegion
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="create-or-modify-network-regions"></a>Creare o modificare aree di rete 

Un'area di rete interconnette diverse parti di una rete dislocate su più aree geografiche. Ogni area di rete deve essere associata a un sito centrale. Il sito centrale è il sito del data center in cui è in esecuzione il servizio dei criteri di larghezza di banda del controllo di ammissione di chiamata. È possibile utilizzare il Pannello di controllo di Skype for Business Server per configurare le aree di rete. Queste includono impostazioni che determinano se consentire percorsi alternativi Internet per le connessioni audio e video. Dal Pannello di controllo di Skype for Business Server puoi creare, modificare o eliminare un'area di rete. Utilizzare questo argomento per creare e modificare le aree di rete. 

### <a name="to-create-a-network-region"></a>Per creare un'area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area.**

4.  Nella pagina **Area** fare clic su **Nuovo**.

5.  Nella pagina **Nuova area** digitare un valore nel campo **Nome**. Questo valore deve essere univoco all'interno della distribuzione di Skype for Business Server.

6.  Nell'elenco a discesa **Sito centrale** selezionare il sito centrale per questa area di rete.

7.  La casella di controllo **Abilita percorso alternativo audio** è selezionata per impostazione predefinita. Questo campo determina se le chiamate audio verranno instradate tramite un percorso alternativo se non è disponibile una larghezza di banda adeguata nel percorso principale. Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet. Se alcune delle chiamate vengono effettuate via Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni della larghezza di banda.

8.  La casella di controllo **Abilita percorso alternativo video** è selezionata per impostazione predefinita. Questo parametro determina se le chiamate video verranno instradate tramite un percorso alternativo se non è disponibile una larghezza di banda adeguata nel percorso principale. Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet. Se alcune delle chiamate vengono effettuate via Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni della larghezza di banda.

9.  (Facoltativo) Digitare un valore nel campo **Descrizione** per specificare ulteriori informazioni sull'area che non è possibile fornire solo con il nome.

10. Fare clic su **Commit**.

La tabella **Siti associati** non viene utilizzata per la creazione di un'area di rete. Si associa un sito a un'area durante la creazione o la modifica del sito. Per informazioni dettagliate, vedere [Managing call admission control for sites.](managing-call-admission-control-for-sites.md)

### <a name="to-modify-a-network-region"></a>Per modificare un'area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area.**

4.  Nella pagina **Area** fare clic sull'area che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  Nella pagina **Modifica area** è possibile modificare le impostazioni per abilitare e disabilitare i percorsi alternativi per audio e video, nonché modificare la descrizione. Per informazioni dettagliate, vedere la sezione "Per creare un'area di rete" più indietro in questo argomento.

7.  Fare clic su **Commit**.

Non è possibile modificare i **Siti associati** in questa pagina. L'elenco dei siti associati viene fornito per riferimento in modo da sapere quali siti saranno interessati dalla modifica delle impostazioni dell'area.


## <a name="delete-existing-network-regions"></a>Eliminare aree di rete esistenti 

Un'area di rete interconnette diverse parti di una rete dislocate su più aree geografiche. Ogni area di rete deve essere associata a un sito centrale. Il sito centrale è il sito del data center in cui è in esecuzione il servizio dei criteri di larghezza di banda del controllo di ammissione di chiamata. È possibile utilizzare il Pannello di controllo di Skype for Business Server per configurare le aree di rete. Queste includono impostazioni che determinano se consentire percorsi alternativi Internet per le connessioni audio e video. Dal Pannello di controllo di Skype for Business Server puoi creare, modificare o eliminare un'area di rete. Utilizzare questo argomento per eliminare le aree di rete esistenti. 

### <a name="to-delete-a-network-region"></a>Per eliminare un'area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area.**

4.  Nella pagina **Area** fare clic sull'area che si desidera eliminare.
  
    > [!NOTE]  
    > È possibile eliminare più aree contemporaneamente. A tale scopo, premere CTRL e selezionare più aree tenendo premuto CTRL. Per selezionare tutte le aree, scegliere **Seleziona tutto** dal menu **Modifica**.

5.  Scegliere **Elimina** dal menu **Modifica**.

6.  Fare clic su **OK**.


    > [!WARNING]  
    > Non è possibile rimuovere un'area di rete se è associata a un sito di rete. Se si tenta di rimuovere un'area associata a un sito, verrà visualizzato un messaggio di errore. Per scoprire se un'area è associata a siti, selezionare l'area e quindi scegliere **Mostra dettagli** dal menu **Modifica**.


## <a name="see-also"></a>Vedere anche

[Gestione delle route area di rete](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
