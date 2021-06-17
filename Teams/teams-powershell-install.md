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
description: Informazioni sull'uso dei controlli di PowerShell per la gestione Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a1e969a1310a64a281434a630f4fb608b8cfb30
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947567"
---
# <a name="install-microsoft-teams-powershell-module"></a><span data-ttu-id="835dc-103">Installare Microsoft Teams modulo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="835dc-103">Install Microsoft Teams PowerShell Module</span></span>

<span data-ttu-id="835dc-104">Questo articolo spiega come installare il modulo Microsoft Teams PowerShell usando la raccolta di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="835dc-104">This article explains how to install the Microsoft Teams PowerShell module using PowerShell Gallery.</span></span> <span data-ttu-id="835dc-105">Il Microsoft Teams PowerShell è supportato in tutte le Windows.</span><span class="sxs-lookup"><span data-stu-id="835dc-105">The Microsoft Teams PowerShell module is supported on all Windows platforms.</span></span> 

## <a name="requirements"></a><span data-ttu-id="835dc-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="835dc-106">Requirements</span></span>

<span data-ttu-id="835dc-107">Microsoft Teams Il modulo di PowerShell richiede PowerShell 5.1 o versione successiva in tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="835dc-107">Microsoft Teams PowerShell module requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="835dc-108">Installare [l'ultima versione di PowerShell](/powershell/scripting/install/installing-powershell)   disponibile per il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="835dc-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> 

<span data-ttu-id="835dc-109">Per controllare la versione di PowerShell, eseguire il comando seguente all'interno di una sessione di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="835dc-109">To check your PowerShell version, run the following command from within a PowerShell session:</span></span> 

```powershell
$PSVersionTable.PSVersion 
```
<span data-ttu-id="835dc-110">È consigliabile usare il cmdlet Install-Module per installare il modulo Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="835dc-110">We recommend that you use the  Install-Module cmdlet to install the Microsoft Teams PowerShell module.</span></span> 
 
<span data-ttu-id="835dc-111">Se la raccolta di PowerShell (PSGallery) non è configurata come archivio attendibile per **PowerShellGet,** la prima volta che si usa PSGallery viene visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="835dc-111">If PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**, the first time you use the PSGallery you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="835dc-112">Rispondere **Sì** o **Sì a Tutti** per continuare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="835dc-112">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="installing-using-the-powershellgallery"></a><span data-ttu-id="835dc-113">Installazione tramite PowerShellGallery</span><span class="sxs-lookup"><span data-stu-id="835dc-113">Installing using the PowerShellGallery</span></span>

<span data-ttu-id="835dc-114">Microsoft Teams Il modulo di PowerShell è attualmente supportato per l'uso con PowerShell 5.1 in Windows.</span><span class="sxs-lookup"><span data-stu-id="835dc-114">Microsoft Teams PowerShell module is currently supported for use with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="835dc-115">Seguire questa procedura per installare il modulo:</span><span class="sxs-lookup"><span data-stu-id="835dc-115">Follow these steps to install the module:</span></span> 

- <span data-ttu-id="835dc-116">Eseguire [l'aggiornamento Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="835dc-116">Update to [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span></span> <span data-ttu-id="835dc-117">Se si è in Windows 10 versione 1607 o successiva, è già installato PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="835dc-117">If you're on Windows 10 version 1607 or higher, you already have PowerShell 5.1 installed.</span></span> 
- <span data-ttu-id="835dc-118">Installare [.NET Framework 4.7.2](/dotnet/framework/install) o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="835dc-118">Install [.NET Framework 4.7.2](/dotnet/framework/install) or later.</span></span> 
- <span data-ttu-id="835dc-119">Eseguire il comando seguente per installare la versione più recente di PowerShellGet:</span><span class="sxs-lookup"><span data-stu-id="835dc-119">Run the following command to install the latest PowerShellGet:</span></span>
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- <span data-ttu-id="835dc-120">Installare il modulo Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="835dc-120">Install the Teams PowerShell Module.</span></span>

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a><span data-ttu-id="835dc-121">Installazione offline</span><span class="sxs-lookup"><span data-stu-id="835dc-121">Offline Installation</span></span> 

<span data-ttu-id="835dc-122">In alcuni ambienti non è possibile connettersi alla raccolta di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="835dc-122">In some environments, it's not possible to connect to the PowerShell Gallery.</span></span> <span data-ttu-id="835dc-123">In queste situazioni, seguire questa procedura [di installazione manuale.](https://aka.ms/psgallery-manualdownload)</span><span class="sxs-lookup"><span data-stu-id="835dc-123">In those situations, please follow these [manual installation steps](https://aka.ms/psgallery-manualdownload).</span></span>  

## <a name="sign-in"></a><span data-ttu-id="835dc-124">Accedi</span><span class="sxs-lookup"><span data-stu-id="835dc-124">Sign in</span></span>

<span data-ttu-id="835dc-125">Per iniziare a lavorare con Microsoft Teams di PowerShell, accedere con le credenziali di Azure.</span><span class="sxs-lookup"><span data-stu-id="835dc-125">To start working with Microsoft Teams PowerShell module, sign in with your Azure credentials.</span></span>

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a><span data-ttu-id="835dc-126">Aggiornare Teams modulo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="835dc-126">Update Teams PowerShell Module</span></span>

<span data-ttu-id="835dc-127">Per aggiornare qualsiasi modulo di PowerShell, è consigliabile usare lo stesso metodo usato per installare il modulo.</span><span class="sxs-lookup"><span data-stu-id="835dc-127">To update any PowerShell module, you should use the same method used to install the module.</span></span> <span data-ttu-id="835dc-128">Ad esempio, se è stato usato in origine Install-Module, è consigliabile usare [Update-Module](/powershell/module/powershellget/update-module) per ottenere la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="835dc-128">For example, if you originally used Install-Module, then you should use [Update-Module](/powershell/module/powershellget/update-module) to get the latest version.</span></span>  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="835dc-129">Se Teams PowerShell è già stato importato nella sessione di PowerShell, l'aggiornamento del modulo non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="835dc-129">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="835dc-130">Chiudere PowerShell e ria aprire una nuova sessione di PowerShell con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="835dc-130">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="835dc-131">Disinstallare Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="835dc-131">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="835dc-132">Per disinstallare Microsoft Teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell ed eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="835dc-132">To uninstall Microsoft Teams PowerShell, open a new PowerShell command prompt and run the following:</span></span> 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a><span data-ttu-id="835dc-133">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="835dc-133">Next Steps</span></span> 

<span data-ttu-id="835dc-134">Ora si è pronti per gestire le Microsoft Teams usando Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="835dc-134">Now you're ready to manage Microsoft Teams using Microsoft Teams PowerShell.</span></span> <span data-ttu-id="835dc-135">Vedere [Gestione Teams con Teams PowerShell](teams-powershell-managing-teams.md) per iniziare.</span><span class="sxs-lookup"><span data-stu-id="835dc-135">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="835dc-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="835dc-136">Related topics</span></span>

[<span data-ttu-id="835dc-137">Gestione Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="835dc-137">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="835dc-138">Teams Note sulla versione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="835dc-138">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="835dc-139">Microsoft Teams di cmdlet</span><span class="sxs-lookup"><span data-stu-id="835dc-139">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="835dc-140">Skype for Business cmdlet</span><span class="sxs-lookup"><span data-stu-id="835dc-140">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
