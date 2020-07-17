---
title: Installare Microsoft teams PowerShell
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
description: Informazioni su come usare i controlli di PowerShell per la gestione di Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f42548439c0915eea8405b3c466f7696767f80c
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085882"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="a38e2-103">Installare Microsoft teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="a38e2-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="a38e2-104">Questo articolo spiega come installare il modulo di PowerShell di Microsoft teams usando [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="a38e2-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="a38e2-105">Queste istruzioni funzionano in [Azure cloud Shell](/azure/cloud-shell/overview), Linux, MacOS e piattaforme Windows.</span><span class="sxs-lookup"><span data-stu-id="a38e2-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="a38e2-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a38e2-106">Requirements</span></span>

<span data-ttu-id="a38e2-107">Teams PowerShell richiede PowerShell 5,1 o versioni successive in tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="a38e2-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="a38e2-108">Installare la [versione più recente di PowerShell](/powershell/scripting/install/installing-powershell) disponibile per il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a38e2-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="a38e2-109">Sono presenti problemi noti di PowerShell 7 e teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a38e2-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="a38e2-110">Per un'esperienza ottimale, è consigliabile usare PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="a38e2-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="a38e2-111">Installare il modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="a38e2-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="a38e2-112">Per un'esperienza ottimale, usa la disponibilità generale (GA) o i moduli di anteprima pubblica, non entrambi.</span><span class="sxs-lookup"><span data-stu-id="a38e2-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="a38e2-113">Non sono destinati a collaborare.</span><span class="sxs-lookup"><span data-stu-id="a38e2-113">They're not intended to work together.</span></span>


<span data-ttu-id="a38e2-114">Usare i cmdlet **PowerShellGet** per installare il modulo di PowerShell teams.</span><span class="sxs-lookup"><span data-stu-id="a38e2-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="a38e2-115">L'installazione del modulo per tutti gli utenti in un sistema richiede privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="a38e2-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="a38e2-116">Avviare la sessione di PowerShell usando **Esegui come amministratore** in Windows o usare il `sudo` comando in MacOS o Linux:</span><span class="sxs-lookup"><span data-stu-id="a38e2-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="a38e2-117">Per impostazione predefinita, la raccolta di PowerShell (PSGallery) non è configurata come repository attendibile per **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="a38e2-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="a38e2-118">La prima volta che si usa PSGallery, viene visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="a38e2-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="a38e2-119">Rispondere **Sì** o **Sì a tutti** per continuare con l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a38e2-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="a38e2-120">Installare l'anteprima pubblica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="a38e2-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="a38e2-121">Se si usa la versione di anteprima pubblica di teams PowerShell, è consigliabile disinstallare prima di tutto Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="a38e2-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="a38e2-122">L'installazione del modulo anteprima pubblica teams di PowerShell per tutti gli utenti di un sistema richiede privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="a38e2-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="a38e2-123">Avviare la sessione di PowerShell usando **Esegui come amministratore** in Windows o usare il `sudo` comando in MacOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="a38e2-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="a38e2-124">Se si usa PowerShell 5,1, è necessario aggiornare il modulo **PowerShellGet** in anticipo.</span><span class="sxs-lookup"><span data-stu-id="a38e2-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="a38e2-125">Dopo l'aggiornamento di **PowerShellGet**, chiudere e riaprire una sessione di PowerShell con privilegi elevati per assicurarsi che venga caricato il **PowerShellGet** più recente.</span><span class="sxs-lookup"><span data-stu-id="a38e2-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="a38e2-126">Per installare teams PowerShell Public Preview, eseguire il comando di PowerShell seguente.</span><span class="sxs-lookup"><span data-stu-id="a38e2-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="a38e2-127">Installare il connettore Skype for business online</span><span class="sxs-lookup"><span data-stu-id="a38e2-127">Install the Skype for Business Online Connector</span></span>

> [!WARNING]
> <span data-ttu-id="a38e2-128">Skype for Business Online Connector fa attualmente parte di teams PowerShell Public Preview.</span><span class="sxs-lookup"><span data-stu-id="a38e2-128">Skype for Business Online Connector is currently part of Teams PowerShell public preview.</span></span> <span data-ttu-id="a38e2-129">Dopo aver implementato questa funzionalità nel rilascio di GA di teams PowerShell, Skype for Business Online Connector non sarà più disponibile.</span><span class="sxs-lookup"><span data-stu-id="a38e2-129">Once we've rolled this feature into the GA release of Teams PowerShell, Skype for Business Online Connector will no longer be available.</span></span>

<span data-ttu-id="a38e2-130">Scaricare e installare il [modulo di PowerShell per Skype for business](https://www.microsoft.com/download/details.aspx?id=39366), quindi eseguire le operazioni seguenti in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a38e2-130">Download and install the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), then run the following in PowerShell.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="a38e2-131">Accedi</span><span class="sxs-lookup"><span data-stu-id="a38e2-131">Sign in</span></span>

<span data-ttu-id="a38e2-132">Per iniziare a usare teams PowerShell, accedere con le credenziali di Azure.</span><span class="sxs-lookup"><span data-stu-id="a38e2-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="a38e2-133">Se si usa la versione di [anteprima pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)più recente, non è necessario installare il connettore Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="a38e2-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="a38e2-134">Aggiornare PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="a38e2-134">Update Teams PowerShell</span></span>

<span data-ttu-id="a38e2-135">Per aggiornare teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell con privilegi elevati ed eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a38e2-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="a38e2-136">Se teams PowerShell è già stato importato nella sessione di PowerShell, l'aggiornamento del modulo non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="a38e2-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="a38e2-137">Chiudere PowerShell e riaprire una nuova sessione di PowerShell elevata.</span><span class="sxs-lookup"><span data-stu-id="a38e2-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="a38e2-138">Disinstallare teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="a38e2-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="a38e2-139">Per disinstallare teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell con privilegi elevati ed eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a38e2-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="a38e2-140">Se teams PowerShell è già stato importato nella sessione di PowerShell, la disinstallazione del modulo non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="a38e2-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="a38e2-141">Chiudere PowerShell e riaprire una nuova sessione di PowerShell elevata.</span><span class="sxs-lookup"><span data-stu-id="a38e2-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a38e2-142">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a38e2-142">Next Steps</span></span>

<span data-ttu-id="a38e2-143">Ora sei pronto per gestire teams usando PowerShell teams.</span><span class="sxs-lookup"><span data-stu-id="a38e2-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="a38e2-144">Per iniziare, vedere [gestione di team con teams PowerShell](teams-powershell-managing-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="a38e2-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a38e2-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a38e2-145">Related topics</span></span>

[<span data-ttu-id="a38e2-146">Gestione di team con PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="a38e2-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="a38e2-147">Note sulla versione di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="a38e2-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="a38e2-148">Informazioni di riferimento sui cmdlet di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a38e2-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="a38e2-149">Informazioni di riferimento sui cmdlet di Skype for business</span><span class="sxs-lookup"><span data-stu-id="a38e2-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
