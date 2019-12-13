---
title: Installare Microsoft teams con MSI tramite SCCM
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Gli amministratori possono usare il team MSI per distribuire in blocco Microsoft teams per selezionare utenti o computer.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e32eb60b238d606ac30fe74c7551e01efe88242a
ms.sourcegitcommit: c2e315d0fcec742d2e1ba5ad90dffd1a1157a466
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/13/2019
ms.locfileid: "40002230"
---
# <a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="b9309-103">Installare Microsoft teams con MSI</span><span class="sxs-lookup"><span data-stu-id="b9309-103">Install Microsoft Teams using MSI</span></span>

> [!Tip]
> <span data-ttu-id="b9309-104">Vedere la sessione seguente per informazioni sui vantaggi del client desktop di Windows, su come pianificare la distribuzione e su come distribuirla: [Team client desktop di Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="b9309-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="b9309-105">Per usare System Center Configuration Manager o criteri di gruppo o qualsiasi meccanismo di distribuzione di terze parti per una distribuzione ampia, Microsoft ha fornito file MSI (sia 32 bit che 64 bit) che gli amministratori possono usare per la distribuzione in blocco dei team per selezionare utenti o computer.</span><span class="sxs-lookup"><span data-stu-id="b9309-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="b9309-106">Gli amministratori possono usare questi file per distribuire in remoto i team in modo che gli utenti non debbano scaricare manualmente l'app teams.</span><span class="sxs-lookup"><span data-stu-id="b9309-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="b9309-107">Una volta distribuiti, i team verranno avviati automaticamente per tutti gli utenti che accedono a tale computer.</span><span class="sxs-lookup"><span data-stu-id="b9309-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="b9309-108">Puoi disabilitare l'avvio automatico dopo l'installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="b9309-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="b9309-109">[Vedere di seguito](#disable-auto-launch-for-the-msi-installer).) Ti consigliamo di distribuire il pacchetto nel computer, in modo che tutti i nuovi utenti della macchina beneficeranno anche di questa distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b9309-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="b9309-110">Questi sono i collegamenti ai file MSI:</span><span class="sxs-lookup"><span data-stu-id="b9309-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="b9309-111">Entità</span><span class="sxs-lookup"><span data-stu-id="b9309-111">Entity</span></span>  |<span data-ttu-id="b9309-112">32 bit</span><span class="sxs-lookup"><span data-stu-id="b9309-112">32 bit</span></span>      |<span data-ttu-id="b9309-113">64 bit</span><span class="sxs-lookup"><span data-stu-id="b9309-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="b9309-114">Commerciale</span><span class="sxs-lookup"><span data-stu-id="b9309-114">Commercial</span></span>     | [<span data-ttu-id="b9309-115">32 bit</span><span class="sxs-lookup"><span data-stu-id="b9309-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="b9309-116">64 bit</span><span class="sxs-lookup"><span data-stu-id="b9309-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="b9309-117">Governo federale-GCC</span><span class="sxs-lookup"><span data-stu-id="b9309-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="b9309-118">32 bit</span><span class="sxs-lookup"><span data-stu-id="b9309-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="b9309-119">64 bit</span><span class="sxs-lookup"><span data-stu-id="b9309-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="b9309-120">Governo federale-GCC High</span><span class="sxs-lookup"><span data-stu-id="b9309-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="b9309-121">32 bit</span><span class="sxs-lookup"><span data-stu-id="b9309-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="b9309-122">64 bit</span><span class="sxs-lookup"><span data-stu-id="b9309-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="b9309-123">Governo federale-DoD</span><span class="sxs-lookup"><span data-stu-id="b9309-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="b9309-124">32 bit</span><span class="sxs-lookup"><span data-stu-id="b9309-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="b9309-125">64 bit</span><span class="sxs-lookup"><span data-stu-id="b9309-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="b9309-126">I team possono anche essere inclusi in una distribuzione di Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="b9309-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="b9309-127">Per altre informazioni, vedere [distribuire Microsoft teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="b9309-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="b9309-128">Per altre informazioni su SCCM, vedere [Introduzione a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="b9309-128">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="b9309-129">Procedura di distribuzione (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="b9309-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="b9309-130">Recuperare il pacchetto più recente.</span><span class="sxs-lookup"><span data-stu-id="b9309-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="b9309-131">Usare i valori predefiniti prepopolati da MSI.</span><span class="sxs-lookup"><span data-stu-id="b9309-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="b9309-132">Eseguire la distribuzione in computer quando possibile.</span><span class="sxs-lookup"><span data-stu-id="b9309-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="b9309-133">Funzionamento del pacchetto MSI di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9309-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="b9309-134">Installazione del PC</span><span class="sxs-lookup"><span data-stu-id="b9309-134">PC installation</span></span>

<span data-ttu-id="b9309-135">Il programma di installazione di teams MSI verrà collocato nei file di programmazione.</span><span class="sxs-lookup"><span data-stu-id="b9309-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="b9309-136">Ogni volta che un utente accede a un nuovo profilo utente di Windows, verrà avviato il programma di installazione e verrà installata una copia dell'app teams nella cartella AppData dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b9309-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="b9309-137">Se un utente ha già installato l'app teams nella cartella AppData, il programma di installazione MSI ignorerà il processo per l'utente.</span><span class="sxs-lookup"><span data-stu-id="b9309-137">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="b9309-138">Non usare il file MSI per distribuire gli aggiornamenti, perché il client verrà aggiornato automaticamente quando viene rilevata una nuova versione disponibile nel servizio.</span><span class="sxs-lookup"><span data-stu-id="b9309-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="b9309-139">Per ridistribuire il programma di installazione più recente, usare il processo di ridistribuzione di MSI descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="b9309-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="b9309-140">Se si distribuisce una versione precedente del pacchetto MSI, il client verrà aggiornato automaticamente, ad eccezione degli ambienti VDI, quando possibile per l'utente.</span><span class="sxs-lookup"><span data-stu-id="b9309-140"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="b9309-141">Se viene distribuita una versione molto vecchia, il file MSI attiverà un aggiornamento dell'app prima che l'utente possa usare teams.</span><span class="sxs-lookup"><span data-stu-id="b9309-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="b9309-142">Non è consigliabile modificare le posizioni di installazione predefinite, perché questo potrebbe interrompere il flusso di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b9309-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="b9309-143">Una versione troppo vecchia impedirà alla fine di impedire agli utenti di accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="b9309-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="b9309-144">Requisiti del computer di destinazione</span><span class="sxs-lookup"><span data-stu-id="b9309-144">Target computer requirements</span></span>

- <span data-ttu-id="b9309-145">.NET Framework 4,5 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="b9309-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="b9309-146">Windows 7 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="b9309-146">Windows 7 or later</span></span>
- <span data-ttu-id="b9309-147">3 GB di spazio su disco per ogni profilo utente (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="b9309-147">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="b9309-148">Installazione VDI</span><span class="sxs-lookup"><span data-stu-id="b9309-148">VDI installation</span></span>

<span data-ttu-id="b9309-149">Per istruzioni complete su come distribuire l'app desktop teams su VDI, vedere [team per l'infrastruttura desktop virtualizzata](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="b9309-149">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="b9309-150">Procedura per la pulizia e la ridistribuzione</span><span class="sxs-lookup"><span data-stu-id="b9309-150">Clean up and redeployment procedure</span></span>

<span data-ttu-id="b9309-151">Se un utente disinstalla teams dal proprio profilo utente, il programma di installazione MSI rileva che l'utente ha disinstallato l'app teams e non ha più installato Team per il profilo utente.</span><span class="sxs-lookup"><span data-stu-id="b9309-151">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="b9309-152">Per ridistribuire team per l'utente in un determinato computer in cui è stata disinstallata, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9309-152">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="b9309-153">Disinstallare l'app teams installata per ogni profilo utente.</span><span class="sxs-lookup"><span data-stu-id="b9309-153">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="b9309-154">Dopo la disinstallazione, eliminare la directory in modo ricorsivo in%localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="b9309-154">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="b9309-155">Ridistribuire il pacchetto MSI in quel particolare computer.</span><span class="sxs-lookup"><span data-stu-id="b9309-155">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="b9309-156">È possibile usare lo script di [pulizia della distribuzione di Microsoft teams](scripts/Powershell-script-teams-deployment-clean-up.md) per completare i passaggi 1 e 2 tramite SCCM.</span><span class="sxs-lookup"><span data-stu-id="b9309-156">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="b9309-157">Disabilitare l'avvio automatico per il programma di installazione MSI</span><span class="sxs-lookup"><span data-stu-id="b9309-157">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="b9309-158">Il comportamento predefinito di MSI consiste nell'installare il client teams non appena un utente accede e quindi avvia automaticamente teams.</span><span class="sxs-lookup"><span data-stu-id="b9309-158">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="b9309-159">È possibile modificare questo comportamento con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9309-159">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="b9309-160">Quando un utente accede a Windows, i team verranno installati con MSI</span><span class="sxs-lookup"><span data-stu-id="b9309-160">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="b9309-161">Tuttavia, il client teams non si avvia finché l'utente non ha avviato manualmente i team</span><span class="sxs-lookup"><span data-stu-id="b9309-161">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="b9309-162">Viene aggiunto un collegamento per avviare teams sul desktop dell'utente</span><span class="sxs-lookup"><span data-stu-id="b9309-162">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="b9309-163">Una volta avviati manualmente, i team verranno avviati automaticamente ogni volta che l'utente accede</span><span class="sxs-lookup"><span data-stu-id="b9309-163">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="b9309-164">Per la versione a 32 bit</span><span class="sxs-lookup"><span data-stu-id="b9309-164">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="b9309-165">Per la versione a 64 bit</span><span class="sxs-lookup"><span data-stu-id="b9309-165">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
> <span data-ttu-id="b9309-166">Se si esegue manualmente il file MSI, assicurarsi di eseguirlo con autorizzazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="b9309-166">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="b9309-167">Anche se viene eseguito come amministratore, senza eseguirlo con autorizzazioni elevate, il programma di installazione non sarà in grado di configurare l'opzione per disabilitare l'avvio automatico.</span><span class="sxs-lookup"><span data-stu-id="b9309-167">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
