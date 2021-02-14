---
title: Creare e impostare piani di chiamata
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Informazioni su come usare l'interfaccia di amministrazione di Microsoft Teams Windows PowerShell per creare e gestire piani di chiamata (piani di chiamata chiamate PSTN).
ms.openlocfilehash: 0655f81df9c8ce25368a281a7f5b3392f7fe6ec3
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814785"
---
# <a name="create-and-manage-dial-plans"></a>Creare e impostare piani di chiamata

Una volta pianificati i piani di chiamata per l'organizzazione e aver trovato tutte le regole di normalizzazione che devono essere create per l'instradamento delle chiamate, sei pronto a creare i piani di chiamata. È possibile usare l'interfaccia di amministrazione di Microsoft Teams Windows PowerShell per creare e gestire piani di chiamata.  

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

### <a name="create-a-dial-plan"></a>Creare un piano di chiamata

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a  >  **Dial plan vocale.**
2. Fare **clic su** Aggiungi, quindi immettere un nome e una descrizione per il piano di chiamata.
    ![Screenshot che mostra la pagina Aggiungi per la creazione di un piano di chiamata](media/create-dial-plan.png)
3. In **Dettagli piano** di chiamata, specificare un prefisso di composizione esterno se gli utenti devono comporre una o più cifre iniziali aggiuntive (ad esempio 9) per ottenere una linea esterna. Procedi come segue.
    1. Nella casella **Prefisso composizione esterno** immettere un prefisso di composizione esterno. Il prefisso può essere un massimo di quattro caratteri (#,*, e 0-9).
    2. Attiva la **composizione del dispositivo ottimizzata.** Se si specifica un prefisso di composizione esterno, è necessario attivare questa impostazione anche per applicare il prefisso in modo che le chiamate possano essere effettuate all'esterno dell'organizzazione.
4. In **Base alle regole di** normalizzazione, configurare e associare una o più regole di [normalizzazione](what-are-dial-plans.md#normalization-rules) per il piano di chiamata. A ogni piano di chiamata deve essere associata almeno una regola di normalizzazione.  A questo scopo, eseguire una o più delle operazioni seguenti:
    - Per creare una nuova regola di normalizzazione e associarla al dial plan, fare clic su **Aggiungi** e quindi definire la regola.
    - Per modificare una regola di normalizzazione già associata al dial plan, selezionarla facendo clic a sinistra del nome della regola e quindi su **Modifica.** Apportare le modifiche desiderate e quindi fare clic su **Salva.**
    - Per rimuovere una regola di normalizzazione dal dial plan, selezionarla facendo clic a sinistra del nome della regola e quindi su **Rimuovi.**
5. Disporre le regole di normalizzazione nell'ordine desiderato. Fare **clic su Sposta** su o Sposta **giù** per cambiare la posizione delle regole nell'elenco.

    > [!NOTE]
    > Teams attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e usa la prima regola che corrisponde al numero composto. Se si imposta un piano di chiamata in modo che un numero composto corrisponda a più di una regola di normalizzazione, assicurarsi che le regole più restrittive siano ordinate sopra quelle meno restrittive.

6. Fare clic su **Salva**.
7. Per testare il piano di chiamata, in **Prova** piano di chiamata immettere un numero di telefono e quindi fare clic su **Prova.**

### <a name="edit-a-dial-plan"></a>Modificare un piano di chiamata

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a  >  **Dial plan vocale.**
2. Selezionare il piano di chiamata facendo clic a sinistra del nome del piano di chiamata e quindi facendo clic su **Modifica.**
3. Apportare le modifiche desiderate e quindi fare clic su **Salva.**

### <a name="assign-a-dial-plan-to-users"></a>Assegnare un piano di chiamata agli utenti

Per assegnare un piano di chiamata, devi utilizzare la stessa modalità di assegnazione dei criteri. [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>Utilizzo di PowerShell
  
### <a name="verify-and-start-remote-powershell"></a>Verificare e avviare una sessione remota di PowerShell

 **Verificare che sia in esecuzione Windows PowerShell 3.0 o versione successiva**
  
1. Per verificare che sia in esecuzione la versione 3.0 o successiva: accedere al **menu Start**  >  **Windows PowerShell.**
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o successiva, scaricare e installare gli aggiornamenti per Windows PowerShell. Vedere [Windows Management Framework 4.0 per](https://go.microsoft.com/fwlink/?LinkId=716845) scaricare e aggiornare Windows PowerShell alla versione 4.0. Quando richiesto, riavviare il computer.
    
4. Dovrai inoltre installare il modulo Windows PowerShell per Skype for Business online che ti consente di creare una sessione Windows PowerShell remota che si connette a Skype for Business online. Puoi scaricare questo modulo, supportato solo su computer a 64 bit, [nel modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688) Se richiesto, riavviare il computer.
    
Per altre informazioni, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in un'Windows PowerShell singola.](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)
  
 **Avviare una sessione di Windows PowerShell**
  
1. Fare **clic sul** pulsante Start  >  **Windows PowerShell.**
    
2. Nella finestra **Windows PowerShell** connessione a Microsoft 365 o Office 365 eseguendo:
    
 
    > [!NOTE]
    > Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.
    >
    > Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

    ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a>Creare e gestire i piani di chiamata

È possibile utilizzare un singolo cmdlet o uno script di PowerShell per creare e gestire i piani di chiamata dei tenant.
  
#### <a name="using-single-cmdlets"></a>Utilizzo di cmdlet singolo

- Per creare un nuovo piano di chiamata, eseguire:
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Per altri esempi e parametri, consultare[New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).
    
- Per modificare le impostazioni di un piano di chiamata esistente, eseguire:
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Per altri esempi e parametri, consultare[Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).
    
- Per aggiungere utenti a un piano di chiamata, eseguire:
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Per altri esempi e parametri, consultare [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).
    
- Per visualizzare le impostazioni di un piano di chiamata, eseguire:
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Per altri esempi e parametri, consultare [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).
    
- Per eliminare un piano di chiamata, eseguire:
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Per altri esempi e parametri, consultare [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).
    
- Per visualizzare le impostazioni dell'effettivo piano di chiamata, eseguire:
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Per altri esempi e parametri, consultare [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).
    
- Per testare le impostazioni effettive di un piano di chiamata, eseguire:
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Per altri esempi e parametri, consultare [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).
    
#### <a name="using-a-powershell-script"></a>Uso di uno script di PowerShell

Esegui questa procedura per eliminare una regola di normalizzazione associata a un piano di chiamata tenant senza dover prima eliminare il piano di chiamata tenant:
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Eseguire questo metodo per aggiungere la seguente regola di normalizzazione al piano di chiamata del tenant denominato RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Eseguire questa operazione per rimuovere la seguente regola di normalizzazione dal piano di chiamata del tenant denominato RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Eseguire quanto segue quando si desidera esaminare anche le regole di normalizzazione esistenti, determinare quale si desidera eliminare e quindi utilizzare l'indice per rimuoverla. Matrice delle regole di normalizzazione inizia con l'indice 0. Si desidera rimuovere la regola di normalizzazione a 3 cifre, in modo che sia indice 1.
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Eseguire questa operazione per trovare tutti gli utenti a cui è stato concesso il piano di chiamata del tenant RedmondDialPlan.
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Eseguire questa procedura per rimuovere tutti gli eventuali TenantDialPlan assegnati a tutti gli utenti che hanno hostingProvider di sipfed.online.lync.com.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

Eseguirli per aggiungere il piano di chiamata esistente locale denominato OPDP1 come un piano di chiamata del tenant per l'organizzazione. È necessario innanzitutto salvare il piano di chiamata del tenant locale in un file .xml e quindi utilizzarlo per creare il nuovo piano di chiamata del tenant.
  
Eseguire questa operazione per salvare il piano di chiamata del tenant locale nel file .xml.
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Eseguire questa operazione per creare il nuovo piano di chiamata del tenant.
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a>Argomenti correlati

- [Che cosa sono i piani di chiamata?](what-are-dial-plans.md)
- [Domande comuni sul trasferimento dei numeri di telefono](transferring-phone-numbers-common-questions.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)
- [Etichetta della dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
