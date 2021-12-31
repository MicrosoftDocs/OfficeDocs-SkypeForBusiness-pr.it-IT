---
title: Configurare il Microsoft Teams riunione per Google Workspace
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Scopri come configurare il componente aggiuntivo Microsoft Teams riunione per Google Workspace.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5b3d873dd327be4cbc28d4d979ad06cb6f9c9ea
ms.sourcegitcommit: 9ed5aecbf671accae93ac5084ad7875e82e3858b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2021
ms.locfileid: "61648884"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurare il Microsoft Teams riunione per Google Workspace

L'Microsoft Teams per le riunioni consente agli utenti del calendario di Google di pianificare e partecipare a una riunione Microsoft Teams direttamente da Google Workspace. Gli utenti potranno accedere alle funzionalità Teams riunioni, tra cui videoconferenze e audioconferenze, condivisione dello schermo, chat delle riunioni, lavagne digitali e altro ancora. Rimani connesso e organizzato per lavorare di più insieme in tutto il lavoro, la scuola e la vita.

Il Microsoft Teams per le riunioni di Google Workspace deve essere abilitato da un amministratore Teams prima che gli utenti del tenant possano accedere all'app.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Abilitare o disabilitare Microsoft Teams componente aggiuntivo riunione per Google Workspace nel portale di Azure

L'amministratore del tenant può abilitare o disabilitare un componente aggiuntivo Microsoft Teams riunione per Google Workspace dall'account di amministratore dell'organizzazione usando il portale di Azure.

Il componente aggiuntivo è abilitato per impostazione predefinita.

1. Accedere al portale di Azure.

2. Selezionare **Enterprise tutte le**  >  **applicazioni.**

3. Cercare il **componente aggiuntivo Microsoft Teams riunione per Google Workspace.**

   ![Portale di Azure che mostra tutte le applicazioni.](media/aad-add-google-workspace.png)

4. Selezionare **Sì**.

   ![Portale di Azure che mostra le proprietà dell'area di lavoro di Google.](media/google-workspace-properties.png)

5. (Facoltativo) Per disabilitare il componente aggiuntivo, selezionare **No** invece **di Sì** nel passaggio 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Disabilitare Microsoft Teams componente aggiuntivo riunione per Google Workspace con PowerShell

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

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Eliminare il componente aggiuntivo Microsoft Teams riunione per Google Workspace

Per istruzioni, vedere la documentazione di Google [Eliminare un'app Google Workspace Marketplace.](https://support.google.com/a/answer/6216211?hl=en)

## <a name="create-the-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Creare il componente aggiuntivo Microsoft Teams riunione per Google Workspace usando PowerShell

Se il componente aggiuntivo Microsoft Teams riunione non è presente nel tenant, è possibile crearlo usando PowerShell:In case the Microsoft Teams meeting add-on is not present in your tenant, you can create it using PowerShell: 

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
