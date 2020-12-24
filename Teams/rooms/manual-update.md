---
title: Aggiornare manualmente un dispositivo Microsoft teams rooms
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
description: Informazioni su come aggiornare manualmente il dispositivo Microsoft teams rooms in una versione specifica.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731394"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="58a46-103">Aggiornare manualmente un dispositivo Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="58a46-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="58a46-104">L'app Microsoft teams Rooms viene distribuita tramite Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="58a46-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="58a46-105">Gli aggiornamenti dell'app vengono installati automaticamente da Microsoft Store durante la manutenzione notturna; Questo è il metodo consigliato per ottenere gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="58a46-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="58a46-106">Esistono tuttavia alcune situazioni in cui un dispositivo di teams Rooms non può ricevere aggiornamenti da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="58a46-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="58a46-107">Ad esempio, i criteri di sicurezza potrebbero non consentire ai dispositivi di connettersi a Internet o potrebbero non consentire il download delle app da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="58a46-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="58a46-108">In alternativa, potresti voler aggiornare un dispositivo prima di eseguire la configurazione, durante il quale Microsoft Store non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="58a46-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="58a46-109">Se non si riesce ad ottenere gli aggiornamenti da Microsoft Store, è possibile usare uno script di PowerShell per l'aggiornamento delle app offline per aggiornare manualmente i dispositivi delle sale di Teams a una versione più recente dell'app teams rooms.</span><span class="sxs-lookup"><span data-stu-id="58a46-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="58a46-110">Seguire i passaggi di questo articolo per aggiornare manualmente i dispositivi di teams rooms.</span><span class="sxs-lookup"><span data-stu-id="58a46-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="58a46-111">Questo processo può aggiornare solo un dispositivo di teams Rooms con l'app teams rooms già installata.</span><span class="sxs-lookup"><span data-stu-id="58a46-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="58a46-112">Non può essere usata per eseguire una nuova installazione.</span><span class="sxs-lookup"><span data-stu-id="58a46-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="58a46-113">Inoltre, non può essere usato per declassare l'app a una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="58a46-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="58a46-114">Per eseguire una nuova installazione dell'app teams rooms, contattare il produttore del dispositivo per elementi multimediali specifici o vedere [preparare il supporto di installazione](console.md#prepare-the-installation-media).</span><span class="sxs-lookup"><span data-stu-id="58a46-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="58a46-115">Passaggio 1: scaricare lo script di aggiornamento dell'app offline</span><span class="sxs-lookup"><span data-stu-id="58a46-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="58a46-116">Prima di tutto, Scarica la versione più recente dello script di aggiornamento dell'app offline.</span><span class="sxs-lookup"><span data-stu-id="58a46-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="58a46-117">Per scaricare lo script, fare clic su <https://go.microsoft.com/fwlink/?linkid=2151817> .</span><span class="sxs-lookup"><span data-stu-id="58a46-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="58a46-118">Lo script verrà scaricato nella cartella download predefinita del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="58a46-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="58a46-119">I file scaricati possono essere contrassegnati come bloccati da Windows.</span><span class="sxs-lookup"><span data-stu-id="58a46-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="58a46-120">Se è necessario eseguire lo script senza alcuna interazione, è necessario sbloccare lo script.</span><span class="sxs-lookup"><span data-stu-id="58a46-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="58a46-121">Per sbloccare lo script, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="58a46-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="58a46-122">Fare clic con il pulsante destro del mouse sul file in Esplora file</span><span class="sxs-lookup"><span data-stu-id="58a46-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="58a46-123">Fare clic su **Proprietà**</span><span class="sxs-lookup"><span data-stu-id="58a46-123">Click **Properties**</span></span>
3. <span data-ttu-id="58a46-124">Selezionare **Sblocca**</span><span class="sxs-lookup"><span data-stu-id="58a46-124">Select **Unblock**</span></span>
4. <span data-ttu-id="58a46-125">Fare clic su **OK**</span><span class="sxs-lookup"><span data-stu-id="58a46-125">Click **OK**</span></span>

<span data-ttu-id="58a46-126">Per sbloccare lo script usando PowerShell, vedere [sbloccare file](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span><span class="sxs-lookup"><span data-stu-id="58a46-126">To unblock the script using PowerShell, see [Unblock-File](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="58a46-127">Dopo il download dello script di aggiornamento dell'app offline, trasferire il file nel dispositivo teams rooms.</span><span class="sxs-lookup"><span data-stu-id="58a46-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="58a46-128">È possibile trasferire un file nel dispositivo usando un'unità USB o accedendo al file da una condivisione file di rete mentre si è in modalità amministratore nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="58a46-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="58a46-129">Assicurarsi di notare dove salvare il file nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="58a46-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="58a46-130">Passaggio 2: eseguire lo script per aggiornare l'app teams rooms</span><span class="sxs-lookup"><span data-stu-id="58a46-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="58a46-131">Lo script di aggiornamento dell'app offline deve essere eseguito da un prompt dei comandi con privilegi elevati mentre l'utente Skype (l'utente in cui viene eseguita l'app) è ancora connesso.</span><span class="sxs-lookup"><span data-stu-id="58a46-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="58a46-132">Per altre informazioni su come accedere a un account di amministratore per usare il prompt dei comandi con privilegi elevati mentre l'utente Skype è ancora connesso, vedere [passare alla modalità amministratore e viceversa quando l'app Microsoft teams Rooms è in esecuzione](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span><span class="sxs-lookup"><span data-stu-id="58a46-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="58a46-133">Per eseguire lo script da un prompt dei comandi con privilegi elevati, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="58a46-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="58a46-134">Passare alla modalità amministratore</span><span class="sxs-lookup"><span data-stu-id="58a46-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="58a46-135">Fare clic sull'icona Start, digitare **prompt dei comandi** e quindi scegliere **Esegui come amministratore**</span><span class="sxs-lookup"><span data-stu-id="58a46-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="58a46-136">Eseguire il comando seguente `<path to script>` , dove include il percorso completo dello script e il nome del file di script:</span><span class="sxs-lookup"><span data-stu-id="58a46-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="58a46-137">Ad esempio, se il file di script si trova `C:\Users\Admin\Downloads` e il nome del file di script è `MTR-Update-4.5.6.7.ps1` , eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="58a46-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="58a46-138">Consentire l'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="58a46-138">Allow the script to run.</span></span> <span data-ttu-id="58a46-139">Al termine, lo script riavvia il dispositivo teams rooms.</span><span class="sxs-lookup"><span data-stu-id="58a46-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="58a46-140">Puoi anche eseguire lo script usando Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58a46-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="58a46-141">Per altre informazioni sull'uso di PowerShell remoto con i dispositivi teams rooms, vedere [gestione remota tramite PowerShell](rooms-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="58a46-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="58a46-142">Passaggio 3: verificare che l'app sia stata aggiornata correttamente</span><span class="sxs-lookup"><span data-stu-id="58a46-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="58a46-143">Se lo script viene eseguito correttamente, il dispositivo verrà riavviato nell'app teams rooms.</span><span class="sxs-lookup"><span data-stu-id="58a46-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="58a46-144">Se lo script incontra un problema, indicherà qual è il problema nella riga di comando e ne registra l'output in un file.</span><span class="sxs-lookup"><span data-stu-id="58a46-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="58a46-145">Seguire le istruzioni fornite dallo script.</span><span class="sxs-lookup"><span data-stu-id="58a46-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="58a46-146">Se è necessario contattare il supporto tecnico Microsoft, assicurarsi di includere il file di log insieme alla richiesta di supporto.</span><span class="sxs-lookup"><span data-stu-id="58a46-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="58a46-147">Lo script consentirà di specificare il percorso del file di log.</span><span class="sxs-lookup"><span data-stu-id="58a46-147">The script will provide you with the path to the log file.</span></span>
