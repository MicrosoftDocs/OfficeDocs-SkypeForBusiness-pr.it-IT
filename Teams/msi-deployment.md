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
ms.openlocfilehash: 0b80b82a89fc162e33263c784480f619dcd5cf32
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37573372"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="2ef3b-103">Installare Microsoft teams con MSI</span><span class="sxs-lookup"><span data-stu-id="2ef3b-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="2ef3b-104">Vedere la sessione seguente per informazioni sui vantaggi del client desktop di Windows, su come pianificare la distribuzione e su come distribuirla: [Team client desktop di Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="2ef3b-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="2ef3b-105">Per usare System Center Configuration Manager o criteri di gruppo o qualsiasi meccanismo di distribuzione di terze parti per una distribuzione ampia, Microsoft ha fornito file MSI (sia [32 bit](https://aka.ms/teams32bitmsi) che [64 bit](https://aka.ms/teams64bitmsi)) che gli amministratori possono usare per la distribuzione in blocco dei team da selezionare utenti o computer.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="2ef3b-106">Gli amministratori possono usare questi file per distribuire in remoto i team in modo che gli utenti non debbano scaricare manualmente l'app teams.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="2ef3b-107">Una volta distribuiti, i team verranno avviati automaticamente per tutti gli utenti che accedono a tale computer.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="2ef3b-108">Puoi disabilitare l'avvio automatico dopo l'installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="2ef3b-109">[Vedere di seguito](#disable-auto-launch-for-the-msi-installer).) Ti consigliamo di distribuire il pacchetto nel computer, in modo che tutti i nuovi utenti della macchina beneficeranno anche di questa distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 

<span data-ttu-id="2ef3b-110">I team possono anche essere inclusi in una distribuzione di Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-110">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="2ef3b-111">Per altre informazioni, vedere [distribuire Microsoft teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="2ef3b-111">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>
 
> [!Note] 
> <span data-ttu-id="2ef3b-112">Per altre informazioni su SCCM, vedere [Introduzione a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="2ef3b-112">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="2ef3b-113">Procedura di distribuzione (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="2ef3b-113">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="2ef3b-114">Recuperare il pacchetto più recente.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-114">Retrieve the latest package.</span></span>
2. <span data-ttu-id="2ef3b-115">Usare i valori predefiniti prepopolati da MSI.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-115">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="2ef3b-116">Eseguire la distribuzione in computer quando possibile.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-116">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="2ef3b-117">Funzionamento del pacchetto MSI di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ef3b-117">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="2ef3b-118">Installazione del PC</span><span class="sxs-lookup"><span data-stu-id="2ef3b-118">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="2ef3b-119">Per informazioni su come distribuire Team in un ambiente Virtual DesktopInfrastructure (VDI), vedere [installazione VDI](#vdi-installation) .</span><span class="sxs-lookup"><span data-stu-id="2ef3b-119">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="2ef3b-120">Il programma di installazione di teams MSI verrà collocato nei file di programmazione.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-120">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="2ef3b-121">Ogni volta che un utente accede a un nuovo profilo utente di Windows, verrà avviato il programma di installazione e verrà installata una copia dell'app teams nella cartella AppData dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-121">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="2ef3b-122">Se un utente ha già installato l'app teams nella cartella AppData, il programma di installazione MSI ignorerà il processo per l'utente.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-122">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="2ef3b-123">Non usare il file MSI per distribuire gli aggiornamenti, perché il client verrà aggiornato automaticamente quando viene rilevata una nuova versione disponibile nel servizio.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-123">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="2ef3b-124">Per ridistribuire il programma di installazione più recente, usare il processo di ridistribuzione di MSI descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-124">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="2ef3b-125">Se si distribuisce una versione precedente del pacchetto MSI, il client verrà aggiornato automaticamente, ad eccezione degli ambienti VDI, quando possibile per l'utente.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-125"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="2ef3b-126">Se viene distribuita una versione molto vecchia, il file MSI attiverà un aggiornamento dell'app prima che l'utente possa usare teams.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-126">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="2ef3b-127">Non è consigliabile modificare le posizioni di installazione predefinite, perché questo potrebbe interrompere il flusso di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-127">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="2ef3b-128">Una versione troppo vecchia impedirà alla fine di impedire agli utenti di accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-128">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="2ef3b-129">Requisiti del computer di destinazione</span><span class="sxs-lookup"><span data-stu-id="2ef3b-129">Target computer requirements</span></span>

- <span data-ttu-id="2ef3b-130">.NET Framework 4,5 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="2ef3b-130">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="2ef3b-131">Windows 7 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="2ef3b-131">Windows 7 or later</span></span>
- <span data-ttu-id="2ef3b-132">3 GB di spazio su disco per ogni profilo utente (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="2ef3b-132">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="2ef3b-133">Installazione VDI</span><span class="sxs-lookup"><span data-stu-id="2ef3b-133">VDI installation</span></span>

<span data-ttu-id="2ef3b-134">Ecco il processo per distribuire l'app desktop teams.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-134">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="2ef3b-135">Per informazioni complete, vedere [team per l'infrastruttura desktop virtualizzata](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="2ef3b-135">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="2ef3b-136">Scaricare il pacchetto MSI teams usando uno dei collegamenti seguenti, a seconda dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-136">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="2ef3b-137">È consigliabile usare la versione a 64 bit per una VM VDI con un sistema operativo a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-137">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="2ef3b-138">versione a 32 bit</span><span class="sxs-lookup"><span data-stu-id="2ef3b-138">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="2ef3b-139">versione a 64 bit</span><span class="sxs-lookup"><span data-stu-id="2ef3b-139">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="2ef3b-140">Eseguire il comando seguente per installare il file MSI nella VM VDI o per completare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-140">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="2ef3b-141">Questo consente di installare i team nei file di programma.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-141">This installs Teams to Program Files.</span></span> <span data-ttu-id="2ef3b-142">A questo punto, la configurazione dell'immagine dorata è completa.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-142">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="2ef3b-143">La prossima sessione di accesso interattivo avvia team e richiede le credenziali.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-143">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="2ef3b-144">Tieni presente che non è possibile disabilitare l'avvio automatico dei team durante l'installazione di teams in VDI tramite la proprietà ALLUSER.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-144">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="2ef3b-145">Eseguire il comando seguente per disinstallare il file MSI dalla VM VDI o prepararsi per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-145">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="2ef3b-146">In questo articolo vengono disinstallati team da file di programma.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-146">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="2ef3b-147">Procedura per la pulizia e la ridistribuzione</span><span class="sxs-lookup"><span data-stu-id="2ef3b-147">Clean up and redeployment procedure</span></span>

<span data-ttu-id="2ef3b-148">Se un utente disinstalla teams dal proprio profilo utente, il programma di installazione MSI rileva che l'utente ha disinstallato l'app teams e non ha più installato Team per il profilo utente.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-148">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="2ef3b-149">Per ridistribuire team per l'utente in un determinato computer in cui è stata disinstallata, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ef3b-149">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="2ef3b-150">Disinstallare l'app teams installata per ogni profilo utente.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-150">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="2ef3b-151">Dopo la disinstallazione, eliminare la directory in modo ricorsivo in%localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-151">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="2ef3b-152">Ridistribuire il pacchetto MSI in quel particolare computer.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-152">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="2ef3b-153">È possibile usare lo script di [pulizia della distribuzione di Microsoft teams](scripts/Powershell-script-teams-deployment-clean-up.md) per completare i passaggi 1 e 2 tramite SCCM.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-153">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="2ef3b-154">Disabilitare l'avvio automatico per il programma di installazione MSI</span><span class="sxs-lookup"><span data-stu-id="2ef3b-154">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="2ef3b-155">Il comportamento predefinito di MSI consiste nell'installare il client teams non appena un utente accede e quindi avvia automaticamente teams.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-155">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="2ef3b-156">È possibile modificare questo comportamento con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ef3b-156">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="2ef3b-157">Quando un utente accede a Windows, i team verranno installati con MSI</span><span class="sxs-lookup"><span data-stu-id="2ef3b-157">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="2ef3b-158">Tuttavia, il client teams non si avvia finché l'utente non ha avviato manualmente i team</span><span class="sxs-lookup"><span data-stu-id="2ef3b-158">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="2ef3b-159">Viene aggiunto un collegamento per avviare teams sul desktop dell'utente</span><span class="sxs-lookup"><span data-stu-id="2ef3b-159">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="2ef3b-160">Una volta avviati manualmente, i team verranno avviati automaticamente ogni volta che l'utente accede</span><span class="sxs-lookup"><span data-stu-id="2ef3b-160">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="2ef3b-161">Per la versione a 32 bit</span><span class="sxs-lookup"><span data-stu-id="2ef3b-161">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="2ef3b-162">Per la versione a 64 bit</span><span class="sxs-lookup"><span data-stu-id="2ef3b-162">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="2ef3b-163">Se si esegue manualmente il file MSI, assicurarsi di eseguirlo con autorizzazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-163">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="2ef3b-164">Anche se viene eseguito come amministratore, senza eseguirlo con autorizzazioni elevate, il programma di installazione non sarà in grado di configurare l'opzione per disabilitare l'avvio automatico.</span><span class="sxs-lookup"><span data-stu-id="2ef3b-164">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
