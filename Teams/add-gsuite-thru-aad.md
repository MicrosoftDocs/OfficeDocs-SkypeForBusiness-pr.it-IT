---
title: Configurare il componente aggiuntivo riunione Microsoft teams per Google Workspace
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
description: Informazioni su come configurare il componente aggiuntivo riunione Microsoft teams per Google Workspace.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 882ed439f8bba27b1cf0c14056c146267cacd359
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/24/2020
ms.locfileid: "49387295"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurare il componente aggiuntivo riunione Microsoft teams per Google Workspace

L'uso del componente aggiuntivo riunione Microsoft teams consente agli utenti di Google Calendar di pianificare e partecipare a una riunione Microsoft teams direttamente da Google Workspace. Gli utenti avranno accesso alle funzionalità delle riunioni di Team, tra cui servizi di conferenza video e audio, condivisione dello schermo, chat di riunione, lavagne digitali e altro ancora. Rimanere connessi e organizzati per ottenere di più insieme il lavoro, la scuola e la vita.

Il componente aggiuntivo riunione Microsoft teams per Google Workspace deve essere abilitato da un amministratore di teams prima che gli utenti del tenant possano accedere all'app.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Abilitare o disabilitare il componente aggiuntivo riunione Microsoft teams per Google Workspace in Azure Portal

In qualità di amministratore del tenant, puoi abilitare o disabilitare un componente aggiuntivo riunione di Microsoft teams per Google Workspace dall'account di amministratore dell'organizzazione usando il portale di Azure.

Il componente aggiuntivo è abilitato per impostazione predefinita.

1. Accedere a Azure Portal.

2. Selezionare **applicazioni aziendali**  >  **tutte le applicazioni**.

3. Cercare **il componente aggiuntivo riunione Microsoft teams per Google Workspace**.

   ![Portale di Azure che Mostra tutte le applicazioni](media/aad-add-google-workspace.png)

4. Selezionare **Sì**.

   ![Portale di Azure che mostra le proprietà di Google Workspace](media/google-workspace-properties.png)

5. Opzionale Per disabilitare il componente aggiuntivo, selezionare **No** invece di **Sì** nel passaggio 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Disabilitare il componente aggiuntivo riunione Microsoft teams per Google Workspace tramite PowerShell

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

Per altre informazioni, vedere [creare un'entità di servizio di Azure con Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Eliminare il componente aggiuntivo riunione Microsoft teams per Google Workspace

Per istruzioni, vedi la documentazione di Google per [eliminare un'app di Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) .
