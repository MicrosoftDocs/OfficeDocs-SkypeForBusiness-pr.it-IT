---
title: Configurare una console per Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Questo articolo descrive come configurare la console di Microsoft Teams Rooms e le relative periferiche.
ms.openlocfilehash: 4caa2677eea01ecc96e426692b536aec8563c473
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117574"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="1bdf7-103">Configurare una console per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="1bdf7-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="1bdf7-104">Questo articolo descrive come configurare la console di Microsoft Teams Rooms e le relative periferiche.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="1bdf7-105">È consigliabile eseguire questa procedura solo se gli account necessari di Microsoft Teams o Skype for Business ed Exchange sono già stati creati e testati come descritto in Distribuire le chat room [di Microsoft Teams.](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="1bdf7-106">Sono necessari l'hardware e il software descritti nei [requisiti di Microsoft Teams Rooms.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="1bdf7-107">Questo argomento contiene le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bdf7-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="1bdf7-108">Preparare il supporto di installazione</span><span class="sxs-lookup"><span data-stu-id="1bdf7-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="1bdf7-109">Installare un certificato CA privato nella console</span><span class="sxs-lookup"><span data-stu-id="1bdf7-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="1bdf7-110">Installare Windows 10 e l'app console Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="1bdf7-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="1bdf7-111">Configurazione iniziale della console</span><span class="sxs-lookup"><span data-stu-id="1bdf7-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="1bdf7-112">Elenco di controllo per la distribuzione di Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="1bdf7-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="1bdf7-113">Le chat room di Microsoft Teams funzionano solo in un ambiente Microsoft Teams o Skype for Business correttamente configurato in cui gli account del dispositivo sono configurati correttamente, come descritto in [Distribuire le sale di Microsoft Teams.](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="1bdf7-114">Preparare il supporto di installazione</span><span class="sxs-lookup"><span data-stu-id="1bdf7-114">Prepare the installation media</span></span>
<span data-ttu-id="1bdf7-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="1bdf7-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="1bdf7-116">L'installazione dell'app console Microsoft Teams Rooms richiede un dispositivo di archiviazione USB con almeno 32 GB di capacità.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="1bdf7-117">Nel dispositivo non dovrebbero essere presenti altri file. i file esistenti sullo spazio di archiviazione USB andranno persi.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1bdf7-118">Se non si crea il supporto di installazione di Microsoft Teams Rooms in base a queste istruzioni, è probabile che si crei un comportamento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="1bdf7-119">Il processo seguente è per la creazione di supporti di installazione per l'immagine di nuovi dispositivi Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="1bdf7-120">I dispositivi esistenti, per impostazione predefinita, vengono aggiornati automaticamente da Windows Update e Windows Store.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bdf7-121">Il computer Windows 10 usato per creare il supporto di installazione di Microsoft Teams Rooms deve essere nella stessa versione o versione successiva di Windows del supporto di installazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="1bdf7-122">Scaricare lo [scriptCreateSrsMedia.ps1 .](https://go.microsoft.com/fwlink/?linkid=867842)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="1bdf7-123">Eseguire lo script CreateSrsMedia.ps1 da un prompt con privilegi elevati in un computer Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="1bdf7-124">Seguire le istruzioni dello script per creare un disco di configurazione USB di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="1bdf7-125">Ogni volta che lo script CreateSrsMedia.ps1, l'output dello schermo includerà il nome di un file di log o di una trascrizione per la sessione.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="1bdf7-126">In caso di problemi con l'esecuzione dello script, assicurarsi di avere una copia della trascrizione disponibile quando si richiede il supporto.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="1bdf7-127">Lo script CreateSrsMedia.ps1 automatizza le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bdf7-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="1bdf7-128">Scaricare il programma di installazione MSI più recente per Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="1bdf7-129">Determinare la build di Windows che l'utente deve fornire.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="1bdf7-130">Le versioni rilasciate più di recente possono essere testate e supportate per l'uso con i dispositivi Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="1bdf7-131">Scaricare i componenti di supporto necessari.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="1bdf7-132">Assemblare i componenti necessari sul supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="1bdf7-133">È necessaria una versione specifica di Windows 10 e questa versione è disponibile solo per i clienti con contratto multilicenza.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="1bdf7-134">È possibile ottenere una copia dal [Centro servizi per contratti multilicenza.](https://www.microsoft.com/Licensing/servicecenter/)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="1bdf7-135">Al termine, rimuovere il disco USB dal computer e passare a [Installare Windows 10 e l'app console Microsoft Teams Rooms.](console.md#Reimage)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="1bdf7-136">Installare Windows 10 e l'app console Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="1bdf7-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="1bdf7-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="1bdf7-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="1bdf7-138">A questo punto è necessario applicare il supporto di configurazione creato.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="1bdf7-139">Il dispositivo di destinazione verrà eseguito come appliance e l'utente predefinito verrà impostato in modo da eseguire solo l'app console Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="1bdf7-140">Se il dispositivo di destinazione verrà installato in un dock (ad esempio un Surface Pro), scollegarlo dal dock.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="1bdf7-141">Verificare che il dispositivo di destinazione non sia connesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="1bdf7-142">Verificare che il dispositivo di destinazione sia connesso all'alimentazione CA.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="1bdf7-143">Collegare il disco di configurazione USB al dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="1bdf7-144">Eseguire l'avvio sul disco di configurazione USB.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="1bdf7-145">Fare riferimento alle istruzioni del produttore.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="1bdf7-146">Se il dispositivo di destinazione è un Surface Pro, eseguire la procedura seguente per eseguire l'avvio nel disco di configurazione USB:</span><span class="sxs-lookup"><span data-stu-id="1bdf7-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="1bdf7-147">a.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-147">a.</span></span> <span data-ttu-id="1bdf7-148">Premere e continuare a tenere premuto il pulsante del volume (-).</span><span class="sxs-lookup"><span data-stu-id="1bdf7-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="1bdf7-149">b.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-149">b.</span></span> <span data-ttu-id="1bdf7-150">Premere e rilasciare il pulsante di alimentazione.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-150">Press and release the power button.</span></span>

    <span data-ttu-id="1bdf7-151">c.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-151">c.</span></span> <span data-ttu-id="1bdf7-152">Dopo l'avvio dell'installazione di Windows, rilasciare il pulsante del volume verso il basso (-).</span><span class="sxs-lookup"><span data-stu-id="1bdf7-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="1bdf7-153">Il sistema verrà arrestato al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="1bdf7-154">Dopo l'arresto del sistema, è possibile rimuovere il disco di configurazione USB.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="1bdf7-155">A questo punto, è possibile posizionare il dispositivo di destinazione nel dock (se si usa un prodotto basato su dock), collegare le periferiche necessarie per la sala riunioni e connettersi alla rete.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="1bdf7-156">Fare riferimento alle istruzioni del produttore.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="1bdf7-157">Gli aggiornamenti software per Microsoft Teams Rooms vengono scaricati automaticamente da Microsoft Store per le aziende.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="1bdf7-158">Vedere [Prerequisiti per Microsoft Store per le aziende](/microsoft-store/prerequisites-microsoft-store-for-business) e l'istruzione per verificare che la console della sala sia in grado di accedere al negozio e di eseguire l'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-158">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="1bdf7-159">Selezione di una lingua</span><span class="sxs-lookup"><span data-stu-id="1bdf7-159">Selecting a language</span></span> 

<span data-ttu-id="1bdf7-160">In Creator's Update, è necessario usare lo script ApplyCurrentRegionAndLanguage.ps1 in scenari in cui la selezione implicita della lingua non fornisce all'utente la lingua effettiva dell'applicazione desiderata(ad esempio, vuole che l'app console sia disponibile in francese, ma sarà disponibile in inglese).</span><span class="sxs-lookup"><span data-stu-id="1bdf7-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1bdf7-161">Le istruzioni seguenti funzionano solo per le console create con Windows Creator's Update.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="1bdf7-162">I sistemi legacy/in-market che non sono stati impostati usando i supporti multimediali con il nuovo sistema di provisioning non potranno usare queste istruzioni, ma non dovranno risentire del problema iniziale che richiede questo intervento manuale (Anniversary Edition consente di scegliere esplicitamente la lingua dell'app nell'ambito della configurazione).</span><span class="sxs-lookup"><span data-stu-id="1bdf7-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="1bdf7-163">Per applicare la lingua desiderata</span><span class="sxs-lookup"><span data-stu-id="1bdf7-163">To apply your desired language</span></span>

1. <span data-ttu-id="1bdf7-164">Passare alla modalità di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="1bdf7-165">Selezionare il menu Start.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="1bdf7-166">Seleziona l'icona a forma di ingranaggio per avviare **l'app** Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="1bdf7-167">Selezionare **Lingua &amp; ora**.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="1bdf7-168">Selezionare **Lingua &amp; area geografica.**</span><span class="sxs-lookup"><span data-stu-id="1bdf7-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="1bdf7-169">Selezionare **Aggiungi una lingua.**</span><span class="sxs-lookup"><span data-stu-id="1bdf7-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="1bdf7-170">Selezionare la lingua da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="1bdf7-171">Selezionare la lingua appena aggiunta all'elenco "Lingue".</span><span class="sxs-lookup"><span data-stu-id="1bdf7-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="1bdf7-172">Selezionare **Imposta come predefinito.**</span><span class="sxs-lookup"><span data-stu-id="1bdf7-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="1bdf7-173">Per le lingue da rimuovere:</span><span class="sxs-lookup"><span data-stu-id="1bdf7-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="1bdf7-174">a.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-174">a.</span></span> <span data-ttu-id="1bdf7-175">Selezionare la lingua da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-175">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="1bdf7-176">b.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-176">b.</span></span> <span data-ttu-id="1bdf7-177">Selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-177">Select **Remove**.</span></span>
    
11. <span data-ttu-id="1bdf7-178">Avviare un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="1bdf7-179">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1bdf7-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="1bdf7-180">Riavviare il sistema.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-180">Restart the system.</span></span>
    
<span data-ttu-id="1bdf7-181">La lingua desiderata viene ora applicata alla console di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="1bdf7-182">Configurazione iniziale della console</span><span class="sxs-lookup"><span data-stu-id="1bdf7-182">Initial set up of the console</span></span>
<span data-ttu-id="1bdf7-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="1bdf7-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="1bdf7-184">Dopo l'installazione di Windows, l'app console Microsoft Teams Rooms verrà avviata nel processo di configurazione iniziale all'avvio successivo o se è stata scelta l'opzione /reboot.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="1bdf7-185">Viene visualizzata la schermata Account utente.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-185">The User Account screen appears.</span></span> <span data-ttu-id="1bdf7-186">Immetti l'indirizzo di accesso Skype (in user@domain) dell'account della chat room da usare con la console.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="1bdf7-187">Immettere la password per l'account della chat room e immetterla di nuovo per verificarla.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="1bdf7-188">In "Configura dominio", impostare l'FQDN per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="1bdf7-189">Se il dominio SIP di Skype for Business è diverso dal dominio di Exchange dell'utente, immettere il dominio di Exchange in questo campo.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="1bdf7-190">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="1bdf7-191">Selezionare i dispositivi indicati nella schermata Caratteristiche e fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="1bdf7-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="1bdf7-192">Per impostazione predefinita, la condivisione automatica dello schermo è impostata su Su e Nascondi nomi riunione su Disattivato.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="1bdf7-193">I dispositivi da selezionare sono:</span><span class="sxs-lookup"><span data-stu-id="1bdf7-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="1bdf7-194">Microfono per conferenze: il microfono predefinito per questa sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="1bdf7-195">Altoparlante per conferenza: l'altoparlante predefinito per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="1bdf7-196">Altoparlante predefinito: l'altoparlante usato per l'audio dall'ingestione HDMI.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="1bdf7-197">Ogni elemento ha un menu a discesa di opzioni tra cui selezionare.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-197">Each item has a drop-down menu of options to select from.</span></span> <span data-ttu-id="1bdf7-198">È necessario effettuare una selezione per ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-198">You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="1bdf7-199">Fare clic **su Fine.**</span><span class="sxs-lookup"><span data-stu-id="1bdf7-199">Click **Finish**.</span></span>
    
<span data-ttu-id="1bdf7-200">L'app console Microsoft Teams Rooms dovrebbe iniziare immediatamente ad accedere a Skype for Business Server con le credenziali immesse sopra e dovrebbe anche iniziare a sincronizzare il calendario con Exchange usando le stesse credenziali.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="1bdf7-201">Per informazioni dettagliate sull'uso dell'app console, vedere la Guida di [Microsoft Teams Rooms.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1bdf7-202">Microsoft Teams Rooms si basa sulla presenza di hardware della console certificato.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="1bdf7-203">Anche un'immagine creata correttamente contenente l'app console Microsoft Teams Rooms non verrà avviato oltre la procedura di configurazione iniziale, a meno che non venga rilevato l'hardware della console.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="1bdf7-204">Per le soluzioni basate su Surface Pro, Surface Pro deve essere connesso all'hardware del dock di accompagnamento per superare questo controllo.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1bdf7-205">Alcuni utenti di lingue non inglesi potrebbero aver bisogno di una tastiera fisica connessa alla console durante la configurazione iniziale nel caso in cui i simboli non siano supportati sulla tastiera virtuale.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="1bdf7-206">Installare un certificato CA privato nella console</span><span class="sxs-lookup"><span data-stu-id="1bdf7-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="1bdf7-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="1bdf7-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="1bdf7-208">La console di Microsoft Teams Rooms deve considerare attendibili i certificati usati dai server a cui si connette.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="1bdf7-209">Per O365 questa operazione viene eseguita automaticamente, poiché questi server usano autorità di certificazione pubbliche, che vengono automaticamente considerati attendibili da Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="1bdf7-210">In un caso in cui l'Autorità di certificazione sia privata, ad esempio una distribuzione locale con Active Directory e l'Autorità di certificazione di Windows, è possibile aggiungere il certificato alla console di Microsoft Teams Rooms in un paio di modi:</span><span class="sxs-lookup"><span data-stu-id="1bdf7-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="1bdf7-211">È possibile aggiungere la console ad Active Directory e aggiungere automaticamente i certificati necessari in base alla pubblicazione dell'Autorità di certificazione in Active Directory (opzione di distribuzione normale).</span><span class="sxs-lookup"><span data-stu-id="1bdf7-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="1bdf7-212">È possibile installare il certificato manualmente dopo il processo di creazione di immagini.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="1bdf7-213">Prima di eseguire questa operazione, è necessario [completare la configurazione iniziale della console.](console.md#Initial)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="1bdf7-214">Per installare manualmente il certificato</span><span class="sxs-lookup"><span data-stu-id="1bdf7-214">To manually install the certificate</span></span>

1. <span data-ttu-id="1bdf7-215">Scaricare il certificato CA nel computer e salvarlo in "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="1bdf7-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="1bdf7-216">Posizionare la console in modalità di amministrazione (vedere [Modalità di amministrazione e gestione dei dispositivi).](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="1bdf7-217">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1bdf7-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="1bdf7-218">Aggiunta a un dominio di Active Directory (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="1bdf7-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="1bdf7-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="1bdf7-220">È possibile aggiungere le console di Microsoft Teams Rooms al dominio.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="1bdf7-221">Le console di Microsoft Teams Rooms devono essere collocate in un'unità organizzativa separata dalle workstation del PC, perché molti criteri per le workstation non sono compatibili con Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="1bdf7-222">Un esempio comune sono i criteri di applicazione delle password che impediscono l'avvio automatico di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="1bdf7-223">Per informazioni sulla gestione delle impostazioni dell'oggetto Criteri di gruppo, vedere [Gestire le chat room di Microsoft Teams.](rooms-operations.md)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="1bdf7-224">Per aggiungere le chat room di Microsoft Teams a un dominio</span><span class="sxs-lookup"><span data-stu-id="1bdf7-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="1bdf7-225">Accedere alla console dall'account di amministratore (vedere [Modalità di amministrazione e gestione dei dispositivi).](rooms-operations.md#AdminMode)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="1bdf7-226">Avviare il prompt dei comandi di Powershell con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="1bdf7-227">Immettere il comando seguente in Powershell:</span><span class="sxs-lookup"><span data-stu-id="1bdf7-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="1bdf7-228">Ad esempio, se il dominio completo è redmond.corp.microsoft.com e si vuole che le console di Microsoft Teams Rooms siano in un'unità organizzativa "Microsoft Teams Rooms" figlio di un'unità organizzativa "Risorse", il comando sarà:</span><span class="sxs-lookup"><span data-stu-id="1bdf7-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="1bdf7-229">Se si vuole rinominare il computer quando lo si unisce a un dominio, usare il flag -NewName seguito dal nuovo nome del computer.</span><span class="sxs-lookup"><span data-stu-id="1bdf7-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="1bdf7-230">Elenco di controllo per la distribuzione di Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="1bdf7-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="1bdf7-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="1bdf7-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="1bdf7-232">Usare l'elenco di controllo seguente durante una verifica finale che la console e tutte le relative periferiche siano completamente configurate:</span><span class="sxs-lookup"><span data-stu-id="1bdf7-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="1bdf7-233">**Impostazioni dell'applicazione**</span><span class="sxs-lookup"><span data-stu-id="1bdf7-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1bdf7-234">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-234">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-235">Il nome dell'account della sala e il numero di telefono (se PSTN abilitato) vengono visualizzati correttamente nell'angolo in alto a destra dello schermo della console</span><span class="sxs-lookup"><span data-stu-id="1bdf7-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="1bdf7-236">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-236">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-237">Il nome del computer Windows è impostato correttamente (utile per l'amministrazione remota)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="1bdf7-238">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-238">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-239">Password dell'account amministratore impostata e verificata</span><span class="sxs-lookup"><span data-stu-id="1bdf7-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="1bdf7-240">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-240">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-241">Tutti gli aggiornamenti del firmware sono stati applicati</span><span class="sxs-lookup"><span data-stu-id="1bdf7-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="1bdf7-242">**Periferiche audio/video**</span><span class="sxs-lookup"><span data-stu-id="1bdf7-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1bdf7-243">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-243">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-244">La versione del firmware delle periferiche della fotocamera è corretta (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="1bdf7-245">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-245">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-246">Fotocamera funzionale e posizionata in modo ottimale</span><span class="sxs-lookup"><span data-stu-id="1bdf7-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="1bdf7-247">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-247">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-248">Impostazioni per Dispositivo di riproduzione predefinito e Dispositivo di comunicazione predefinito riproduzione impostato sulla periferica audio prevista</span><span class="sxs-lookup"><span data-stu-id="1bdf7-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="1bdf7-249">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-249">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-250">Impostazioni per registrazione dispositivo di comunicazione predefinito impostato sulla periferica audio prevista</span><span class="sxs-lookup"><span data-stu-id="1bdf7-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="1bdf7-251">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-251">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-252">La versione del firmware delle periferiche audio è corretta (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="1bdf7-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="1bdf7-253">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-253">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-254">Dispositivo di input audio funzionale e posizionato in modo ottimale</span><span class="sxs-lookup"><span data-stu-id="1bdf7-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="1bdf7-255">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-255">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-256">Dispositivo di output audio funzionante e posizionato in modo ottimale</span><span class="sxs-lookup"><span data-stu-id="1bdf7-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="1bdf7-257">**Dock**</span><span class="sxs-lookup"><span data-stu-id="1bdf7-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1bdf7-258">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-258">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-259">I cavi sono sicuri e non pizzicati</span><span class="sxs-lookup"><span data-stu-id="1bdf7-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="1bdf7-260">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-260">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-261">L'inserimento audio tramite HDMI è funzionale</span><span class="sxs-lookup"><span data-stu-id="1bdf7-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="1bdf7-262">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-262">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-263">L'inserimento di video su HDMI è funzionale</span><span class="sxs-lookup"><span data-stu-id="1bdf7-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="1bdf7-264">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-264">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-265">Il Dock può ruotare liberamente</span><span class="sxs-lookup"><span data-stu-id="1bdf7-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="1bdf7-266">☐</span><span class="sxs-lookup"><span data-stu-id="1bdf7-266">☐</span></span>  <br/> |<span data-ttu-id="1bdf7-267">La luminosità dello schermo è accettabile per l'ambiente</span><span class="sxs-lookup"><span data-stu-id="1bdf7-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1bdf7-268">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bdf7-268">See also</span></span>
<span data-ttu-id="1bdf7-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="1bdf7-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="1bdf7-270">Piano per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="1bdf7-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="1bdf7-271">Distribuire Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="1bdf7-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="1bdf7-272">Configurare una console per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="1bdf7-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
<span data-ttu-id="1bdf7-273">[Gestire Microsoft Teams Rooms](rooms-manage.md).</span><span class="sxs-lookup"><span data-stu-id="1bdf7-273">[Manage Microsoft Teams Rooms](rooms-manage.md)</span></span>