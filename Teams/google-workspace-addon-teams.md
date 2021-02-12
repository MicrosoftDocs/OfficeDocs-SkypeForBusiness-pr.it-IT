---
title: Configurare il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Informazioni su come configurare il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880877"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurare il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace

Il componente aggiuntivo per le riunioni di Microsoft Teams consente agli utenti di Google Calendar di pianificare e partecipare a una riunione di Microsoft Teams direttamente da Google Workspace. Gli utenti avranno accesso alle funzionalità per le riunioni di Teams, tra cui le audioconferenze e video, la condivisione dello schermo, la chat delle riunioni, le lavagne digitali e altro ancora. Restare connessi e organizzati per essere più eserciti insieme tra lavoro, scuola e vita privata.

Il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace deve essere abilitato da un amministratore di Teams prima che gli utenti del tenant possano accedere all'app.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Abilitare o disabilitare il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace nel portale di Azure

L'amministratore del tenant può abilitare o disabilitare un componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace dall'account di amministratore dell'organizzazione tramite il portale di Azure.

Il componente aggiuntivo è abilitato per impostazione predefinita.

1. Accedi al portale di Azure.

2. Selezionare **Applicazioni Enterprise** Tutte le  >  **applicazioni.**

3. Cercare il componente **aggiuntivo per le riunioni di Microsoft Teams per Google Workspace.**

   ![Portale di Azure con tutte le applicazioni](media/aad-add-google-workspace.png)

4. Selezionare **Sì.**

   ![Portale di Azure con le proprietà dell'area di lavoro di Google](media/google-workspace-properties.png)

5. (Facoltativo) Per disabilitare il componente aggiuntivo, selezionare **No** invece di **Sì** nel passaggio 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Disabilitare il componente aggiuntivo per le riunioni di Microsoft Teams per l'area di lavoro di Google con PowerShell

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
    $servicePrincipal = New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName -AccountEnabled $false
    Write-Host "Created and disabled the Service Principal \n"
}
```

Per altre informazioni, vedere [Creare un'entità servizio di Azure con Azure PowerShell.](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Eliminare il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace

Per istruzioni, vedere la documentazione di Google [Elimina un'app Google Workspace Marketplace.](https://support.google.com/a/answer/6216211?hl=en)
