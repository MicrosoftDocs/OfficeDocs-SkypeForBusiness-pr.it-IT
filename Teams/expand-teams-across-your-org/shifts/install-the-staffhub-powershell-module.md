---
title: Installare il modulo di PowerShell StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Informazioni su come installare e connettersi al modulo di PowerShell Microsoft StaffHub.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dc7c97a3c8107de3c2515a8f112bbc1993e3d8f
ms.sourcegitcommit: d4ebbebd5e4bfac27280bdc043fc6edd0722d1d7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "36184534"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="5fd9b-103">Installare il modulo di PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="5fd9b-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fd9b-104">Efficace il 1 ° ottobre 2019, Microsoft StaffHub sarà ritirato.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="5fd9b-105">Stiamo costruendo funzionalità di StaffHub in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="5fd9b-106">Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="5fd9b-107">StaffHub smetterà di funzionare per tutti gli utenti il 1 ° ottobre 2019.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="5fd9b-108">Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="5fd9b-109">Per altre informazioni, vedere [Microsoft StaffHub per](microsoft-staffhub-to-be-retired.md)ritirarsi.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="5fd9b-110">Seguire i passaggi di questo articolo per installare e connettersi al modulo di PowerShell Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="5fd9b-111">Per gestire StaffHub, è necessario usare PowerShell e trasferire i team di StaffHub in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="5fd9b-112">Installare il modulo di PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="5fd9b-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="5fd9b-113">Scaricare il [modulo di PowerShell StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="5fd9b-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="5fd9b-114">Aprire Windows PowerShell 3,0 o versione successiva come amministratore. A tale scopo, fare clic sul pulsante **Start**, digitare **Windows PowerShell**, fare clic con il pulsante destro del mouse su **Windows PowerShell**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="5fd9b-115">Per ottenere la versione più recente di Windows PowerShell, vedere [installazione di Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5fd9b-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
3. <span data-ttu-id="5fd9b-116">Esegui il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="5fd9b-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
    

4. <span data-ttu-id="5fd9b-117">Controllare il percorso della cartella nell'output e verificare che nel computer siano presenti tutte le cartelle del percorso prima di procedere con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="5fd9b-118">Se le cartelle sono mancanti, crearle.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="5fd9b-119">Eseguire la procedura seguente per consentire l'installazione del modulo di PowerShell StaffHub:</span><span class="sxs-lookup"><span data-stu-id="5fd9b-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

6. <span data-ttu-id="5fd9b-120">Eseguire la procedura seguente, &lt;dove&gt; path è il percorso nell'output del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-120">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="5fd9b-121">Ad esempio, il percorso potrebbe essere simile a C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="5fd9b-122">Assicurarsi di eseguire ogni comando separatamente.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-122">Be sure to run each command separately.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```
7. <span data-ttu-id="5fd9b-123">Uscire da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="5fd9b-124">Aprire Windows PowerShell 3,0 o versione successiva come amministratore globale, quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fd9b-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="5fd9b-125">Connettersi al modulo di PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="5fd9b-125">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="5fd9b-126">Esegui il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="5fd9b-126">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="5fd9b-127">Quando viene richiesto, accedere come amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="5fd9b-127">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5fd9b-128">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5fd9b-128">Related topics</span></span>

- [<span data-ttu-id="5fd9b-129">Riferimento a Microsoft PowerShell per StaffHub</span><span class="sxs-lookup"><span data-stu-id="5fd9b-129">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="5fd9b-130">Spostare i team di Microsoft StaffHub in turni in teams</span><span class="sxs-lookup"><span data-stu-id="5fd9b-130">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
