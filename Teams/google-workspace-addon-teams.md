---
title: Configurare il Microsoft Teams riunione per Google Workspace
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
description: Scopri come configurare il componente aggiuntivo Microsoft Teams riunione per Google Workspace.
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
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="28da9-103">Configurare il Microsoft Teams riunione per Google Workspace</span><span class="sxs-lookup"><span data-stu-id="28da9-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="28da9-104">L'Microsoft Teams per le riunioni consente agli utenti del calendario di Google di pianificare e partecipare a una riunione Microsoft Teams direttamente da Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="28da9-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="28da9-105">Gli utenti potranno accedere alle funzionalità Teams riunioni, tra cui video e audioconferenze, condivisione dello schermo, chat delle riunioni, lavagne digitali e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="28da9-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="28da9-106">Rimani connesso e organizzato per lavorare di più insieme in tutto il lavoro, la scuola e la vita.</span><span class="sxs-lookup"><span data-stu-id="28da9-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="28da9-107">Il componente Microsoft Teams riunione per Google Workspace deve essere abilitato da un amministratore Teams prima che gli utenti del tenant possano accedere all'app.</span><span class="sxs-lookup"><span data-stu-id="28da9-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="28da9-108">Abilitare o disabilitare Microsoft Teams componente aggiuntivo riunione per Google Workspace nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="28da9-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="28da9-109">L'amministratore tenant può abilitare o disabilitare un componente aggiuntivo Microsoft Teams riunione per Google Workspace dall'account di amministratore dell'organizzazione usando il portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="28da9-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="28da9-110">Il componente aggiuntivo è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="28da9-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="28da9-111">Accedere al portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="28da9-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="28da9-112">Selezionare **Enterprise tutte** le  >  **applicazioni.**</span><span class="sxs-lookup"><span data-stu-id="28da9-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="28da9-113">Cercare il **componente aggiuntivo Microsoft Teams riunione per Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="28da9-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![Portale di Azure che mostra tutte le applicazioni](media/aad-add-google-workspace.png)

4. <span data-ttu-id="28da9-115">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="28da9-115">Select **Yes**.</span></span>

   ![Portale di Azure che mostra le proprietà dell'area di lavoro di Google](media/google-workspace-properties.png)

5. <span data-ttu-id="28da9-117">(Facoltativo) Per disabilitare il componente aggiuntivo, selezionare **No** invece **di Sì** nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="28da9-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="28da9-118">Disabilitare Microsoft Teams per le riunioni per Google Workspace usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="28da9-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="28da9-119">Per altre informazioni, vedere [Creare un'entità servizio di Azure con Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span><span class="sxs-lookup"><span data-stu-id="28da9-119">For more information, see [Create an Azure service principal with Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="28da9-120">Eliminare il componente aggiuntivo Microsoft Teams riunione per Google Workspace</span><span class="sxs-lookup"><span data-stu-id="28da9-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="28da9-121">Per istruzioni, vedere la documentazione di Google [Eliminare un'app Google Workspace Marketplace.](https://support.google.com/a/answer/6216211?hl=en)</span><span class="sxs-lookup"><span data-stu-id="28da9-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>