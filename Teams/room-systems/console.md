---
title: Configurare una console Microsoft teams rooms
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Questo articolo descrive come configurare la console Microsoft teams Rooms e le sue periferiche.
ms.openlocfilehash: 1bb1e45eca95628222b799d94c953bb49da1ea17
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243477"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="c9e2a-103">Configurare una console Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="c9e2a-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="c9e2a-104">Questo articolo descrive come configurare la console Microsoft teams Rooms e le sue periferiche.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="c9e2a-105">È consigliabile eseguire questa procedura solo se gli account Microsoft teams o Skype for business e Exchange necessari sono già stati creati e testati come descritto in [distribuire le sale di Microsoft teams](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="c9e2a-106">Sarà necessario l'hardware e il software descritti nei [requisiti di Microsoft teams Rooms](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="c9e2a-107">Questo argomento contiene le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9e2a-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="c9e2a-108">Preparare il supporto di installazione</span><span class="sxs-lookup"><span data-stu-id="c9e2a-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="c9e2a-109">Installare un certificato CA privato nella console</span><span class="sxs-lookup"><span data-stu-id="c9e2a-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="c9e2a-110">Installare Windows 10 e l'app console Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="c9e2a-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="c9e2a-111">Configurazione iniziale della console</span><span class="sxs-lookup"><span data-stu-id="c9e2a-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="c9e2a-112">Elenco di controllo della distribuzione di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="c9e2a-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="c9e2a-113">Le sale di Microsoft teams funzionano solo in un ambiente Microsoft teams o Skype for business correttamente configurato in cui gli account di dispositivo sono configurati correttamente, come descritto in [distribuire le sale di Microsoft teams](room-systems-v2.md).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="c9e2a-114">Preparare il supporto di installazione</span><span class="sxs-lookup"><span data-stu-id="c9e2a-114">Prepare the installation media</span></span>
<span data-ttu-id="c9e2a-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="c9e2a-115"></span></span>

<span data-ttu-id="c9e2a-116">L'installazione dell'app console Microsoft teams Rooms richiede un dispositivo di archiviazione USB con almeno 32GB di capacità.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="c9e2a-117">Non devono essere presenti altri file nel dispositivo; tutti i file esistenti nello spazio di archiviazione USB andranno perduti.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9e2a-118">L'errore di creare il supporto di installazione di Microsoft teams rooms in base a queste istruzioni probabilmente comporterà un comportamento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="c9e2a-119">Il processo seguente è per la creazione di elementi multimediali di installazione in nuovi dispositivi Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="c9e2a-120">I dispositivi esistenti, per impostazione predefinita, vengono aggiornati automaticamente da Windows Update e Windows Store.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="c9e2a-121">Scaricare lo [script CreateSrsMedia. ps1](https://go.microsoft.com/fwlink/?linkid=867842).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="c9e2a-122">Eseguire lo script CreateSrsMedia. ps1 da una richiesta elevata in un computer con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="c9e2a-123">Seguire le istruzioni dello script per creare un disco di configurazione USB di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="c9e2a-124">Ogni volta che lo script CreateSrsMedia. ps1 viene avviato, l'output dello schermo includerà il nome di un file di log o una trascrizione per la sessione.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-124">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="c9e2a-125">In caso di problemi con l'esecuzione dello script, assicurarsi di avere una copia della trascrizione disponibile quando si richiede il supporto.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-125">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="c9e2a-126">Lo script CreateSrsMedia. ps1 automatizza le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9e2a-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="c9e2a-127">Scaricare il programma di installazione MSI più recente per le sale di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="c9e2a-128">Determinare la build di Windows che l'utente deve fornire.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="c9e2a-129">Le versioni rilasciate più di recente possono essere testate e supportate per l'uso con i dispositivi Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="c9e2a-130">Scaricare i componenti di supporto necessari.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="c9e2a-131">Assemblare i componenti necessari nel supporto di installazione.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="c9e2a-132">È necessaria una versione specifica di Windows 10 e questa versione è disponibile solo per i clienti con contratti multilicenza.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="c9e2a-133">È possibile ottenere una copia dal [centro servizi per contratti multilicenza](https://www.microsoft.com/Licensing/servicecenter/).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="c9e2a-134">Al termine, rimuovere il disco USB dal computer e procedere con [l'installazione di Windows 10 e dell'app console Microsoft teams Rooms](console.md#Reimage).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="c9e2a-135">Installare Windows 10 e l'app console Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="c9e2a-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="c9e2a-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="c9e2a-136"></span></span>

<span data-ttu-id="c9e2a-137">È ora necessario applicare il supporto di configurazione creato.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="c9e2a-138">Il dispositivo di destinazione verrà eseguito come appliance e l'utente predefinito sarà impostato per eseguire solo l'app console Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="c9e2a-139">Se il dispositivo di destinazione verrà installato in un dock (ad esempio, una superficie Pro), scollegarlo dal Dock.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="c9e2a-140">Verificare che il dispositivo di destinazione non sia connesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="c9e2a-141">Verificare che il dispositivo di destinazione sia collegato all'alimentazione CA.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="c9e2a-142">Collegare il disco di configurazione USB al dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="c9e2a-143">Avviare il disco di configurazione USB.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="c9e2a-144">Fare riferimento alle istruzioni del produttore.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="c9e2a-145">Se il dispositivo di destinazione è una superficie Pro, usare la procedura seguente per avviare il disco di configurazione USB:</span><span class="sxs-lookup"><span data-stu-id="c9e2a-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="c9e2a-146">un.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-146">a.</span></span> <span data-ttu-id="c9e2a-147">Premere e continuare a tenere premuto il pulsante volume giù (-).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="c9e2a-148">b.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-148">b.</span></span> <span data-ttu-id="c9e2a-149">Premere e rilasciare il pulsante di accensione.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-149">Press and release the power button.</span></span>

    <span data-ttu-id="c9e2a-150">c.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-150">c.</span></span> <span data-ttu-id="c9e2a-151">Dopo l'avvio della configurazione di Windows, rilasciare il pulsante volume giù (-).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="c9e2a-152">Il sistema si arresta dopo il completamento dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="c9e2a-153">Dopo che il sistema è stato arrestato, è sicuro rimuovere il disco di configurazione USB.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="c9e2a-154">A questo punto, è possibile posizionare il dispositivo di destinazione nel Dock (se si usa un prodotto basato su Dock), allegare le periferiche necessarie per la sala riunioni e connettersi alla rete.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="c9e2a-155">Fare riferimento alle istruzioni del produttore.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-155">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="c9e2a-156">Selezione di una lingua</span><span class="sxs-lookup"><span data-stu-id="c9e2a-156">Selecting a language</span></span> 

<span data-ttu-id="c9e2a-157">Nell'aggiornamento di Creator è necessario usare lo script ApplyCurrentRegionAndLanguage. ps1 in scenari in cui la selezione della lingua implicita non offre all'utente la lingua effettiva dell'applicazione desiderata (ad esempio, vogliono che l'app console venga aggiornata in francese, ma è in arrivo in inglese).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-157">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9e2a-158">Le istruzioni seguenti funzionano solo per le console create con l'aggiornamento di Windows Creator.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-158">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="c9e2a-159">I sistemi legacy/in-Market che non sono stati configurati con il nuovo sistema di provisioning non saranno in grado di usare queste istruzioni, ma dovrebbero anche non risentire del problema iniziale che richiede questo intervento manuale (anniversario Edition consente di selezionare il lingua dell'app in modo esplicito come parte del programma di installazione).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-159">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="c9e2a-160">Per applicare la lingua desiderata</span><span class="sxs-lookup"><span data-stu-id="c9e2a-160">To apply your desired language</span></span>

1. <span data-ttu-id="c9e2a-161">Passare alla modalità amministratore.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-161">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="c9e2a-162">Selezionare il menu Start.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-162">Select the Start menu.</span></span>
    
3. <span data-ttu-id="c9e2a-163">Selezionare l'icona dell'ingranaggio per avviare l'app **Impostazioni** .</span><span class="sxs-lookup"><span data-stu-id="c9e2a-163">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="c9e2a-164">Selezionare **lingua &amp; temporale**.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-164">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="c9e2a-165">Selezionare **lingua &amp; dell'area geografica**.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-165">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="c9e2a-166">Selezionare **Aggiungi una lingua**.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-166">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="c9e2a-167">Selezionare la lingua che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-167">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="c9e2a-168">Selezionare la lingua appena aggiunta all'elenco "lingue".</span><span class="sxs-lookup"><span data-stu-id="c9e2a-168">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="c9e2a-169">Selezionare **Imposta come predefinito**.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-169">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="c9e2a-170">Per tutte le lingue che si desidera rimuovere:</span><span class="sxs-lookup"><span data-stu-id="c9e2a-170">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="c9e2a-171">un.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-171">a.</span></span> <span data-ttu-id="c9e2a-172">Selezionare la lingua che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-172">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="c9e2a-173">b.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-173">b.</span></span> <span data-ttu-id="c9e2a-174">Selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-174">Select **Remove**.</span></span>
    
11. <span data-ttu-id="c9e2a-175">Avviare un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-175">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="c9e2a-176">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c9e2a-176">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="c9e2a-177">Riavviare il sistema.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-177">Restart the system.</span></span>
    
<span data-ttu-id="c9e2a-178">La lingua desiderata viene ora applicata alla console Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-178">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="c9e2a-179">Configurazione iniziale della console</span><span class="sxs-lookup"><span data-stu-id="c9e2a-179">Initial set up of the console</span></span>
<span data-ttu-id="c9e2a-180"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="c9e2a-180"></span></span>

<span data-ttu-id="c9e2a-181">Dopo l'installazione di Windows, l'app console Microsoft teams Rooms verrà inserita nel processo di configurazione iniziale quando verrà avviata la successiva o se è stata selezionata l'opzione/reboot.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-181">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="c9e2a-182">Viene visualizzata la schermata dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-182">The User Account screen appears.</span></span> <span data-ttu-id="c9e2a-183">Immettere l'indirizzo di accesso Skype (in formato utente @ dominio) dell'account della sala da usare con la console.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-183">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="c9e2a-184">Immettere la password per l'account della sala e immetterla di nuovo per verificarla.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-184">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="c9e2a-185">In "Configura dominio" impostare il nome di dominio completo per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-185">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="c9e2a-186">Se il dominio SIP di Skype for business è diverso dal dominio Exchange dell'utente, immettere il dominio Exchange in questo campo.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-186">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="c9e2a-187">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-187">Click **Next**.</span></span>
    
5. <span data-ttu-id="c9e2a-188">Selezionare i dispositivi indicati nella schermata caratteristiche e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-188">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="c9e2a-189">Il valore predefinito consiste nel fatto che la condivisione dello schermo automatico sia impostata su attivato e nascondere i nomi delle riunioni impostati su disattivato.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-189">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="c9e2a-190">I dispositivi da selezionare sono:</span><span class="sxs-lookup"><span data-stu-id="c9e2a-190">The devices to select are:</span></span>
    
   - <span data-ttu-id="c9e2a-191">Microfono per i servizi di conferenza: il microfono predefinito per questa sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-191">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="c9e2a-192">Altoparlante per i servizi di conferenza: altoparlante predefinito per i servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-192">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="c9e2a-193">Altoparlante predefinito: l'altoparlante usato per l'audio dall'uso di HDMI.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-193">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="c9e2a-194">Ogni elemento ha un menu a discesa di opzioni tra cui scegliere.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-194">Each item has a drop-down menu of options to select from.</span></span> <span data-ttu-id="c9e2a-195">Devi effettuare una selezione per ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-195">You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="c9e2a-196">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-196">Click **Finish**.</span></span>
    
<span data-ttu-id="c9e2a-197">L'app console Microsoft teams Rooms dovrebbe iniziare immediatamente l'accesso a Skype for Business Server con le credenziali immesse sopra e deve anche iniziare a sincronizzare il calendario con Exchange usando le stesse credenziali.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-197">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="c9e2a-198">Per informazioni dettagliate sull'uso dell'app console, vedere la [Guida di Microsoft teams Rooms](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-198">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c9e2a-199">Microsoft teams Rooms si basa sulla presenza di hardware console certificato.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-199">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="c9e2a-200">Anche un'immagine creata correttamente che contiene l'app console Microsoft teams Rooms non verrà avviata oltre la procedura di configurazione iniziale, a meno che non venga rilevato l'hardware della console.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-200">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="c9e2a-201">Per le soluzioni basate su Surface Pro, la superficie Pro deve essere connessa all'hardware Dock associato per superare questo controllo.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-201">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9e2a-202">Alcuni utenti di lingua diversa dall'inglese potrebbero avere bisogno di una tastiera fisica connessa alla console durante la configurazione iniziale, se i simboli non sono supportati nella tastiera virtuale.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-202">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="c9e2a-203">Installare un certificato CA privato nella console</span><span class="sxs-lookup"><span data-stu-id="c9e2a-203">Install a private CA certificate on the console</span></span>
<span data-ttu-id="c9e2a-204"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c9e2a-204"></span></span>

<span data-ttu-id="c9e2a-205">La console Microsoft teams Rooms deve considerare attendibile i certificati usati dai server a cui si connette.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-205">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="c9e2a-206">Per Office 365, questa operazione viene eseguita automaticamente, poiché questi server usano le autorità di certificazione pubbliche e questi vengono automaticamente considerati attendibili da Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-206">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="c9e2a-207">Nel caso in cui l'autorità di certificazione sia privata, ad esempio una distribuzione locale con Active Directory e l'autorità di certificazione di Windows, è possibile aggiungere il certificato alla console Microsoft teams rooms in un paio di modi:</span><span class="sxs-lookup"><span data-stu-id="c9e2a-207">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="c9e2a-208">È possibile accedere alla console in Active Directory e aggiungere automaticamente i certificati necessari, poiché l'autorità di certificazione viene pubblicata in Active Directory (opzione di distribuzione normale).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-208">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="c9e2a-209">È possibile installare manualmente il certificato dopo il processo di imaging.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-209">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="c9e2a-210">Prima di eseguire questa operazione, è necessario completare [la configurazione iniziale della console](console.md#Initial).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-210">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="c9e2a-211">Per installare manualmente il certificato</span><span class="sxs-lookup"><span data-stu-id="c9e2a-211">To manually install the certificate</span></span>

1. <span data-ttu-id="c9e2a-212">Scaricare il certificato CA nel computer e salvarlo in "C:\Skype room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span><span class="sxs-lookup"><span data-stu-id="c9e2a-212">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="c9e2a-213">Posizionare la console in modalità amministratore (vedere [modalità di amministrazione e gestione dei dispositivi](room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-213">Place the console in admin mode (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="c9e2a-214">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c9e2a-214">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="c9e2a-215">Partecipare a un dominio Active Directory (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="c9e2a-215">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="c9e2a-216"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="c9e2a-216"></span></span>

<span data-ttu-id="c9e2a-217">È possibile partecipare alle console di Microsoft teams Rooms al proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-217">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="c9e2a-218">Le console di Microsoft teams Rooms devono essere posizionate in un'unità organizzativa separata dalle workstation PC perché molti criteri di workstation non sono compatibili con le sale di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-218">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="c9e2a-219">Un esempio comune sono i criteri di applicazione delle password che impediscono l'avvio automatico delle sale di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-219">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="c9e2a-220">Per informazioni sulla gestione delle impostazioni degli oggetti Criteri di gruppo, vedere [gestire le sale di Microsoft teams](room-systems-v2-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-220">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="c9e2a-221">Per partecipare a Microsoft teams Rooms a un dominio</span><span class="sxs-lookup"><span data-stu-id="c9e2a-221">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="c9e2a-222">Accedere alla console dall'account di amministrazione (vedere [modalità di amministrazione e gestione dei dispositivi](room-systems-v2-operations.md#AdminMode)).</span><span class="sxs-lookup"><span data-stu-id="c9e2a-222">Sign into the console from the admin account (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="c9e2a-223">Avviare il prompt dei comandi di PowerShell con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-223">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="c9e2a-224">Immettere il comando seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c9e2a-224">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="c9e2a-225">Ad esempio, se il dominio completo è redmond.corp.microsoft.com e si vuole che le console di Microsoft teams Rooms si trovino in un'unità organizzativa "Microsoft teams Rooms" che è un elemento figlio di un'unità organizzativa "Resources", il comando sarà:</span><span class="sxs-lookup"><span data-stu-id="c9e2a-225">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="c9e2a-226">Se si vuole rinominare il computer quando si partecipa a un dominio, usare il contrassegno-NewName seguito dal nuovo nome del computer.</span><span class="sxs-lookup"><span data-stu-id="c9e2a-226">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="c9e2a-227">Elenco di controllo della distribuzione di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="c9e2a-227">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="c9e2a-228"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c9e2a-228"></span></span>

<span data-ttu-id="c9e2a-229">Usare l'elenco di controllo seguente durante una verifica finale che la console e tutte le sue periferiche siano completamente configurate:</span><span class="sxs-lookup"><span data-stu-id="c9e2a-229">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="c9e2a-230">**Impostazioni applicazione**</span><span class="sxs-lookup"><span data-stu-id="c9e2a-230">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c9e2a-231">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-231">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-232">Nome account della sala e telefono # (se PSTN abilitato) vengono visualizzati correttamente nella parte superiore destra della schermata della console</span><span class="sxs-lookup"><span data-stu-id="c9e2a-232">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="c9e2a-233">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-233">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-234">Il nome del computer Windows è impostato correttamente (utile per l'amministrazione remota)</span><span class="sxs-lookup"><span data-stu-id="c9e2a-234">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="c9e2a-235">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-235">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-236">Password dell'account amministratore impostata e verificata</span><span class="sxs-lookup"><span data-stu-id="c9e2a-236">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="c9e2a-237">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-237">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-238">Tutti gli aggiornamenti del firmware sono stati applicati</span><span class="sxs-lookup"><span data-stu-id="c9e2a-238">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="c9e2a-239">**Periferiche audio/video**</span><span class="sxs-lookup"><span data-stu-id="c9e2a-239">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c9e2a-240">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-240">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-241">La versione del firmware della periferica fotocamera è corretta (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="c9e2a-241">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c9e2a-242">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-242">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-243">Fotocamera funzionale e posizionata in modo ottimale</span><span class="sxs-lookup"><span data-stu-id="c9e2a-243">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="c9e2a-244">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-244">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-245">Impostazioni per il dispositivo predefinito per la riproduzione e la riproduzione del dispositivo di comunicazione predefinito impostato su periferica audio desiderata</span><span class="sxs-lookup"><span data-stu-id="c9e2a-245">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c9e2a-246">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-246">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-247">Impostazioni per la registrazione del dispositivo di comunicazione predefinito impostato sulla periferica audio desiderata</span><span class="sxs-lookup"><span data-stu-id="c9e2a-247">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="c9e2a-248">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-248">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-249">La versione del firmware della periferica audio è corretta (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="c9e2a-249">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="c9e2a-250">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-250">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-251">Dispositivo di input audio funzionale e posizionato in modo ottimale</span><span class="sxs-lookup"><span data-stu-id="c9e2a-251">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="c9e2a-252">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-252">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-253">Dispositivo di output audio funzionale e posizionato in modo ottimale</span><span class="sxs-lookup"><span data-stu-id="c9e2a-253">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="c9e2a-254">**Dock**</span><span class="sxs-lookup"><span data-stu-id="c9e2a-254">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c9e2a-255">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-255">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-256">I cavi sono sicuri e non vengono pizzicati</span><span class="sxs-lookup"><span data-stu-id="c9e2a-256">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="c9e2a-257">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-257">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-258">L'acquisizione di audio tramite HDMI è funzionale</span><span class="sxs-lookup"><span data-stu-id="c9e2a-258">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c9e2a-259">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-259">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-260">L'acquisizione di video tramite HDMI è funzionale</span><span class="sxs-lookup"><span data-stu-id="c9e2a-260">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="c9e2a-261">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-261">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-262">Il Dock può ruotare liberamente</span><span class="sxs-lookup"><span data-stu-id="c9e2a-262">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="c9e2a-263">☐</span><span class="sxs-lookup"><span data-stu-id="c9e2a-263">☐</span></span>  <br/> |<span data-ttu-id="c9e2a-264">La luminosità dello schermo è accettabile per l'ambiente</span><span class="sxs-lookup"><span data-stu-id="c9e2a-264">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c9e2a-265">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9e2a-265">See also</span></span>
<span data-ttu-id="c9e2a-266"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="c9e2a-266"></span></span>

[<span data-ttu-id="c9e2a-267">Pianificare le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9e2a-267">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="c9e2a-268">Distribuire le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9e2a-268">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="c9e2a-269">Configurare una console Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="c9e2a-269">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="c9e2a-270">Gestire le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9e2a-270">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
