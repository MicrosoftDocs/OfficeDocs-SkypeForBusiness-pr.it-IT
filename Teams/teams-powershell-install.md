---
title: Installare Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni sull'uso dei controlli di PowerShell per la gestione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768341"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="bc954-103">Installare Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc954-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="bc954-104">Questo articolo spiega come installare il modulo di Microsoft Teams PowerShell usando [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="bc954-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="bc954-105">Queste istruzioni funzionano su [piattaforme Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="bc954-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="bc954-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bc954-106">Requirements</span></span>

<span data-ttu-id="bc954-107">Teams PowerShell richiede PowerShell 5.1 o versione successiva in tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="bc954-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="bc954-108">Installare [l'ultima versione di PowerShell](/powershell/scripting/install/installing-powershell) disponibile per il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bc954-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!NOTE]
> <span data-ttu-id="bc954-109">Per un'esperienza ottimale, è consigliabile usare PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="bc954-109">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="bc954-110">Installare il modulo di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="bc954-110">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="bc954-111">Per un'esperienza ottimale, usare i moduli Disponibilità generale (GA) o Anteprima pubblica, non entrambi.</span><span class="sxs-lookup"><span data-stu-id="bc954-111">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="bc954-112">Non sono destinati a collaborare.</span><span class="sxs-lookup"><span data-stu-id="bc954-112">They're not intended to work together.</span></span>


<span data-ttu-id="bc954-113">Usare i cmdlet **di PowerShellGet** per installare il modulo di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="bc954-113">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="bc954-114">L'installazione del modulo per tutti gli utenti in un sistema richiede privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="bc954-114">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="bc954-115">Avviare la sessione di PowerShell usando **Esegui come amministratore** in Windows o usare il comando in `sudo` macOS o Linux:</span><span class="sxs-lookup"><span data-stu-id="bc954-115">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="bc954-116">Per impostazione predefinita, la raccolta di PowerShell (PSGallery) non è configurata come archivio attendibile per **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="bc954-116">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="bc954-117">La prima volta che si usa PSGallery, viene visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="bc954-117">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="bc954-118">Rispondere **Sì** o **Sì a Tutti** per continuare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="bc954-118">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="sign-in"></a><span data-ttu-id="bc954-119">Accedi</span><span class="sxs-lookup"><span data-stu-id="bc954-119">Sign in</span></span>

<span data-ttu-id="bc954-120">Per iniziare a lavorare con Teams PowerShell, accedere con le credenziali di Azure.</span><span class="sxs-lookup"><span data-stu-id="bc954-120">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="bc954-121">Se si usa la versione di anteprima pubblica di [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)più recente, non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="bc954-121">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="bc954-122">Accedere con L'autenticazione a più fattori e l'autenticazione moderna</span><span class="sxs-lookup"><span data-stu-id="bc954-122">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="bc954-123">Se l'account usa l'autenticazione a più fattori, seguire la procedura descritta in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="bc954-123">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a><span data-ttu-id="bc954-124">Aggiornare PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="bc954-124">Update Teams PowerShell</span></span>

<span data-ttu-id="bc954-125">Per aggiornare Teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell con privilegi elevati ed eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bc954-125">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="bc954-126">Se Teams PowerShell è già stato importato nella sessione di PowerShell, l'aggiornamento del modulo non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="bc954-126">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="bc954-127">Chiudere PowerShell e ria aprire una nuova sessione di PowerShell con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="bc954-127">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="bc954-128">Disinstallare Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc954-128">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="bc954-129">Per disinstallare Teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell con privilegi elevati ed eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bc954-129">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="bc954-130">Se Teams PowerShell è già stato importato nella sessione di PowerShell, la disinstallazione del modulo non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="bc954-130">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="bc954-131">Chiudere PowerShell e ria aprire una nuova sessione di PowerShell con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="bc954-131">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="bc954-132">Installare l'anteprima pubblica di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="bc954-132">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="bc954-133">Se si usa la versione anteprima pubblica di Teams PowerShell, è consigliabile disinstallare prima Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="bc954-133">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="bc954-134">L'installazione del modulo di anteprima pubblica di Teams PowerShell per tutti gli utenti in un sistema richiede privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="bc954-134">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="bc954-135">Avviare la sessione di PowerShell usando **Esegui come amministratore** in Windows o usare il comando in `sudo` macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="bc954-135">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="bc954-136">Se si usa PowerShell 5.1, è necessario aggiornare il modulo **PowerShellGet** in anticipo.</span><span class="sxs-lookup"><span data-stu-id="bc954-136">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="bc954-137">Dopo aver aggiornato **PowerShellGet,** chiudere e riaprire una sessione di PowerShell con privilegi elevati per assicurarsi che sia caricato **l'ultimo PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="bc954-137">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="bc954-138">Per installare l'anteprima pubblica di Teams PowerShell, eseguire il comando di PowerShell seguente.</span><span class="sxs-lookup"><span data-stu-id="bc954-138">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="bc954-139">È possibile trovare l'ultima versione di anteprima in [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) o in PowerShell eseguendo "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span><span class="sxs-lookup"><span data-stu-id="bc954-139">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a><span data-ttu-id="bc954-140">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="bc954-140">Next Steps</span></span>

<span data-ttu-id="bc954-141">Ora sei pronto per gestire Teams con Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc954-141">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="bc954-142">Per [informazioni introduttive, vedere Gestione di Teams con Teams PowerShell.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bc954-142">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bc954-143">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bc954-143">Related topics</span></span>

[<span data-ttu-id="bc954-144">Gestione di Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc954-144">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="bc954-145">Note sulla versione di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="bc954-145">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="bc954-146">Informazioni di riferimento sul cmdlet di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc954-146">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="bc954-147">Informazioni di riferimento sul cmdlet di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc954-147">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
