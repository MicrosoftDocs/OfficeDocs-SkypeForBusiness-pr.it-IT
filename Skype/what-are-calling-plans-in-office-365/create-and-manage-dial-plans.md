---
title: "Creare e gestire i dial plan"
ms.author: tonysmit
author: tonysmit
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
description: "Learn how to create calling dial plans (PSTN Calling dial plans) in Office 365 and how to manage them. "
---

# Creare e gestire i dial plan

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](7af17c94-5f8f-4452-ae1d-01f495b4dc94.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/7af17c94-5f8f-4452-ae1d-01f495b4dc94). 
  
Dopo aver pianificato dial plan per l'organizzazione e rapida tutte le regole di normalizzazione che devono essere creato per il routing delle chiamate, è necessario utilizzare Windows PowerShell per creare il dial plan e apportare modifiche alle impostazioni.
  
> [!NOTE]
> Non è possibile utilizzare l'interfaccia di amministrazione di Skype for Business per la creazione e la gestione di piani di chiamata. 
  
## Verifica e avvio di una sessione remota di PowerShell

 **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
  
1. A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
 **Avviare una sessione di Windows PowerShell**
  
1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:
    
    > [!NOTE]
    > Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Per altre informazioni sull'avvio di Windows PowerShell, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o[Connessione a Skype for Business online con Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
## Creazione e gestione dei piani di chiamata

Per creare e gestire piani di chiamata di ambito tenant puoi utilizzare un singolo cmdlet oppure uno script di PowerShell.
  
### Utilizzo di singoli cmdlet

- Per creare un nuovo piano di chiamata, eseguire:
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Per altri esempi e parametri, vedi [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).
    
- Per apportare modifiche alle impostazioni per un dial plan esistente, eseguire:
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Per altri esempi e parametri, vedi [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).
    
- Per aggiungere utenti a un piano di chiamata, eseguire:
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Per altri esempi e parametri, vedi [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).
    
- Per visualizzare le impostazioni in un dial plan, eseguire:
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Per altri esempi e parametri, vedi [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).
    
- Per eliminare un dial plan, eseguire:
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Per altri esempi e parametri, vedi [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).
    
- Per visualizzare le impostazioni del plan efficace, eseguire:
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Per altri esempi e parametri, vedi [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).
    
- Per testa le impostazioni del piano di chiamata effettivo, eseguire:
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    Per altri esempi e parametri, vedi [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).
    
### Utilizzo di uno script di PowerShell

Esegui lo script riportato di seguito per eliminare una regola di normalizzazione associata a un piano di chiamata di ambito tenant senza dover prima eliminare il piano di chiamata:
  
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
```

```
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
```

```
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```

Eseguire questa operazione per aggiungere la seguente regola normalizzazione denominato RedmondDialPlan tenant dial plan esistente.
  
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```

Esegui lo script riportato di seguito per rimuovere la seguente regola di normalizzazione dal piano di chiamata esistente denominato "RedmondDialPlan".
  
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
```

```
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

Eseguire le operazioni seguenti quando si desidera esaminare anche le regole di normalizzazione esistente, determinare quello che si desidera eliminare e quindi usare il relativo indice per rimuoverla. Matrice di regole di normalizzazione inizia con indice 0. Si desidera rimuovere la regola di normalizzazione a 3 cifre, in modo che sia indice 1.
  
```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
```

```
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
```

```
$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Esegui lo script riportato di seguito per trovare tutti gli utenti a cui è stato assegnato il piano di chiamata di ambito tenant denominato "RedmondDialPlan".
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Eseguire operazioni per aggiungere che dial plan denominata OPDP1 come un dial plan tenant per l'organizzazione dei locale esistente. È necessario innanzitutto Salva locale nel dial plan in un file XML di e quindi utilizzarla per creare il nuovo tenant dial plan.
  
Eseguire questa operazione per salvare il dial plan locale in un file XML.
  
```
$DPName = "OPDP1"
```

```
$DPFileName = "dialplan.xml"
```

```
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Esegui questo script per creare il nuovo piano di chiamata di ambito tenant.
  
```
$DPFileName = "dialplan.xml"
```

```
$DP = Import-Clixml $DPFileName
```

```
$NormRules = @()
```

```
ForEach($nr in $dp.NormalizationRules)
```

```
{
```

```
 $id1 = "Global/" +$nr.Name
```

```
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
```

```
$NormRules += $nr2
```

```
}
```

```
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```

## Per saperne di più su Windows PowerShell

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

