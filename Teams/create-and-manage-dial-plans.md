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
description: Informazioni su come usare l'interfaccia di amministrazione di Microsoft teams o Windows PowerShell per creare e gestire piani di chiamata (piani di chiamate PSTN).
ms.openlocfilehash: 50cdbaf9fd1e5ae10eca20c0f547dce29d606983
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902021"
---
# <a name="create-and-manage-dial-plans"></a>Creare e impostare piani di chiamata

Dopo aver pianificato i dial plan per l'organizzazione e aver individuato tutte le regole di normalizzazione che devono essere create per il routing delle chiamate, si è pronti per creare i dial plan. È possibile usare l'interfaccia di amministrazione di Microsoft teams o Windows PowerShell per creare e gestire piani di chiamata.  

## <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

### <a name="create-a-dial-plan"></a>Creare un dial plan

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Voice** > **dial plan**.
2. Fare clic su **Aggiungi**e quindi immettere un nome e una descrizione per il dial plan.
    ![Schermata che mostra la pagina Aggiungi per la creazione di un dial plan](media/create-dial-plan.png)
3. In **Dettagli dial plan**specificare un prefisso di chiamata esterna se gli utenti devono chiamare una o più cifre iniziali aggiuntive (ad esempio, 9) per ottenere una linea esterna. Procedi come segue.
    1. Nella casella **prefisso di chiamata esterna** immettere un prefisso per la chiamata esterna. Il prefisso può contenere fino a quattro caratteri (#, * e 0-9).
    2. Attivare la **chiamata a dispositivi ottimizzati**. Se si specifica un prefisso di chiamata esterna, è necessario attivare anche questa impostazione per applicare il prefisso, in modo che le chiamate possano essere effettuate all'esterno dell'organizzazione.
4. In **regole di normalizzazione**configurare e associare una o più [regole di normalizzazione](what-are-dial-plans.md#normalization-rules) per il dial plan. A ogni dial plan deve essere associata almeno una regola di normalizzazione.  A questo scopo, eseguire una o più delle operazioni seguenti:
    - Per creare una nuova regola di normalizzazione e associarla al dial plan, fare clic su **Aggiungi**e quindi definire la regola.
    - Per modificare una regola di normalizzazione già associata al dial plan, selezionare la regola facendo clic a sinistra del nome della regola, quindi fare clic su **modifica**. Apportare le modifiche desiderate e quindi fare clic su **Salva**.
    - Per rimuovere una regola di normalizzazione dal dial plan, selezionare la regola facendo clic a sinistra del nome della regola, quindi fare clic su **Rimuovi**.
5. Disporre le regole di normalizzazione nell'ordine desiderato. Fare clic su spostarsi verso l' **alto** o spostarsi verso il **basso** per modificare la posizione delle regole nell'elenco.

    > [!NOTE]
    > Teams attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato. Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, verificare che le regole più restrittive siano ordinate sopra quelle meno restrittive.

6. Fare clic su **Salva**.
7. Se si vuole testare il dial plan, in **dial plan di prova**immettere un numero di telefono e quindi fare clic su **test**.

### <a name="edit-a-dial-plan"></a>Modificare un dial plan

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Voice** > **dial plan**.
2. Selezionare il dial plan facendo clic a sinistra del nome del dial plan, quindi fare clic su **modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Salva**.

### <a name="add-users-to-a-dial-plan"></a>Aggiungere utenti a un dial plan

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**.
2. Selezionare l'utente facendo clic sul nome visualizzato.
3. Selezionare la scheda **criteri** .
4. Fare clic su **modifica** a destra dei criteri assegnati.
5. Nel menu a discesa **dial plan** selezionare il dial plan che si vuole assegnare all'utente e quindi fare clic su **applica**.

## <a name="using-powershell"></a>Utilizzo di PowerShell
  
### <a name="verify-and-start-remote-powershell"></a>Verificare e avviare Remote PowerShell

 **Verificare che sia in esecuzione Windows PowerShell versione 3,0 o successiva**
  
1. Per verificare che sia in esecuzione la versione 3,0 o successiva: **menu** > Start di**Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3,0 o successiva, scaricare e installare gli aggiornamenti in Windows PowerShell. Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0. Riavviare il computer quando viene richiesto.
    
4. È inoltre necessario installare il modulo Windows PowerShell per Skype for business online che consente di creare una sessione remota di Windows PowerShell che si connette a Skype for business online. Puoi scaricare questo modulo, supportato solo in computer a 64 bit, nel [modulo di Windows PowerShell per Skype for business online](https://go.microsoft.com/fwlink/?LinkId=294688). Riavviare il computer se richiesto.
    
Per altre informazioni, vedere [connettersi a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).
  
 **Avviare una sessione di Windows PowerShell**
  
1. Fare clic su **Avvia** > **Windows PowerShell**.
    
2. Nella finestra di **Windows PowerShell** connettersi a Microsoft 365 o Office 365 eseguendo:
    
    > [!NOTE]
    > Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
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
    
- Per modificare le impostazioni di un dial plan esistente, eseguire:
    
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

Esegui questa operazione per eliminare una regola di normalizzazione associata a un dial plan tenant senza dover eliminare prima di tutto il piano di chiamata del tenant:
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

Esegui questa operazione per rimuovere eventuali TenantDialPlan assegnati da tutti gli utenti che hanno un provider dihosting di sipfed.online.lync.com.
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
- [Etichetta Disclaimer per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
