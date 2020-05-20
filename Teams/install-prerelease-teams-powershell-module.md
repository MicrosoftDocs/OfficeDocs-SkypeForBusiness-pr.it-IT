---
title: Installare la versione non definitiva del modulo di PowerShell Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Seguire questa procedura per installare la versione preliminare del modulo teams PowerShell dalla raccolta di test di PowerShell.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321769"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="a8496-103">Installare la versione non definitiva del modulo di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="a8496-103">Install the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="a8496-104">In questo articolo viene descritto come installare la versione più recente di pre-rilascio del modulo teams PowerShell dalla [raccolta di test di PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="a8496-104">This article describes how to install the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="a8496-105">È necessaria la versione preliminare del modulo di PowerShell teams in scenari in cui i cmdlet per la gestione di una caratteristica teams non sono supportati nella versione in generale disponibile del modulo e sono disponibili solo nella versione precedente al rilascio.</span><span class="sxs-lookup"><span data-stu-id="a8496-105">You'll need the pre-release version of the Teams PowerShell module in scenarios where cmdlets for managing a Teams feature aren't supported in the Generally Available version of the module and are only available in the pre-release version.</span></span>

<span data-ttu-id="a8496-106">Seguire questa procedura per installare la versione più recente di pre-rilascio del modulo di PowerShell teams dalla raccolta di test di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8496-106">Use these steps to install the latest pre-release version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="a8496-107">Non installare il modulo teams PowerShell dalla raccolta di test di PowerShell affiancata con una versione del modulo dalla [raccolta di PowerShell pubblica](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="a8496-107">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the [public PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="a8496-108">Seguire questa procedura per disinstallare prima il modulo di PowerShell teams dalla raccolta di PowerShell pubblica e quindi installare la versione più recente del modulo dalla raccolta di test di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8496-108">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="a8496-109">Chiudere tutte le sessioni di PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="a8496-109">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="a8496-110">Avviare una nuova istanza del modulo di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8496-110">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="a8496-111">Eseguire la procedura seguente per disinstallare il modulo di PowerShell teams dalla raccolta di PowerShell pubblica:</span><span class="sxs-lookup"><span data-stu-id="a8496-111">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="a8496-112">Chiudere tutte le sessioni di PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="a8496-112">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="a8496-113">Avviare di nuovo il modulo di Windows PowerShell e quindi eseguire la procedura seguente per registrare la raccolta di test di PowerShell come origine attendibile:</span><span class="sxs-lookup"><span data-stu-id="a8496-113">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="a8496-114">Eseguire la procedura seguente per installare il modulo di PowerShell più recente di teams dalla raccolta di test di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a8496-114">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="a8496-115">Eseguire le operazioni seguenti per verificare che la versione più recente del modulo di PowerShell teams della raccolta di test di PowerShell sia installata correttamente:</span><span class="sxs-lookup"><span data-stu-id="a8496-115">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="a8496-116">Aggiornamento alla versione più recente del modulo di PowerShell teams dalla raccolta di test di PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8496-116">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="a8496-117">Se il modulo teams PowerShell è già stato installato dalla raccolta test di PowerShell, eseguire la procedura seguente per aggiornare la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="a8496-117">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="a8496-118">Chiudere tutte le sessioni di PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="a8496-118">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="a8496-119">Avviare una nuova istanza del modulo di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8496-119">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="a8496-120">Eseguire la procedura seguente per aggiornare la versione attualmente installata del modulo di PowerShell teams dalla raccolta di test di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a8496-120">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="a8496-121">Eseguire le operazioni seguenti per verificare che la versione più recente del modulo di PowerShell teams della raccolta di test di PowerShell sia installata correttamente:</span><span class="sxs-lookup"><span data-stu-id="a8496-121">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="a8496-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a8496-122">Related topics</span></span>

- [<span data-ttu-id="a8496-123">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="a8496-123">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
