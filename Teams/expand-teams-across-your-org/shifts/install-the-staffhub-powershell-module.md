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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464666"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="0aa6e-103">Installare il modulo di PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="0aa6e-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0aa6e-104">Efficace il 1 ° ottobre 2019, Microsoft StaffHub sarà ritirato.</span><span class="sxs-lookup"><span data-stu-id="0aa6e-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="0aa6e-105">Stiamo costruendo funzionalità di StaffHub in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0aa6e-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="0aa6e-106">Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo.</span><span class="sxs-lookup"><span data-stu-id="0aa6e-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="0aa6e-107">StaffHub smetterà di funzionare per tutti gli utenti il 1 ° ottobre 2019.</span><span class="sxs-lookup"><span data-stu-id="0aa6e-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="0aa6e-108">Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams.</span><span class="sxs-lookup"><span data-stu-id="0aa6e-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="0aa6e-109">Per altre informazioni, vedere [Microsoft StaffHub per](microsoft-staffhub-to-be-retired.md)ritirarsi.</span><span class="sxs-lookup"><span data-stu-id="0aa6e-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="0aa6e-110">Seguire i passaggi di questo articolo per installare e connettersi al modulo di PowerShell Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="0aa6e-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="0aa6e-111">Per gestire StaffHub, è necessario usare PowerShell e trasferire i team di StaffHub in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0aa6e-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="0aa6e-112">Installare il modulo di PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="0aa6e-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="0aa6e-113">Aprire Windows PowerShell 3,0 o versione successiva come amministratore. A tale scopo, fare clic sul pulsante **Start**, digitare **Windows PowerShell**, fare clic con il pulsante destro del mouse su **Windows PowerShell**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="0aa6e-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="0aa6e-114">Per ottenere la versione più recente di Windows PowerShell, vedere [installazione di Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0aa6e-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="0aa6e-115">Eseguire la procedura seguente per installare la versione stabile corrente del modulo di PowerShell StaffHub:</span><span class="sxs-lookup"><span data-stu-id="0aa6e-115">Run the following to install the current stable version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    <span data-ttu-id="0aa6e-116">È possibile eseguire questo comando solo se è necessario installare la versione più recente, che potrebbe avere più instabilità rispetto alla versione stabile corrente:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span><span class="sxs-lookup"><span data-stu-id="0aa6e-116">You can run this command only if you need to install the latest version, which may have more instabilities than the current stable version: `Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span></span>

     > [!NOTE]
     > <span data-ttu-id="0aa6e-117">Se viene visualizzato un messaggio di errore durante l'installazione della versione più recente con più instabilità, è possibile eseguire:`Install-Module PowershellGet -Force`</span><span class="sxs-lookup"><span data-stu-id="0aa6e-117">If you receive an error during the installation of the latest version with more instabilities, you can run: `Install-Module PowershellGet -Force`</span></span>

3. <span data-ttu-id="0aa6e-118">Potrebbe essere visualizzato il messaggio di avviso:</span><span class="sxs-lookup"><span data-stu-id="0aa6e-118">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

<span data-ttu-id="0aa6e-119">Digitare `Y` e fare `Enter`clic su.</span><span class="sxs-lookup"><span data-stu-id="0aa6e-119">Type `Y` and click `Enter`.</span></span>
 
4. <span data-ttu-id="0aa6e-120">Uscire da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0aa6e-120">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="0aa6e-121">Connettersi al modulo di PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="0aa6e-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="0aa6e-122">Esegui il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="0aa6e-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="0aa6e-123">Quando viene richiesto, accedere come amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="0aa6e-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0aa6e-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0aa6e-124">Related topics</span></span>

- [<span data-ttu-id="0aa6e-125">Riferimento a Microsoft PowerShell per StaffHub</span><span class="sxs-lookup"><span data-stu-id="0aa6e-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="0aa6e-126">Spostare i team di Microsoft StaffHub in turni in teams</span><span class="sxs-lookup"><span data-stu-id="0aa6e-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
