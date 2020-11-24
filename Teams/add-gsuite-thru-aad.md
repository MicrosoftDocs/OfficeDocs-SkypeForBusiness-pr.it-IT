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
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="0db73-103">Configurare il componente aggiuntivo riunione Microsoft teams per Google Workspace</span><span class="sxs-lookup"><span data-stu-id="0db73-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="0db73-104">L'uso del componente aggiuntivo riunione Microsoft teams consente agli utenti di Google Calendar di pianificare e partecipare a una riunione Microsoft teams direttamente da Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="0db73-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="0db73-105">Gli utenti avranno accesso alle funzionalità delle riunioni di Team, tra cui servizi di conferenza video e audio, condivisione dello schermo, chat di riunione, lavagne digitali e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="0db73-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="0db73-106">Rimanere connessi e organizzati per ottenere di più insieme il lavoro, la scuola e la vita.</span><span class="sxs-lookup"><span data-stu-id="0db73-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="0db73-107">Il componente aggiuntivo riunione Microsoft teams per Google Workspace deve essere abilitato da un amministratore di teams prima che gli utenti del tenant possano accedere all'app.</span><span class="sxs-lookup"><span data-stu-id="0db73-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="0db73-108">Abilitare o disabilitare il componente aggiuntivo riunione Microsoft teams per Google Workspace in Azure Portal</span><span class="sxs-lookup"><span data-stu-id="0db73-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="0db73-109">In qualità di amministratore del tenant, puoi abilitare o disabilitare un componente aggiuntivo riunione di Microsoft teams per Google Workspace dall'account di amministratore dell'organizzazione usando il portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="0db73-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="0db73-110">Il componente aggiuntivo è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0db73-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="0db73-111">Accedere a Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="0db73-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="0db73-112">Selezionare **applicazioni aziendali**  >  **tutte le applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="0db73-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="0db73-113">Cercare **il componente aggiuntivo riunione Microsoft teams per Google Workspace**.</span><span class="sxs-lookup"><span data-stu-id="0db73-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![Portale di Azure che Mostra tutte le applicazioni](media/aad-add-google-workspace.png)

4. <span data-ttu-id="0db73-115">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="0db73-115">Select **Yes**.</span></span>

   ![Portale di Azure che mostra le proprietà di Google Workspace](media/google-workspace-properties.png)

5. <span data-ttu-id="0db73-117">Opzionale Per disabilitare il componente aggiuntivo, selezionare **No** invece di **Sì** nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="0db73-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="0db73-118">Disabilitare il componente aggiuntivo riunione Microsoft teams per Google Workspace tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="0db73-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="0db73-119">Per altre informazioni, vedere [creare un'entità di servizio di Azure con Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span><span class="sxs-lookup"><span data-stu-id="0db73-119">For more information, see [Create an Azure service principal with Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="0db73-120">Eliminare il componente aggiuntivo riunione Microsoft teams per Google Workspace</span><span class="sxs-lookup"><span data-stu-id="0db73-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="0db73-121">Per istruzioni, vedi la documentazione di Google per [eliminare un'app di Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) .</span><span class="sxs-lookup"><span data-stu-id="0db73-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>
