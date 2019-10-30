---
title: Installare il modulo di PowerShell StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come installare e connettersi al modulo di PowerShell Microsoft StaffHub.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef80290e6b8a1ce4de834a000148d60b2c5ef89d
ms.sourcegitcommit: 7d5dd650480ca2e55c24ce30408a5058067f6932
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "37775075"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="16f10-103">Installare il modulo di PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="16f10-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16f10-104">Efficace 31 dicembre 2019, Microsoft StaffHub sarà ritirato.</span><span class="sxs-lookup"><span data-stu-id="16f10-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="16f10-105">Stiamo costruendo funzionalità di StaffHub in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="16f10-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="16f10-106">Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo.</span><span class="sxs-lookup"><span data-stu-id="16f10-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="16f10-107">StaffHub smetterà di funzionare per tutti gli utenti il 31 dicembre 2019.</span><span class="sxs-lookup"><span data-stu-id="16f10-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="16f10-108">Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams.</span><span class="sxs-lookup"><span data-stu-id="16f10-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="16f10-109">Per altre informazioni, vedere [Microsoft StaffHub per ritirarsi](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="16f10-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="16f10-110">Seguire i passaggi di questo articolo per installare e connettersi al modulo di PowerShell Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="16f10-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="16f10-111">Sarà necessario questo per [trasferire i team di StaffHub in teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="16f10-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="16f10-112">Installare il modulo di PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="16f10-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="16f10-113">Scaricare il [modulo di PowerShell StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span><span class="sxs-lookup"><span data-stu-id="16f10-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span></span>
2. <span data-ttu-id="16f10-114">Aprire Windows PowerShell 3,0 o versione successiva come amministratore. A tale scopo, fare clic sul pulsante **Start**, digitare **Windows PowerShell**, fare clic con il pulsante destro del mouse su **Windows PowerShell**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="16f10-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="16f10-115">Per ottenere la versione più recente di Windows PowerShell, vedere [installazione di Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="16f10-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span>
3. <span data-ttu-id="16f10-116">Esegui il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="16f10-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
4. <span data-ttu-id="16f10-117">Controllare il percorso della cartella nell'output e verificare che nel computer siano presenti tutte le cartelle del percorso prima di procedere con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="16f10-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="16f10-118">Se le cartelle sono mancanti, crearle.</span><span class="sxs-lookup"><span data-stu-id="16f10-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="16f10-119">Eseguire la procedura seguente per consentire l'installazione del modulo di PowerShell StaffHub:</span><span class="sxs-lookup"><span data-stu-id="16f10-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
6. <span data-ttu-id="16f10-120">Eseguire la procedura seguente, &lt;dove&gt; path è il percorso nell'output del passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="16f10-120">Run the following, where &lt;path&gt; is the path in the output from step 3.</span></span> <span data-ttu-id="16f10-121">Ad esempio, il percorso potrebbe essere simile a C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="16f10-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="16f10-122">Assicurarsi di eseguire ogni comando separatamente.</span><span class="sxs-lookup"><span data-stu-id="16f10-122">Be sure to run each command separately.</span></span>

    ```
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. <span data-ttu-id="16f10-123">Uscire da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16f10-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="16f10-124">Aprire Windows PowerShell 3,0 o versione successiva come amministratore globale, quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="16f10-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub

## Connect to the Microsoft StaffHub PowerShell module

1. Run the following:

    ```
    <span data-ttu-id="16f10-125">Connect-StaffHub</span><span class="sxs-lookup"><span data-stu-id="16f10-125">Connect-StaffHub</span></span>
    ```

2. When you're prompted, log in as a global admin.

## Related topics

- [Microsoft StaffHub PowerShell reference](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [Move your Microsoft StaffHub teams to Shifts in Teams](move-staffhub-teams-to-shifts-in-teams.md)
