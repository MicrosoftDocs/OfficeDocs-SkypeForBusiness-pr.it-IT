---
title: Passare da Business Voice a licenze di Teams Telefono
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Informazioni su come modificare le licenze Business Voice in licenze di Teams Telefono.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9e973d00761e62e62a3c749163f9e6dcaa8a636
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057096"
---
# <a name="move-from-business-voice-to-teams-phone-licenses"></a>Passare da Business Voice a licenze di Teams Telefono

Entro la fine di giugno 2022, Business Voice verrà ritirato, quindi [consigliamo alle aziende di passare a Telefono di Microsoft Teams con piano per chiamate licenze in bundle](https://techcommunity.microsoft.com/t5/small-and-medium-business-blog/teams-phone-with-calling-plan-available-in-33-markets-on-january/ba-p/2967643).

Business Voice ha raggruppato le tre licenze seguenti per i componenti aggiuntivi Teams:

- **Telefono di Microsoft Teams** per un Sistema telefonico basato sul cloud in Microsoft Teams.
- **Audioconferenza** per le conferenze telefoniche con accesso esterno e in uscita per le riunioni.
- **Piani per chiamate Microsoft** per le chiamate nazionali alla connettività PSTN (Public Switched Telephone Network).

I clienti Business Voice esistenti non verranno automaticamente convertiti nel nuovo modello di licenza.

Questo articolo è rivolto agli amministratori IT che devono modificare le licenze Business Voice per Telefono di Microsoft Teams e le licenze di Audioconferenza mantenendo le stesse funzionalità.

> [!WARNING]
> Seguire attentamente le istruzioni di questo articolo. Se le istruzioni indicano di NON selezionare il pulsante **Salva** , non selezionare il pulsante **Salva** .
>
> Il salvataggio anticipato può comportare la perdita delle assegnazioni dei numeri di telefono, dei piani di chiamata, degli operatori automatici e delle code di chiamata.

## <a name="acquire-new-licenses"></a>Acquisire nuove licenze

Prima di sostituire le licenze Business Voice, è necessario acquistare licenze sostitutive per gli utenti.

Sono necessarie licenze per fornire queste funzionalità:

- Audioconferenza
- Sistema telefonico basate sul cloud
- Connettività PSTN

Usare la tabella seguente per determinare le licenze da acquistare in base alle proprie esigenze:

| Vecchio piano di licenza | Piano di licenza consigliato | Descrizione |
| ---------------- | ------------------------ | ----------- |
| Business Voice con Piano per chiamate | Teams Telefono con piano per chiamate e audioconferenza di Microsoft Teams con chiamata in uscita verso USA/CAN | Offre funzionalità di Sistema telefonico basate sul cloud, un piano per le chiamate nazionali con Microsoft come provider PSTN e funzionalità di accesso in entrata e in uscita per i partecipanti alle riunioni organizzate da un utente con licenza. |
| Voce aziendale senza piano per chiamate | Teams Telefono Le audioconferenze Standard e Microsoft Teams con accesso esterno in uscita verso USA/CAN | Offre funzionalità di Sistema telefonico basate sul cloud che possono essere combinate con [un piano per chiamate di terze parti con un provider PSTN che usa funzionalità di routing Connessione con operatore diretto](pstn-connectivity.md) e accesso in entrata e in uscita per le riunioni organizzate da un utente con licenza. |

## <a name="how-to-update-licenses"></a>Come aggiornare le licenze

Sono disponibili quattro modi per aggiornare le licenze:

- Aggiornamento della licenza per singolo utente tramite interfaccia di amministrazione di Microsoft 365
- Aggiornamento delle licenze utente in blocco tramite interfaccia di amministrazione di Microsoft 365
- Aggiornamento della licenza utente in blocco con uno script di PowerShell
- Aggiornamento della licenza utente in blocco con licenze basate su gruppo di Azure

# <a name="option-1-single-user-in-admin-center"></a>[Opzione 1: singolo utente nell'interfaccia di amministrazione](#tab/single-user)

### <a name="option-1-single-user-license-update-via-microsoft-365-admin-center"></a>Opzione 1: aggiornamento della licenza per singolo utente tramite interfaccia di amministrazione di Microsoft 365

Per aggiornare un singolo utente, è possibile usare il interfaccia di amministrazione di Microsoft 365.

1. Passare a [admin.microsoft.com](https://admin.microsoft.com/) e accedere con le credenziali di amministratore tenant.
1. Passare a **Utenti** > **attivi e** selezionare l'utente desiderato.
1. Selezionare **Gestisci licenze di prodotto** sulla barra degli strumenti dell'elenco.
1. Nella schermata **Licenze e app** deselezionare la licenza Business Voice.
    > [!IMPORTANT]
    > NON salvare ancora le modifiche. Se si salvano le modifiche senza aggiungere le nuove licenze, il deprovisioning dell'account utente verrà annullato e il numero di telefono non verrà assegnato.
1. Dopo aver deselezionato Business Voice, controlla le nuove licenze per Teams Telefono e Audioconferenza.
1. Ora puoi salvare le modifiche in tutta sicurezza selezionando **Salva modifica**.

Le licenze dell'utente verranno aggiornate e non dovrebbero influire sulla disponibilità del servizio.

# <a name="option-2-bulk-users-in-admin-center"></a>[Opzione 2: utenti in blocco nell'interfaccia di amministrazione](#tab/bulk-users-admin-center)

### <a name="option-2-bulk-user-license-update-via-microsoft-365-admin-center"></a>Opzione 2: aggiornamento della licenza utente in blocco tramite interfaccia di amministrazione di Microsoft 365

Per aggiornare le licenze di più utenti in blocco, è possibile usare il interfaccia di amministrazione di Microsoft 365. Gli utenti selezionati avranno la stessa assegnazione del piano di licenza.

1. Passare a [admin.microsoft.com](https://admin.microsoft.com/) e accedere con le credenziali di amministratore tenant.
1. Passare a **Utenti** > **attivi e** selezionare tutti gli utenti desiderati.  
1. Selezionare **Gestisci licenze di prodotto** sulla barra degli strumenti dell'elenco.
1. Nella richiesta **Cosa si vuole fare con le licenze per questi utenti?** selezionare l'opzione **Sostituisci: Annulla assegnazione licenze esistenti e assegnane di nuove** .
    > [!IMPORTANT]
    > L'opzione **Sostituisci** rimuoverà tutte le licenze esistenti per gli utenti selezionati.  Di conseguenza, dovrai selezionare lo stato delle licenze desiderato per gli utenti, incluse eventuali altre licenze in uso, come Microsoft 365 Business Premium.
    >
    > Inoltre, se gli utenti selezionati hanno configurazioni di licenza di base diverse, verranno sovrascritte con le licenze selezionate, il che potrebbe influire su altre aree di Microsoft 365.
    >
    > Per i tenant con una configurazione di licenze miste, è consigliabile usare [l'opzione di aggiornamento in blocco con uno script di PowerShell](#option-3-bulk-user-license-update-using-a-powershell-script).
1. Nella schermata **Licenze e app** deselezionare la licenza Business Voice.
    > [!IMPORTANT]
    > NON salvare ancora le modifiche. Se si salvano le modifiche senza aggiungere le nuove licenze, gli account degli utenti selezionati verranno rimossi dal provisioning e il numero di telefono non sarà assegnato.
1. Dopo aver deselezionato Business Voice, controlla le nuove licenze per Teams Telefono e Audioconferenza.
1. Ora puoi salvare le modifiche in tutta sicurezza selezionando **Salva modifica**.
  Le licenze degli utenti verranno aggiornate e non dovrebbero influire sulla disponibilità del servizio.

# <a name="option-3-bulk-users-via-powershell"></a>[Opzione 3: utenti in blocco tramite PowerShell](#tab/powershell)

### <a name="option-3-bulk-user-license-update-using-a-powershell-script"></a>Opzione 3: aggiornamento della licenza utente in blocco con uno script di PowerShell

La sostituzione del piano di licenza Business Voice con uno script di PowerShell è una soluzione efficiente per la maggior parte degli scenari.  

Per usare questo metodo, seguire questa procedura generale:

1. Ottenere gli identificatori del piano di licenza specifico del tenant delle licenze Business Voice correnti.
1. Ottenere gli identificatori specifici del tenant dei nuovi piani di licenza di Teams Telefono e Audioconferenza.
1. Verificare se i nuovi piani di licenza hanno gli stessi piani di servizio della licenza Business Voice corrente.
1. Trovare gli utenti tenant con licenza per Business Voice (o modificare lo script per includere un filtro per selezionare un sottoinsieme di utenti, se necessario).
1. Aggiornare la configurazione della licenza degli utenti con i piani di Teams Telefono e Audioconferenza.

> [!IMPORTANT]
> Lo script fornito è un esempio di codice. Lo script non deve essere copiato così come è ed eseguito in un tenant di produzione senza test, convalida e personalizzazione per l'ambiente specifico.

### <a name="how-to-bulk-update-licenses-using-powershell"></a>Come aggiornare in blocco le licenze con PowerShell

1. Installare e importare il modulo di PowerShell di AzureAD.

    ```powershell
    Install-Module AzureAD
    Import-Module AzureAD
    ```

1. Connessione al tenant di Microsoft 365 e fornire le credenziali di amministratore del tenant.

    ```powershell
    Connect-AzureAD
    ```

1. Usare il commandlet seguente per elencare tutti i pacchetti di licenze nel tenant.

    ```powershell
    Get-AzureADSubscribedSku
    ```

1. Usare la tabella seguente per identificare il piano di licenza del componente aggiuntivo Business Voice che verrà sostituito.

    | Codice SKU | Tipo di licenza |
    | -------- | ------------ |
    | BUSINESS_VOICE_MED | Voce aziendale con piano per chiamate - Canada |
    | BUSINESS_VOICE | Voce aziendale con piano per chiamate - Regno Unito |
    | BUSINESS_VOICE_MED2_TELCO | Voce aziendale con piano per chiamate - Stati Uniti |
    | BUSINESS_VOICE_DIRECTROUTING | Voce aziendale senza piano per chiamate |
    | BUSINESS_VOICE_DIRECTROUTING_MED | Voce aziendale senza piano per chiamate - Stati Uniti |

    > [!NOTE]
    > Lo script fornito in questo documento presuppone che nel tenant sia presente un unico codice SKU per voce aziendale.  
    >
    > Se si hanno più SKU business voice, è necessario modificare lo script o eseguirlo più volte, una volta per ogni codice SKU.

1. Creare una variabile di PowerShell denominata `$skuSourceBV`.
    1. Assicurarsi di sostituire l'etichetta con il `SkuPartNumber` codice SKU Business Voice del tenant.
    1. In questo esempio viene usato il `BUSINESS_VOICE_MED2_TELCO` codice SKU.

    ```powershell
    $skuSourceBV = Get-AzureADSubscribedSku  | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
    ```

1. Utilizza la tabella seguente per identificare i nuovi codici SKU della licenza di Teams Telefono e audioconferenza.

    | Codice SKU | Tipo di licenza |
    | -------- | ------------ |
    | MCOTEAMS_ESSENTIALS | Servizi telefonici con piano per chiamate |
    | MCOEV | Teams Telefono Standard (Nessun piano per chiamate) |
    | MCOMEETADV | Audioconferenza |
    | Microsoft_Teams_Audio_Conferencing_select_dial_out | Microsoft Teams Chiamata in uscita selezionata per i servizi di audioconferenza |

1. Creare variabili PowerShell per archiviare i codici SKU univoci di Teams Telefono e audioconferenza.
    1. Assicurarsi di sostituire l'etichetta `SkuPartNumber` con i codici SKU disponibili nel tenant.
    1. In questo esempio vengono usati i `MCOTEAM_ESSENTIALS` codici e `MCOMEETADV` SKU.

        ```powershell
        $skuTargetTPCP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
        $skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"} 
        ```

1. Eseguire questo script per raccogliere i dati necessari del piano di servizio dallo SKU di origine in oggetti univoci.

     ```powershell
     $servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
    $servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
    $servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}
    ```

1. Prima di procedere, verificare se gli SKU di origine (Voce aziendale) e gli SKU di destinazione (Teams Telefono e Audioconferenza) hanno gli stessi piani di servizio inclusi.
    1. Una mancata corrispondenza può attivare una modifica della licenza che potrebbe interrompere i servizi di audioconferenza e voce degli utenti.
    2. Creare variabili per verificare se tutti i piani di servizio nello SKU di origine verranno sostituiti con lo stesso piano di servizio di destinazione.

        ```powershell
        $validated_TP = $false
        $validated_AC = $false
        $validated_CP = $false
        ```

    3. Se la licenza Business Voice di origine non include alcun piano per le chiamate, non verificarlo.

        ```powershell
        if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }
        ```

    4. Verificare se tutti i piani di servizio in SKU di origine hanno un piano di servizio corrispondente in SKU di destinazione.

        ```powershell
        For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) {
        if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
        if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
        if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
        }
        ```

    5. Se è presente un piano di servizio mancante nello SKU di destinazione, è possibile interrompere la disponibilità del servizio per gli utenti e lo script dovrebbe interrompere l'elaborazione.

        ```powershell
        if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit }
        if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit }
        if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit }
        ```

1. Se l'aspetto è corretto, preparare gli oggetti di PowerShell per eseguire le operazioni di aggiornamento sugli oggetti utente. Usare l'oggetto `AssignedLicenses` per questo.

    ```powershell
    $LicenseAddTPCP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddTPCP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTPCP.SkuPartNumber -EQ).SkuID
    $LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
    
    $LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
    $LicensesToUpdate.AddLicenses += ($LicenseAddTPCP)
    $LicensesToUpdate.AddLicenses += ($LicenseAddAC)
    $LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID
    ```

1. Quindi, ottenere l'elenco degli utenti a cui sono assegnate le licenze Business Voice e archiviarlo in un elenco denominato `$usersLicensedOldSKU`.

    ```powershell
    $usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
    
    Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }
    ```

1. Ora, usando il nuovo elenco di utenti, esegui un'attività di aggiornamento per rimuovere le licenze Business Voice e aggiungere le licenze di Teams Telefono e Audioconferenza, usando l'oggetto ``$LicensesToUpdate`` creato in precedenza.

    ```powershell
    $usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
    ```

> [!NOTE]
> Se non disponi di licenze di Teams Telefono e/o audioconferenze sufficienti per sostituire Business Voice, verrà visualizzato l'errore **La sottoscrizione con guid SKU non ha alcuna licenza disponibile** durante l'assegnazione dell'utente non appena il pool di licenze è esaurito.

### <a name="full-script"></a>Script completo

```powershell
#Install the AzureAD module when required
Install-Module AzureAD
#Import the AzureAD module so you can use the commandlets
Import-Module AzureAD

#Connect to your tenant
Connect-AzureAD

#When necessary, uncomment and use this commandlet to list all the licenses in the tenant and identify which license packages are required
#Get-AzureADSubscribedSku

##Replace the SKU codes below to match your desired scenario
$skuSourceBV = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
$skuTargetTP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
$skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"}

##Replace the SKU codes below to match your desired scenario
$servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
$servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
$servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}

##Create variables to validate if all Service Plans in the source SKU will be replaced with the same target service plan
$validated_TP = $false
$validated_AC = $false
$validated_CP = $false

##If source Business Voice has no Calling Plan included, do not check
if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }

##Verify if all service plans in source SKU have a matching service plan in target SKU
For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) { 
    if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
    if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
    if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
}

##If there's a missing service plan in the target sku, we might impact service availability for a user and therefore stop processing
if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit } 
if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit } 
if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit } 


##Prepare variables and update
$LicenseAddTP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddTP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTP.SkuPartNumber -EQ).SkuID
$LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
$LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToUpdate.AddLicenses += ($LicenseAddTP)
$LicensesToUpdate.AddLicenses += ($LicenseAddAC)
$LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID

$usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }

$usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
```

# <a name="option-4-bulk-users-with-azure-group-based-licensing"></a>[Opzione 4: utenti in blocco con licenze basate su gruppo di Azure](#tab/azure-licensing)

### <a name="option-4-bulk-user-license-update-using-azure-group-based-licensing"></a>Opzione 4: aggiornamento della licenza utente in blocco con licenze basate su gruppo di Azure

La gestione delle licenze basata su gruppo di Azure consente di assegnare sottoscrizioni e piani di servizio a un gruppo.

Questo metodo assicura che:

- Le licenze vengono assegnate a tutti i membri del gruppo.
- A tutti i nuovi membri che entrano a far parte del gruppo vengono assegnate le licenze appropriate.
- Quando i membri vengono rimossi dal gruppo, vengono rimosse anche quelle licenze.

Sarà necessario convalidare [i requisiti di licenza per le licenze basate su gruppo](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

> [!NOTE]
> Per questo metodo, gli aggiornamenti delle licenze devono essere elaborati in un unico passaggio.
>
> È consigliabile compilare un elenco di gruppi esistenti a cui sono assegnate licenze Business Voice, selezionare prima un piccolo gruppo di utenti di test e sostituire l'assegnazione del piano di licenza con i nuovi piani di licenza preferiti.

### <a name="how-to-bulk-update-licenses-using-group-based-licensing"></a>Come aggiornare in blocco le licenze usando le licenze basate su gruppo

1. Passare a [portal.azure.com](https://portal.azure.com) e accedere con le credenziali di amministratore.
1. Vai a **Azure Active Directory** e nel menu a sinistra seleziona **Licenze**.
1. Per verificare quali gruppi hanno licenze Business Voice assegnate, scegliere **Tutti i prodotti** e selezionare il piano Voce aziendale.
1. Selezionare **Gruppi con licenza** o **Utenti con licenza**. L'elenco dei gruppi con licenza è disponibile nel riquadro a destra.
1. Selezionare il nome del gruppo per aprire i dettagli dell'assegnazione di gruppo.
1. Selezionare **Attività** per modificare le licenze assegnate a questo gruppo.
1. Selezionare le caselle di fronte ai piani di licenza acquistati per sostituire Business Voice.
1. Deselezionare la casella di controllo davanti al piano di licenza Microsoft 365 Business Voice.
1. Selezionare **Salva**.
1. Tornare al gruppo selezionando il nome del gruppo. Verrà visualizzato un banner che indica che **le modifiche alla licenza sono in sospeso**.
1. Selezionare **Rielaborazione** per forzare l'aggiornamento dell'assegnazione della licenza.

---

## <a name="validate-user-license-updates"></a>Convalidare gli aggiornamenti delle licenze utente

Dopo aver completato il metodo scelto, verificare se le licenze utente sono state aggiornate correttamente.

1. Passare alla [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) e accedere con le credenziali di amministratore.
1. Passare a **Utenti** > **attivi** e selezionare un utente di prova.
1. Selezionare **Gestisci licenze di prodotto** sulla barra degli strumenti.
1. Nella schermata **Licenze e app** verificare quali licenze sono state assegnate.

Se a tutti gli utenti assegnati sono assegnate le licenze corrette, hai completato l'aggiornamento delle licenze Business Voice alle licenze di Teams Telefono e Audioconferenza.
