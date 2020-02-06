---
title: Gestione delle aree di rete
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
description: Area di rete * sono gli hub di rete o i backbone usati nella configurazione del controllo di ammissione alle chiamate, E9-1-1 e bypass multimediale.
ms.openlocfilehash: c08232e455edb4388a052c2859b35e6c137b890a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817485"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Gestione delle aree di rete in Skype for Business Server

Le *aree di rete* sono gli hub di rete o le backbone usati nella configurazione del controllo di ammissione alle chiamate, E9-1-1 e bypass multimediale. Usare le procedure seguenti per visualizzare, creare o modificare le aree di rete. Se ad esempio sono già state create aree di rete per una sola funzionalità vocale, non è necessario creare nuove aree di rete. altre funzionalità vocali avanzate di Enterprise useranno le stesse aree di rete. Può tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche delle caratteristiche. Ad esempio, se sono state create aree di rete per E9-1-1 (che non richiedono un sito centrale associato) e quindi si distribuisce il controllo di ammissione delle chiamate, è necessario modificare le definizioni dell'area di rete per specificare un sito centrale. 

Usare le procedure descritte in questo articolo per visualizzare le informazioni sull'area di rete o per creare, modificare o eliminare aree di rete. 

## <a name="view-network-region-information"></a>Visualizzare le informazioni relative all'area di rete 


Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche. Ogni area di rete deve essere associata a un sito centrale. Il sito centrale è il sito centro dati in cui è in uso il servizio criteri di larghezza di banda di controllo delle chiamate (CAC). Puoi usare il pannello di controllo di Skype for Business Server per visualizzare le aree di rete. Le aree di rete includono impostazioni che determinano se i percorsi alternativi tramite Internet sono consentiti per le connessioni audio e video. Usare questo argomento per visualizzare le aree di rete esistenti. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Per visualizzare informazioni su un'area geografica di rete con il pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **area geografica**.

4.  Nella pagina **area geografica** fare clic sull'area che si vuole visualizzare.
  
    > [!NOTE]  
    > È possibile visualizzare una sola area alla volta.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni relative all'area di rete tramite i cmdlet di Windows PowerShell

Per visualizzare le informazioni relative all'area di rete, è possibile usare Windows PowerShell e il cmdlet **Get-CsNetworkRegion** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

### <a name="to-view-network-region-information"></a>Per visualizzare le informazioni relative all'area di rete

  - Per visualizzare informazioni su tutte le aree geografiche di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkRegion
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .


## <a name="create-or-modify-network-regions"></a>Creare o modificare aree di rete 

Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche. Ogni area di rete deve essere associata a un sito centrale. Il sito centrale è il sito centro dati in cui è in uso il servizio criteri di larghezza di banda di controllo delle chiamate (CAC). Puoi usare il pannello di controllo di Skype for Business Server per configurare le aree geografiche di rete. Le aree di rete includono impostazioni che determinano se i percorsi alternativi tramite Internet sono consentiti per le connessioni audio e video. Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare un'area geografica di rete. Usare questo argomento per creare e modificare le aree di rete. 

### <a name="to-create-a-network-region"></a>Per creare un'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **area geografica**.

4.  Nella pagina **area** fare clic su **nuovo**.

5.  Nella pagina **nuova area** Digitare un valore nel campo **nome** . Questo valore deve essere univoco all'interno della distribuzione di Skype for Business Server.

6.  Nell'elenco a discesa **sito centrale** selezionare il sito centrale per l'area di rete.

7.  La casella di controllo **Attiva percorso alternativo audio** è selezionata per impostazione predefinita. Questo campo determina se le chiamate audio verranno instradate tramite un percorso alternativo se la larghezza di banda adeguata non esiste nel percorso principale. Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet. Se le chiamate saranno chiamate Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni di larghezza di banda.

8.  La casella di controllo **Attiva percorso alternativo video** è selezionata per impostazione predefinita. Questo campo determina se le videochiamate verranno instradate tramite un percorso alternativo se la larghezza di banda adeguata non esiste nel percorso principale. Deselezionare questa casella di controllo solo se è necessario disattivare l'offload su Internet. Se le chiamate saranno chiamate Internet, questa casella di controllo deve essere selezionata, indipendentemente dalle impostazioni di larghezza di banda.

9.  Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni sull'area geografica che non può essere espressa solo dal nome.

10. Fare clic su **Commit**.

La tabella **siti associati** non viene usata per la creazione di un'area di rete. Quando si crea o si modifica il sito, si associa un sito a un'area geografica. Per informazioni dettagliate, vedere [gestione del controllo dell'ammissione delle chiamate per i siti](managing-call-admission-control-for-sites.md).

### <a name="to-modify-a-network-region"></a>Per modificare un'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **area geografica**.

4.  Nella pagina **area** fare clic sull'area che si vuole modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Nella pagina **modifica area** è possibile modificare le impostazioni per l'abilitazione e la disabilitazione di percorsi alternativi audio e video e modificare la descrizione (per informazioni dettagliate, vedere la sezione "per creare un'area di rete" in questo argomento.

7.  Fare clic su **Commit**.

Non è possibile modificare i **siti associati** in questa pagina. L'elenco dei siti associati viene fornito per il riferimento, in modo da sapere quali siti verranno modificati quando si modificano le impostazioni dell'area geografica.


## <a name="delete-existing-network-regions"></a>Eliminare le aree di rete esistenti 

Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche. Ogni area di rete deve essere associata a un sito centrale. Il sito centrale è il sito centro dati in cui è in uso il servizio criteri di larghezza di banda di controllo delle chiamate (CAC). Puoi usare il pannello di controllo di Skype for Business Server per configurare le aree geografiche di rete. Le aree di rete includono impostazioni che determinano se i percorsi alternativi tramite Internet sono consentiti per le connessioni audio e video. Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare un'area geografica di rete. Usare questo argomento per eliminare le aree di rete esistenti. 

### <a name="to-delete-a-network-region"></a>Per eliminare un'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **area geografica**.

4.  Nella pagina **area** fare clic sull'area che si desidera eliminare.
  
    > [!NOTE]  
    > Puoi eliminare più di un'area alla volta. A tale scopo, premere CTRL e selezionare più aree mentre si tiene premuto il tasto CTRL. In alternativa, per selezionare tutte le aree geografiche, fare clic su **Seleziona tutto** dal menu **modifica** .

5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.


    > [!WARNING]  
    > Un'area di rete non può essere rimossa se associata a un sito di rete. Se si tenta di rimuovere un'area associata a un sito, viene visualizzato un messaggio di errore. Per verificare se un'area è associata a qualsiasi sito, selezionare l'area geografica e quindi fare clic su **Mostra dettagli** dal menu **modifica** .


## <a name="see-also"></a>Vedere anche

[Gestione delle route dell'area di rete](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
