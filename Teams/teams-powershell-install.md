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
description: Informazioni su come usare i controlli di PowerShell per la gestione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a99967df019a91460bde5fd4e3e6e7aee15444d3
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569112"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="cad8b-103">Installare Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cad8b-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="cad8b-104">Questo articolo spiega come installare il modulo Microsoft Teams PowerShell tramite [PowerShellGet.](/powershell/scripting/gallery/installing-psget)</span><span class="sxs-lookup"><span data-stu-id="cad8b-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="cad8b-105">Queste istruzioni funzionano su [piattaforme Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="cad8b-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="cad8b-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cad8b-106">Requirements</span></span>

<span data-ttu-id="cad8b-107">Teams PowerShell richiede PowerShell 5.1 o versione successiva su tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="cad8b-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="cad8b-108">Installare [l'ultima versione di PowerShell disponibile](/powershell/scripting/install/installing-powershell) per il sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="cad8b-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="cad8b-109">Ci sono problemi noti con PowerShell 7 e PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="cad8b-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="cad8b-110">Per un'esperienza ottimale, è consigliabile usare PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="cad8b-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="cad8b-111">Installare il modulo Teams di PowerShell</span><span class="sxs-lookup"><span data-stu-id="cad8b-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="cad8b-112">Per un'esperienza ottimale, usare i moduli Disponibilità generale (GA) o Anteprima pubblica, non entrambi.</span><span class="sxs-lookup"><span data-stu-id="cad8b-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="cad8b-113">Non dovrebbero lavorare insieme.</span><span class="sxs-lookup"><span data-stu-id="cad8b-113">They're not intended to work together.</span></span>


<span data-ttu-id="cad8b-114">Usare i **cmdlet PowerShellGet** per installare il modulo Di PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="cad8b-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="cad8b-115">L'installazione del modulo per tutti gli utenti in un sistema richiede privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="cad8b-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="cad8b-116">Avviare la sessione di PowerShell **con Esegui come amministratore** in Windows o usare il comando su `sudo` macOS o Linux:</span><span class="sxs-lookup"><span data-stu-id="cad8b-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="cad8b-117">Per impostazione predefinita, la raccolta di PowerShell (PSGallery) non è configurata come archivio attendibile per **PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="cad8b-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="cad8b-118">La prima volta che si usa PSGallery, viene visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="cad8b-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="cad8b-119">Rispondere **Sì** o **Sì a Tutti per** continuare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="cad8b-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="cad8b-120">Installare Teams PowerShell Public Preview</span><span class="sxs-lookup"><span data-stu-id="cad8b-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="cad8b-121">Se si usa la versione Anteprima pubblica di Teams PowerShell, si consiglia vivamente di disinstallare prima Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="cad8b-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="cad8b-122">L'installazione del modulo di anteprima pubblica di Teams PowerShell per tutti gli utenti in un sistema richiede privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="cad8b-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="cad8b-123">Avviare la sessione di PowerShell **con Esegui come amministratore** in Windows o usare il comando su `sudo` macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="cad8b-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="cad8b-124">Se si usa PowerShell 5.1, è necessario aggiornare il modulo **PowerShellGet** in anticipo.</span><span class="sxs-lookup"><span data-stu-id="cad8b-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="cad8b-125">Dopo aver aggiornato **PowerShellGet,** chiudere e riaprire una sessione di PowerShell con privilegi elevati per assicurarsi che sia caricata **l'ultima sessione PowerShellGet.**</span><span class="sxs-lookup"><span data-stu-id="cad8b-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="cad8b-126">Per installare Teams PowerShell Public Preview, eseguire il comando di PowerShell riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cad8b-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="cad8b-127">Puoi trovare l'ultima versione di anteprima nella Raccolta [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) o in PowerShell eseguendo "Find-Module MicrosoftTeams -AllowPrerelease"</span><span class="sxs-lookup"><span data-stu-id="cad8b-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="cad8b-128">Installare Skype for Business Online Connector</span><span class="sxs-lookup"><span data-stu-id="cad8b-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="cad8b-129">Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="cad8b-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="cad8b-130">Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="cad8b-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in"></a><span data-ttu-id="cad8b-131">Accedi</span><span class="sxs-lookup"><span data-stu-id="cad8b-131">Sign in</span></span>

<span data-ttu-id="cad8b-132">Per iniziare a lavorare con PowerShell di Teams, accedere con le credenziali di Azure.</span><span class="sxs-lookup"><span data-stu-id="cad8b-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="cad8b-133">Se si usa l'ultima versione di Anteprima pubblica di PowerShell per [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="cad8b-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="cad8b-134">Aggiornare PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="cad8b-134">Update Teams PowerShell</span></span>

<span data-ttu-id="cad8b-135">Per aggiornare Teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell con privilegi elevati ed eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cad8b-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="cad8b-136">Se Teams PowerShell è già stato importato nella sessione di PowerShell, l'aggiornamento del modulo non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="cad8b-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="cad8b-137">Chiudere PowerShell e ria aprire una nuova sessione di PowerShell con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="cad8b-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="cad8b-138">Disinstallare Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cad8b-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="cad8b-139">Per disinstallare Teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell con privilegi elevati ed eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cad8b-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="cad8b-140">Se Teams PowerShell è già stato importato nella sessione di PowerShell, la disinstallazione del modulo non riesce.</span><span class="sxs-lookup"><span data-stu-id="cad8b-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="cad8b-141">Chiudere PowerShell e ria aprire una nuova sessione di PowerShell con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="cad8b-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cad8b-142">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cad8b-142">Next Steps</span></span>

<span data-ttu-id="cad8b-143">Ora sei pronto per gestire Teams con Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cad8b-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="cad8b-144">Per [informazioni introduttive, vedere Gestione dei team con PowerShell](teams-powershell-managing-teams.md) di Teams.</span><span class="sxs-lookup"><span data-stu-id="cad8b-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cad8b-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="cad8b-145">Related topics</span></span>

[<span data-ttu-id="cad8b-146">Gestione di Teams con PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="cad8b-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="cad8b-147">Note sulla versione di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="cad8b-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="cad8b-148">Informazioni di riferimento per i cmdlet di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cad8b-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="cad8b-149">Informazioni di riferimento per i cmdlet di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cad8b-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
