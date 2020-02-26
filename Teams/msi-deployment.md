---
title: Installare Microsoft teams tramite MSI tramite Microsoft endpoint Configuration Manager
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
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc57222f56235c71c676f952cb0dd5aa149dc4e3
ms.sourcegitcommit: df552697ae9c8c01c40f816bbe98b251db147199
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277979"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="235cf-103">Installare Microsoft teams con Microsoft endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="235cf-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="235cf-104">Vedere la sessione seguente per informazioni sui vantaggi del client desktop di Windows, su come pianificare la distribuzione e su come distribuirla: [Team client desktop di Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="235cf-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="235cf-105">Per usare Microsoft endpoint Configuration Manager o criteri di gruppo o qualsiasi meccanismo di distribuzione di terze parti per una distribuzione ampia, Microsoft ha fornito file MSI (sia 32 bit che 64 bit) che gli amministratori possono usare per la distribuzione in blocco dei team per selezionare gli utenti o computer.</span><span class="sxs-lookup"><span data-stu-id="235cf-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="235cf-106">Gli amministratori possono usare questi file per distribuire in remoto i team in modo che gli utenti non debbano scaricare manualmente l'app teams.</span><span class="sxs-lookup"><span data-stu-id="235cf-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="235cf-107">Una volta distribuiti, i team verranno avviati automaticamente per tutti gli utenti che accedono a tale computer.</span><span class="sxs-lookup"><span data-stu-id="235cf-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="235cf-108">Puoi disabilitare l'avvio automatico dopo l'installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="235cf-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="235cf-109">[Vedere di seguito](#disable-auto-launch-for-the-msi-installer).) Ti consigliamo di distribuire il pacchetto nel computer, in modo che tutti i nuovi utenti della macchina beneficeranno anche di questa distribuzione.</span><span class="sxs-lookup"><span data-stu-id="235cf-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="235cf-110">Questi sono i collegamenti ai file MSI:</span><span class="sxs-lookup"><span data-stu-id="235cf-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="235cf-111">Entità</span><span class="sxs-lookup"><span data-stu-id="235cf-111">Entity</span></span>  |<span data-ttu-id="235cf-112">32 bit</span><span class="sxs-lookup"><span data-stu-id="235cf-112">32 bit</span></span>      |<span data-ttu-id="235cf-113">64 bit</span><span class="sxs-lookup"><span data-stu-id="235cf-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="235cf-114">Commerciale</span><span class="sxs-lookup"><span data-stu-id="235cf-114">Commercial</span></span>     | [<span data-ttu-id="235cf-115">32 bit</span><span class="sxs-lookup"><span data-stu-id="235cf-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="235cf-116">64 bit</span><span class="sxs-lookup"><span data-stu-id="235cf-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="235cf-117">Governo federale-GCC</span><span class="sxs-lookup"><span data-stu-id="235cf-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="235cf-118">32 bit</span><span class="sxs-lookup"><span data-stu-id="235cf-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="235cf-119">64 bit</span><span class="sxs-lookup"><span data-stu-id="235cf-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="235cf-120">Governo federale-GCC High</span><span class="sxs-lookup"><span data-stu-id="235cf-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="235cf-121">32 bit</span><span class="sxs-lookup"><span data-stu-id="235cf-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="235cf-122">64 bit</span><span class="sxs-lookup"><span data-stu-id="235cf-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="235cf-123">Governo federale-DoD</span><span class="sxs-lookup"><span data-stu-id="235cf-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="235cf-124">32 bit</span><span class="sxs-lookup"><span data-stu-id="235cf-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="235cf-125">64 bit</span><span class="sxs-lookup"><span data-stu-id="235cf-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="235cf-126">I team possono anche essere inclusi in una distribuzione di Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="235cf-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="235cf-127">Per altre informazioni, vedere [distribuire Microsoft teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="235cf-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="235cf-128">Per altre informazioni su Microsoft endpoint Configuration Manager, vedere [che cos'è Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="235cf-128">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="235cf-129">Procedura di distribuzione (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="235cf-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="235cf-130">Recuperare il pacchetto più recente.</span><span class="sxs-lookup"><span data-stu-id="235cf-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="235cf-131">Usare i valori predefiniti prepopolati da MSI.</span><span class="sxs-lookup"><span data-stu-id="235cf-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="235cf-132">Eseguire la distribuzione in computer quando possibile.</span><span class="sxs-lookup"><span data-stu-id="235cf-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="235cf-133">Funzionamento del pacchetto MSI di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="235cf-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="235cf-134">Installazione del PC</span><span class="sxs-lookup"><span data-stu-id="235cf-134">PC installation</span></span>

<span data-ttu-id="235cf-135">Il programma di installazione di teams MSI verrà collocato nei file di programmazione.</span><span class="sxs-lookup"><span data-stu-id="235cf-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="235cf-136">Ogni volta che un utente accede a un nuovo profilo utente di Windows, verrà avviato il programma di installazione e verrà installata una copia dell'app teams nella cartella AppData dell'utente.</span><span class="sxs-lookup"><span data-stu-id="235cf-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="235cf-137">Se un utente ha già installato l'app teams nella cartella AppData, il programma di installazione MSI ignorerà il processo per l'utente.</span><span class="sxs-lookup"><span data-stu-id="235cf-137">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="235cf-138">Non usare il file MSI per distribuire gli aggiornamenti, perché il client verrà aggiornato automaticamente quando viene rilevata una nuova versione disponibile nel servizio.</span><span class="sxs-lookup"><span data-stu-id="235cf-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="235cf-139">Per ridistribuire il programma di installazione più recente, usare il processo di ridistribuzione di MSI descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="235cf-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="235cf-140">Se si distribuisce una versione precedente del pacchetto MSI, il client verrà aggiornato automaticamente, ad eccezione degli ambienti VDI, quando possibile per l'utente.</span><span class="sxs-lookup"><span data-stu-id="235cf-140"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="235cf-141">Se viene distribuita una versione molto vecchia, il file MSI attiverà un aggiornamento dell'app prima che l'utente possa usare teams.</span><span class="sxs-lookup"><span data-stu-id="235cf-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="235cf-142">Non è consigliabile modificare le posizioni di installazione predefinite, perché questo potrebbe interrompere il flusso di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="235cf-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="235cf-143">Una versione troppo vecchia impedirà alla fine di impedire agli utenti di accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="235cf-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="235cf-144">Requisiti del computer di destinazione</span><span class="sxs-lookup"><span data-stu-id="235cf-144">Target computer requirements</span></span>

- <span data-ttu-id="235cf-145">.NET Framework 4,5 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="235cf-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="235cf-146">Windows 7 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="235cf-146">Windows 7 or later</span></span>
- <span data-ttu-id="235cf-147">Windows Server 2012 R2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="235cf-147">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="235cf-148">3 GB di spazio su disco per ogni profilo utente (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="235cf-148">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="235cf-149">Installazione VDI</span><span class="sxs-lookup"><span data-stu-id="235cf-149">VDI installation</span></span>

<span data-ttu-id="235cf-150">Per istruzioni complete su come distribuire l'app desktop teams su VDI, vedere [team per l'infrastruttura desktop virtualizzata](teams-for-vdi.md).</span><span class="sxs-lookup"><span data-stu-id="235cf-150">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="235cf-151">Procedura per la pulizia e la ridistribuzione</span><span class="sxs-lookup"><span data-stu-id="235cf-151">Clean up and redeployment procedure</span></span>

<span data-ttu-id="235cf-152">Se un utente disinstalla teams dal proprio profilo utente, il programma di installazione MSI rileva che l'utente ha disinstallato l'app teams e non ha più installato Team per il profilo utente.</span><span class="sxs-lookup"><span data-stu-id="235cf-152">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="235cf-153">Per ridistribuire team per l'utente in un determinato computer in cui è stata disinstallata, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="235cf-153">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="235cf-154">Disinstallare l'app teams installata per ogni profilo utente.</span><span class="sxs-lookup"><span data-stu-id="235cf-154">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="235cf-155">Dopo la disinstallazione, eliminare la directory in modo ricorsivo in%localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="235cf-155">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="235cf-156">Ridistribuire il pacchetto MSI in quel particolare computer.</span><span class="sxs-lookup"><span data-stu-id="235cf-156">Redeploy the MSI package to that particular computer.</span></span>

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="235cf-157">Impedire l'avvio automatico dei team dopo l'installazione</span><span class="sxs-lookup"><span data-stu-id="235cf-157">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="235cf-158">Il comportamento predefinito di MSI consiste nell'installare l'app teams non appena un utente accede e quindi avvia automaticamente teams.</span><span class="sxs-lookup"><span data-stu-id="235cf-158">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="235cf-159">Se non si vuole che i team vengano avviati automaticamente per gli utenti dopo l'installazione, è possibile usare criteri di gruppo per impostare un'impostazione di criteri o disabilitare l'avvio automatico per il programma di installazione MSI.</span><span class="sxs-lookup"><span data-stu-id="235cf-159">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

#### <a name="use-group-policy-recommended"></a><span data-ttu-id="235cf-160">Usare criteri di gruppo (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="235cf-160">Use Group Policy (recommended)</span></span>

<span data-ttu-id="235cf-161">Consentire l' **avvio automatico di Microsoft teams dopo** l'impostazione di criteri di gruppo installazione.</span><span class="sxs-lookup"><span data-stu-id="235cf-161">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="235cf-162">Questa impostazione dei criteri può essere trovata in team Configurazione utente\Modelli Amministrativi\microsoft.</span><span class="sxs-lookup"><span data-stu-id="235cf-162">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="235cf-163">Questo è il metodo consigliato perché puoi disattivare o attivare l'impostazione dei criteri in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="235cf-163">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="235cf-164">Quando si abilita questa impostazione per i criteri prima dell'installazione di teams, teams non si avvia automaticamente quando gli utenti accedono a Windows.</span><span class="sxs-lookup"><span data-stu-id="235cf-164">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="235cf-165">Dopo che un utente ha eseguito l'accesso a teams per la prima volta, teams avvia automaticamente la volta successiva che l'utente accede.</span><span class="sxs-lookup"><span data-stu-id="235cf-165">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="235cf-166">Per altre informazioni, vedere [usare criteri di gruppo per evitare che i team vengano avviati automaticamente dopo l'installazione](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span><span class="sxs-lookup"><span data-stu-id="235cf-166">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="235cf-167">Se i team sono già stati distribuiti e si vuole impostare questo criterio per disabilitare l'autostart di teams, impostare prima di tutto l'impostazione di criteri di gruppo sul valore desiderato e quindi eseguire lo [script di reset autostart di teams](scripts/powershell-script-teams-reset-autostart.md) per ogni singolo utente.</span><span class="sxs-lookup"><span data-stu-id="235cf-167">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="235cf-168">Disabilitare l'avvio automatico per il programma di installazione MSI</span><span class="sxs-lookup"><span data-stu-id="235cf-168">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="235cf-169">È possibile disabilitare l'avvio automatico per il programma di installazione MSI usando il parametro **Options = "noAutoStart = true"** come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="235cf-169">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="235cf-170">Per la versione a 32 bit</span><span class="sxs-lookup"><span data-stu-id="235cf-170">For the 32-bit version</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```

<span data-ttu-id="235cf-171">Per la versione a 64 bit</span><span class="sxs-lookup"><span data-stu-id="235cf-171">For the 64-bit version</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

<span data-ttu-id="235cf-172">Quando un utente accede a Windows, teams viene installato con MSI e viene aggiunto un collegamento per avviare teams al desktop dell'utente.</span><span class="sxs-lookup"><span data-stu-id="235cf-172">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="235cf-173">I team non si avviano finché l'utente non avvia manualmente teams.</span><span class="sxs-lookup"><span data-stu-id="235cf-173">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="235cf-174">Dopo che l'utente ha avviato manualmente teams, teams avvia automaticamente ogni volta che l'utente effettua l'accesso.</span><span class="sxs-lookup"><span data-stu-id="235cf-174">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

> [!Note]
> <span data-ttu-id="235cf-175">Se si esegue manualmente il file MSI, assicurarsi di eseguirlo con autorizzazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="235cf-175">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="235cf-176">Anche se viene eseguito come amministratore, senza eseguirlo con autorizzazioni elevate, il programma di installazione non sarà in grado di configurare l'opzione per disabilitare l'avvio automatico.</span><span class="sxs-lookup"><span data-stu-id="235cf-176">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
