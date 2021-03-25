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
description: Informazioni su come aggiornare manualmente il dispositivo Microsoft Teams Rooms a una versione specifica.
ms.openlocfilehash: 3353758fa36534994336fc81e0a759c8b9f3c678
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117514"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="e89e8-103">Aggiornare manualmente un dispositivo Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="e89e8-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="e89e8-104">L'app Microsoft Teams Rooms viene distribuita tramite Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="e89e8-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="e89e8-105">Gli aggiornamenti dell'app vengono installati automaticamente da Microsoft Store durante la manutenzione notturna; questo è il metodo consigliato per ottenere gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="e89e8-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="e89e8-106">Esistono tuttavia alcune situazioni in cui un dispositivo Teams Rooms non può ricevere aggiornamenti da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="e89e8-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="e89e8-107">Ad esempio, i criteri di sicurezza potrebbero non consentire la connessione dei dispositivi a Internet o il download delle app da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="e89e8-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="e89e8-108">Oppure, potresti voler aggiornare un dispositivo prima di eseguire la configurazione, durante il quale Microsoft Store non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="e89e8-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="e89e8-109">Se non è possibile ottenere gli aggiornamenti da Microsoft Store, è possibile usare uno script di PowerShell di aggiornamento dell'app offline per aggiornare manualmente i dispositivi di Teams Rooms a una versione più recente dell'app Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e89e8-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="e89e8-110">Seguire la procedura descritta in questo articolo per aggiornare manualmente i dispositivi di Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e89e8-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="e89e8-111">Questo processo può aggiornare solo un dispositivo Teams Rooms con l'app Teams Rooms già installata.</span><span class="sxs-lookup"><span data-stu-id="e89e8-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="e89e8-112">Non può essere usato per eseguire una nuova installazione.</span><span class="sxs-lookup"><span data-stu-id="e89e8-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="e89e8-113">Non può inoltre essere usato per eseguire il downgrade dell'app a una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e89e8-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="e89e8-114">Per eseguire una nuova installazione dell'app Teams Rooms, contattare il produttore del dispositivo per ottenere elementi multimediali specifici oppure vedere [Preparare il supporto di installazione.](console.md#prepare-the-installation-media)</span><span class="sxs-lookup"><span data-stu-id="e89e8-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="e89e8-115">Passaggio 1: Scaricare lo script di aggiornamento dell'app offline</span><span class="sxs-lookup"><span data-stu-id="e89e8-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="e89e8-116">Prima di tutto, scaricare l'ultima versione dello script di aggiornamento dell'app offline.</span><span class="sxs-lookup"><span data-stu-id="e89e8-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="e89e8-117">Per scaricare lo script, fare clic su <https://go.microsoft.com/fwlink/?linkid=2151817> .</span><span class="sxs-lookup"><span data-stu-id="e89e8-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="e89e8-118">Lo script verrà scaricato nella cartella di download predefinita del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e89e8-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="e89e8-119">I file scaricati potrebbero essere contrassegnati come bloccati da Windows.</span><span class="sxs-lookup"><span data-stu-id="e89e8-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="e89e8-120">Se è necessario eseguire lo script senza alcuna interazione, è necessario sbloccarlo.</span><span class="sxs-lookup"><span data-stu-id="e89e8-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="e89e8-121">Per sbloccare lo script, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e89e8-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="e89e8-122">Fare clic con il pulsante destro del mouse sul file in Esplora file</span><span class="sxs-lookup"><span data-stu-id="e89e8-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="e89e8-123">Fare clic **su Proprietà**</span><span class="sxs-lookup"><span data-stu-id="e89e8-123">Click **Properties**</span></span>
3. <span data-ttu-id="e89e8-124">Selezionare **Sblocca**</span><span class="sxs-lookup"><span data-stu-id="e89e8-124">Select **Unblock**</span></span>
4. <span data-ttu-id="e89e8-125">Fare clic **su OK**</span><span class="sxs-lookup"><span data-stu-id="e89e8-125">Click **OK**</span></span>

<span data-ttu-id="e89e8-126">Per sbloccare lo script con PowerShell, vedere [Sblocca file](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span><span class="sxs-lookup"><span data-stu-id="e89e8-126">To unblock the script using PowerShell, see [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="e89e8-127">Dopo aver scaricato lo script di aggiornamento dell'app offline, trasferire il file nel dispositivo Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e89e8-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="e89e8-128">È possibile trasferire un file nel dispositivo usando un'unità USB o accedendo al file da una condivisione file di rete mentre è attiva la modalità di amministrazione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e89e8-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="e89e8-129">Assicurarsi di prendere nota della posizione in cui si salva il file nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e89e8-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="e89e8-130">Passaggio 2: Eseguire lo script per aggiornare l'app Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="e89e8-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="e89e8-131">Lo script di aggiornamento dell'app offline deve essere eseguito da un prompt dei comandi con privilegi elevati mentre l'utente Skype (l'utente con cui viene eseguita l'app) è ancora connesso.</span><span class="sxs-lookup"><span data-stu-id="e89e8-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="e89e8-132">Per altre informazioni su come accedere a un account amministratore per usare il prompt dei comandi con privilegi elevati mentre l'utente Skype è ancora connesso, vedere Passare alla modalità di amministrazione e tornare alla modalità di amministrazione quando [l'app Microsoft Teams Rooms](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e89e8-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="e89e8-133">Eseguire le operazioni seguenti per eseguire lo script da un prompt dei comandi con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="e89e8-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="e89e8-134">Passare alla modalità di amministrazione</span><span class="sxs-lookup"><span data-stu-id="e89e8-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="e89e8-135">Fare clic sull'icona Start, **digitare Prompt dei comandi** e quindi selezionare Esegui come **amministratore**</span><span class="sxs-lookup"><span data-stu-id="e89e8-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="e89e8-136">Eseguire il comando seguente, dove `<path to script>` include il percorso completo dello script e il nome del file di script:</span><span class="sxs-lookup"><span data-stu-id="e89e8-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="e89e8-137">Ad esempio, se il file script si trova in `C:\Users\Admin\Downloads` e il nome del file script è , eseguire il comando `MTR-Update-4.5.6.7.ps1` seguente:</span><span class="sxs-lookup"><span data-stu-id="e89e8-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="e89e8-138">Consentire l'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="e89e8-138">Allow the script to run.</span></span> <span data-ttu-id="e89e8-139">Al termine, lo script riavvierà il dispositivo Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e89e8-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="e89e8-140">È anche possibile eseguire lo script usando PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="e89e8-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="e89e8-141">Per altre informazioni sull'uso di PowerShell remoto con i dispositivi Teams Rooms, vedere [Gestione remota tramite PowerShell.](rooms-operations.md#remote-management-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="e89e8-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="e89e8-142">Passaggio 3: Verificare che l'app sia stata aggiornata correttamente</span><span class="sxs-lookup"><span data-stu-id="e89e8-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="e89e8-143">Se lo script viene eseguito correttamente, il dispositivo verrà riavviato nell'app Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e89e8-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="e89e8-144">Se lo script rileva un problema, indicherà il problema nella riga di comando e ne registrerà l'output in un file.</span><span class="sxs-lookup"><span data-stu-id="e89e8-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="e89e8-145">Seguire le istruzioni fornite nello script.</span><span class="sxs-lookup"><span data-stu-id="e89e8-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="e89e8-146">Se è necessario contattare il supporto tecnico Microsoft, assicurarsi di includere il file di log insieme alla richiesta di supporto.</span><span class="sxs-lookup"><span data-stu-id="e89e8-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="e89e8-147">Lo script fornirà il percorso del file di log.</span><span class="sxs-lookup"><span data-stu-id="e89e8-147">The script will provide you with the path to the log file.</span></span>