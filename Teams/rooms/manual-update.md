---
title: Aggiornare manualmente un dispositivo Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Informazioni su come aggiornare manualmente il dispositivo Sale di Microsoft Teams a una versione specifica.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731394"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="dc5f2-103">Aggiornare manualmente un dispositivo Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="dc5f2-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="dc5f2-104">L'app Sale di Microsoft Teams viene distribuita tramite Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="dc5f2-105">Gli aggiornamenti dell'app vengono installati automaticamente da Microsoft Store durante la manutenzione notturna; questo è il metodo consigliato per ottenere gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="dc5f2-106">In alcune situazioni, tuttavia, un dispositivo Sale di Teams non può ricevere gli aggiornamenti da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="dc5f2-107">Ad esempio, i criteri di sicurezza potrebbero non consentire la connessione a Internet dei dispositivi o il download di app da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="dc5f2-108">Oppure, potresti voler aggiornare un dispositivo prima di eseguire la configurazione, durante il quale Microsoft Store non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="dc5f2-109">Se non è possibile ottenere gli aggiornamenti da Microsoft Store, è possibile usare uno script di PowerShell per l'aggiornamento offline delle app per aggiornare manualmente i dispositivi della chat room di Teams a una versione più recente dell'app Sale di Teams.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="dc5f2-110">Seguire i passaggi di questo articolo per aggiornare manualmente i dispositivi di Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="dc5f2-111">Questo processo può aggiornare solo un dispositivo Teams Rooms con l'app Sale di Teams già installata.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="dc5f2-112">Non può essere usato per eseguire una nuova installazione.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="dc5f2-113">Non può inoltre essere usato per eseguire il downgrade dell'app a una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="dc5f2-114">Per eseguire una nuova installazione dell'app Sale di Teams, contattare il produttore del dispositivo per ottenere elementi multimediali specifici oppure vedere Preparare il [supporto di installazione.](console.md#prepare-the-installation-media)</span><span class="sxs-lookup"><span data-stu-id="dc5f2-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="dc5f2-115">Passaggio 1: Scaricare lo script di aggiornamento delle app offline</span><span class="sxs-lookup"><span data-stu-id="dc5f2-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="dc5f2-116">Prima di tutto, scaricare l'ultima versione dello script di aggiornamento dell'app offline.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="dc5f2-117">Per scaricare lo script, fare clic su <https://go.microsoft.com/fwlink/?linkid=2151817> .</span><span class="sxs-lookup"><span data-stu-id="dc5f2-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="dc5f2-118">Lo script verrà scaricato nella cartella download predefinita del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="dc5f2-119">I file scaricati potrebbero essere contrassegnati come bloccati da Windows.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="dc5f2-120">Se è necessario eseguire lo script senza alcuna interazione, è necessario sbloccare lo script.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="dc5f2-121">Per sbloccare lo script, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc5f2-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="dc5f2-122">Fare clic con il pulsante destro del mouse sul file in Esplora file</span><span class="sxs-lookup"><span data-stu-id="dc5f2-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="dc5f2-123">Fare clic **su Proprietà**</span><span class="sxs-lookup"><span data-stu-id="dc5f2-123">Click **Properties**</span></span>
3. <span data-ttu-id="dc5f2-124">Selezionare **Sblocca**</span><span class="sxs-lookup"><span data-stu-id="dc5f2-124">Select **Unblock**</span></span>
4. <span data-ttu-id="dc5f2-125">Fare clic **su OK**</span><span class="sxs-lookup"><span data-stu-id="dc5f2-125">Click **OK**</span></span>

<span data-ttu-id="dc5f2-126">Per sbloccare lo script con PowerShell, vedere [Sblocca file.](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)</span><span class="sxs-lookup"><span data-stu-id="dc5f2-126">To unblock the script using PowerShell, see [Unblock-File](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="dc5f2-127">Dopo aver scaricato lo script di aggiornamento dell'app offline, trasferire il file nel dispositivo Teams Room.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="dc5f2-128">Puoi trasferire un file nel dispositivo usando un'unità USB o accedendo al file da una condivisione file di rete mentre sei in modalità amministratore nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="dc5f2-129">Prendere nota della posizione in cui si salva il file nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="dc5f2-130">Passaggio 2: Eseguire lo script per aggiornare l'app Sale di Teams</span><span class="sxs-lookup"><span data-stu-id="dc5f2-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="dc5f2-131">Lo script di aggiornamento dell'app offline deve essere eseguito da un prompt dei comandi con privilegi elevati mentre l'utente Skype (l'utente con cui viene eseguita l'app) ha ancora eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="dc5f2-132">Per ulteriori informazioni su come accedere a un account amministratore per usare il prompt dei comandi con privilegi elevati mentre l'utente di Skype è ancora connesso, consulta Passare alla modalità amministratore e tornare quando [l'app Sale](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)di Microsoft Teams è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="dc5f2-133">Eseguire la procedura seguente per eseguire lo script da un prompt dei comandi con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="dc5f2-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="dc5f2-134">Passare alla modalità amministratore</span><span class="sxs-lookup"><span data-stu-id="dc5f2-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="dc5f2-135">Fare clic sull'icona Start, **digitare Prompt dei** comandi e quindi selezionare Esegui come **amministratore**</span><span class="sxs-lookup"><span data-stu-id="dc5f2-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="dc5f2-136">Eseguire il comando `<path to script>` seguente, che include il percorso completo dello script e il nome del file script:</span><span class="sxs-lookup"><span data-stu-id="dc5f2-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="dc5f2-137">Ad esempio, se il file script si trova in `C:\Users\Admin\Downloads` e il nome del file script è , eseguire il comando `MTR-Update-4.5.6.7.ps1` seguente:</span><span class="sxs-lookup"><span data-stu-id="dc5f2-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="dc5f2-138">Consentire l'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-138">Allow the script to run.</span></span> <span data-ttu-id="dc5f2-139">Al termine, lo script riavvierà il dispositivo Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="dc5f2-140">È anche possibile eseguire lo script usando una sessione remota di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="dc5f2-141">Per altre informazioni sull'uso di Una sessione remota di PowerShell con i dispositivi Room di Teams, vedere [Gestione remota con PowerShell.](rooms-operations.md#remote-management-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="dc5f2-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="dc5f2-142">Passaggio 3: Verificare che l'app sia stata aggiornata correttamente</span><span class="sxs-lookup"><span data-stu-id="dc5f2-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="dc5f2-143">Se lo script viene eseguito correttamente, il dispositivo verrà riavviato nell'app Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="dc5f2-144">Se lo script rileva un problema, indicherà quale è il problema nella riga di comando e registrerà l'output in un file.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="dc5f2-145">Seguire le istruzioni fornite nello script.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="dc5f2-146">Se è necessario contattare il supporto tecnico Microsoft, assicurarsi di includere il file di log insieme alla richiesta di supporto.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="dc5f2-147">Lo script fornirà il percorso del file di log.</span><span class="sxs-lookup"><span data-stu-id="dc5f2-147">The script will provide you with the path to the log file.</span></span>
