---
title: Creare e impostare dial plan
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
description: Informazioni su come usare l'interfaccia di amministrazione di Microsoft Teams o Windows PowerShell per creare e gestire i dial plan (piani di chiamata PSTN).
ms.openlocfilehash: 0b2c8c64d1e4e01843c6565d43a07e0ebdb24d71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120808"
---
# <a name="create-and-manage-dial-plans"></a>Creare e impostare dial plan

Dopo aver programmato i dial plan per l'organizzazione e aver trovato tutte le regole di normalizzazione che devono essere create per il routing delle chiamate, è possibile creare i dial plan. È possibile usare l'interfaccia di amministrazione di Microsoft Teams o Windows PowerShell per creare e gestire i piani di chiamata.  

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

### <a name="create-a-dial-plan"></a>Creare un piano di chiamata

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Piano di**  >  **chiamata vocale.**
2. Fare **clic su** Aggiungi e quindi immettere un nome e una descrizione per il piano di chiamata.
    ![Screenshot che mostra la pagina Aggiungi per la creazione di un dial plan](media/create-dial-plan.png)
3. In **Dettagli piano di** chiamata specificare un prefisso di composizione esterno se gli utenti devono comporre una o più cifre iniziali aggiuntive , ad esempio 9, per ottenere una linea esterna. Procedi come segue.
    1. Nella casella **Prefisso di composizione esterno** immettere un prefisso di composizione esterno. Il prefisso può contenere fino a quattro caratteri (#,*, e 0-9).
    2. Attivare la **composizione ottimizzata del dispositivo**. Se si specifica un prefisso di composizione esterno, è necessario attivare questa impostazione anche per applicare il prefisso in modo che le chiamate possano essere effettuate all'esterno dell'organizzazione.
4. In **Regole di normalizzazione** configurare e associare una o più regole [di normalizzazione](what-are-dial-plans.md#normalization-rules) per il piano di chiamata. A ogni piano di chiamata deve essere associata almeno una regola di normalizzazione.  A questo scopo, eseguire una o più delle operazioni seguenti:
    - Per creare una nuova regola di normalizzazione e associarla al dial plan, fare clic su **Aggiungi** e quindi definire la regola.
    - Per modificare una regola di normalizzazione già associata al dial plan, selezionarla facendo clic a sinistra del nome della regola e quindi su **Modifica.** Apportare le modifiche desiderate e quindi fare clic su **Salva.**
    - Per rimuovere una regola di normalizzazione dal dial plan, selezionarla facendo clic a sinistra del nome della regola e quindi su **Rimuovi.**
5. Disporre le regole di normalizzazione nell'ordine desiderato. Fare **clic su Sposta su** o Sposta **giù** per modificare la posizione delle regole nell'elenco.

    > [!NOTE]
    > Teams attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e usa la prima regola che corrisponde al numero composto. Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, assicurarsi che le regole più restrittive siano ordinate al di sopra di quelle meno restrittive.

6. Fare clic su **Salva**.
7. Se si vuole testare il piano di chiamata, in **Test piano di chiamata** immettere un numero di telefono e quindi fare clic su **Test**.

### <a name="edit-a-dial-plan"></a>Modificare un piano di chiamata

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Piano di**  >  **chiamata vocale.**
2. Selezionare il piano di chiamata facendo clic a sinistra del nome del dial plan e quindi fare clic su **Modifica.**
3. Apportare le modifiche desiderate e quindi fare clic su **Salva.**

### <a name="assign-a-dial-plan-to-users"></a>Assegnare un piano di chiamata agli utenti

Assegnare un piano di chiamata nello stesso modo in cui si assegnano i criteri. [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>Utilizzo di PowerShell
  
### <a name="start-powershell"></a>Avviare PowerShell
- Aprire un Windows PowerShell comando ed eseguire i comandi seguenti:

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a>Creare e gestire i dial plan

È possibile utilizzare un singolo cmdlet o uno script di PowerShell per creare e gestire i piani di chiamata dei tenant.
  
#### <a name="using-single-cmdlets"></a>Utilizzo di cmdlet singolo

- Per creare un nuovo piano di chiamata, eseguire:
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Per altri esempi e parametri, consultare[New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).
    
- Per modificare le impostazioni di un piano di chiamata esistente, eseguire:
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Per altri esempi e parametri, consultare[Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).
    
- Per aggiungere utenti a un piano di chiamata, eseguire:
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Per altri esempi e parametri, consultare [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).
    
- Per visualizzare le impostazioni di un piano di chiamata, eseguire:
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Per altri esempi e parametri, consultare [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).
    
- Per eliminare un piano di chiamata, eseguire:
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Per altri esempi e parametri, consultare [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).
    
- Per visualizzare le impostazioni dell'effettivo piano di chiamata, eseguire:
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Per altri esempi e parametri, consultare [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).
    
- Per testare le impostazioni effettive di un piano di chiamata, eseguire:
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Per altri esempi e parametri, consultare [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).
    
#### <a name="using-a-powershell-script"></a>Uso di uno script di PowerShell

Eseguire questa operazione per eliminare una regola di normalizzazione associata a un piano di chiamata tenant senza prima eliminare il piano di chiamata del tenant:
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

Esegui questa operazione per rimuovere qualsiasi TenantDialPlan assegnato da tutti gli utenti che hanno un HostingProvider di sipfed.online.lync.com.
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
- [Domande comuni sul trasferimento dei numeri di telefono](./phone-number-calling-plans/port-order-overview.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)
- [Etichetta di esclusione di responsabilità per chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)