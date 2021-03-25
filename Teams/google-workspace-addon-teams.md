---
title: Configurare il componente aggiuntivo Riunione di Microsoft Teams per Google Workspace
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
ms.openlocfilehash: 6e1b7024190ac51b89e09fafced86ffea13f5961
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120697"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurare il componente aggiuntivo Riunione di Microsoft Teams per Google Workspace

L'uso del componente aggiuntivo Per le riunioni di Microsoft Teams consente agli utenti del calendario di Google di pianificare e partecipare a una riunione di Microsoft Teams direttamente da Google Workspace. Gli utenti potranno accedere alle funzionalità delle riunioni di Teams, tra cui videoconferenze e audioconferenze, condivisione dello schermo, chat delle riunioni, lavagne digitali e altro ancora. Rimani connesso e organizzato per lavorare di più insieme in tutto il lavoro, la scuola e la vita.

Il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace deve essere abilitato da un amministratore di Teams prima che gli utenti del tenant possano accedere all'app.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Abilitare o disabilitare il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace nel portale di Azure

L'amministratore tenant può abilitare o disabilitare un componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace dall'account di amministratore dell'organizzazione usando il portale di Azure.

Il componente aggiuntivo è abilitato per impostazione predefinita.

1. Accedere al portale di Azure.

2. Selezionare **Applicazioni aziendali Tutte** le  >  **applicazioni**.

3. Cercare il **componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace.**

   ![Portale di Azure che mostra tutte le applicazioni](media/aad-add-google-workspace.png)

4. Selezionare **Sì**.

   ![Portale di Azure che mostra le proprietà dell'area di lavoro di Google](media/google-workspace-properties.png)

5. (Facoltativo) Per disabilitare il componente aggiuntivo, selezionare **No** invece **di Sì** nel passaggio 4.

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
    $servicePrincipal = New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName -AccountEnabled $false
    Write-Host "Created and disabled the Service Principal \n"
}
```

Per altre informazioni, vedere [Creare un'entità servizio di Azure con Azure PowerShell.](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Eliminare il componente aggiuntivo per le riunioni di Microsoft Teams per Google Workspace

Per istruzioni, vedere la documentazione di Google [Eliminare un'app Google Workspace Marketplace.](https://support.google.com/a/answer/6216211?hl=en)