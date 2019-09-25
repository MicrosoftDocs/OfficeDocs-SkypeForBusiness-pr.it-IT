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
description: Informazioni su come installare e connettersi alla versione prerelease del modulo di PowerShell Microsoft StaffHub.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80f8f586d8a2a41d0d716e0821eb1f6d8d4bcbee
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142035"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="30d82-103">Installare il modulo di PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="30d82-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30d82-104">Efficace il 1 ° ottobre 2019, Microsoft StaffHub sarà ritirato.</span><span class="sxs-lookup"><span data-stu-id="30d82-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="30d82-105">Stiamo costruendo funzionalità di StaffHub in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="30d82-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="30d82-106">Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo.</span><span class="sxs-lookup"><span data-stu-id="30d82-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="30d82-107">StaffHub smetterà di funzionare per tutti gli utenti il 1 ° ottobre 2019.</span><span class="sxs-lookup"><span data-stu-id="30d82-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="30d82-108">Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams.</span><span class="sxs-lookup"><span data-stu-id="30d82-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="30d82-109">Per altre informazioni, vedere [Microsoft StaffHub per ritirarsi](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="30d82-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="30d82-110">Usare i passaggi descritti in questo articolo per installare e connettersi alla versione prerelease del modulo di PowerShell Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="30d82-110">Use the steps in this article to install and connect to the prerelease version of the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="30d82-111">Sarà necessario questo per [trasferire i team di StaffHub in teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="30d82-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="30d82-112">Installare la versione prerelease del modulo di PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="30d82-112">Install the prerelease version of the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="30d82-113">Aprire Windows PowerShell 3,0 o versione successiva come amministratore. A tale scopo, fare clic sul pulsante **Start**, digitare **Windows PowerShell**, fare clic con il pulsante destro del mouse su **Windows PowerShell**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="30d82-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="30d82-114">Per ottenere la versione più recente di Windows PowerShell, vedere [installazione di Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="30d82-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="30d82-115">Eseguire la procedura seguente per installare la versione prerelease del modulo di PowerShell StaffHub:</span><span class="sxs-lookup"><span data-stu-id="30d82-115">Run the following to install the prerelease version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. <span data-ttu-id="30d82-116">Potrebbe essere visualizzato il messaggio di avviso:</span><span class="sxs-lookup"><span data-stu-id="30d82-116">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    <span data-ttu-id="30d82-117">Digitare `Y`e quindi fare clic `Enter`su.</span><span class="sxs-lookup"><span data-stu-id="30d82-117">Type `Y`, and then click `Enter`.</span></span>
 
4. <span data-ttu-id="30d82-118">Uscire da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30d82-118">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="30d82-119">Connettersi al modulo di PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="30d82-119">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="30d82-120">Esegui il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="30d82-120">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="30d82-121">Quando viene richiesto, accedere come amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="30d82-121">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="30d82-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="30d82-122">Related topics</span></span>

- [<span data-ttu-id="30d82-123">Riferimento a Microsoft PowerShell per StaffHub</span><span class="sxs-lookup"><span data-stu-id="30d82-123">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="30d82-124">Spostare i team di Microsoft StaffHub in turni in teams</span><span class="sxs-lookup"><span data-stu-id="30d82-124">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
