---
title: Configurare il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace
author: CarolynRowe
ms.author: crowe
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Informazioni su come configurare il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 020fdd048b25dc015036e49d00858c106cf9a7af
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789181"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurare il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace

L'uso del componente aggiuntivo per le riunioni di Microsoft Teams consente agli utenti del calendario di Google di pianificare e partecipare a una riunione di Microsoft Teams direttamente da Google Workspace. Gli utenti avranno accesso alle funzionalità delle riunioni di Teams, tra cui video e audioconferenze, condivisione dello schermo, chat delle riunioni, lavagne digitali e altro ancora. Rimani connesso e organizzato per lavorare di più insieme tra il lavoro, la scuola e la vita privata.

Il componente aggiuntivo per la riunione di Microsoft Teams per Google Workspace deve essere abilitato da un amministratore di Teams prima che gli utenti tenant possano accedere all'app.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Abilitare o disabilitare il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace nel portale di Azure

Gli amministratori tenant possono abilitare o disabilitare un componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace dall'account di amministratore dell'organizzazione usando il portale di Azure.

Il componente aggiuntivo è abilitato per impostazione predefinita.

1. Accedi alla portale di Azure.

2. Selezionare **Applicazioni** >  Enterprise **Tutte le applicazioni**.

3. Cercare il **componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace**.

   ![portale di Azure che mostra tutte le applicazioni.](media/aad-add-google-workspace.png)

4. Seleziona **Sì**.

   ![portale di Azure con le proprietà dell'area di lavoro Google.](media/google-workspace-properties.png)

5. (Facoltativo) Per disabilitare il componente aggiuntivo, selezionare **No** invece di **Sì** nel passaggio 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Disabilitare il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace con PowerShell

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Set-AzureADServicePrincipal -ObjectId $servicePrincipal.ObjectId -AccountEnabled $false
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Get-AzureADServicePrincipal -Filter "appId eq '$appId'" | Set-AzureADServicePrincipal -AccountEnabled:$false
    Write-Host "Created and disabled the Service Principal \n"
}
```

Per altre informazioni, vedere [Creare un'entità servizio di Azure con Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Eliminare il componente aggiuntivo per la riunione di Microsoft Teams per Google Workspace

Per istruzioni, vedi la documentazione di [Google Eliminare un'app Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) .

## <a name="create-the-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Creare il componente aggiuntivo per la riunione di Microsoft Teams per Google Workspace con PowerShell

Se il componente aggiuntivo per la riunione di Microsoft Teams non è presente nel tenant, è possibile crearlo con PowerShell: 

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already
    Write-Host "The Service principal already exists"
} else {
    # Service principal does not yet exist, create it
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Write-Host "Created the Service Principal"
}
```
