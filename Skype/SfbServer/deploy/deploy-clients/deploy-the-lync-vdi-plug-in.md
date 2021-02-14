---
title: Distribuire il plug-in VDI di Lync con Skype for Business Server
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: In questo argomento vengono illustrate le procedure di distribuzione per l'uso di Skype for Business durante la connessione a un desktop virtuale remoto.
ms.openlocfilehash: f7ff99045c861c4435675d9e9e86deaedd499c10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805936"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="04da1-103">Distribuire il plug-in VDI di Lync con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="04da1-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="04da1-104">In questo argomento vengono illustrate le procedure di distribuzione per l'uso di Skype for Business durante la connessione a un desktop virtuale remoto.</span><span class="sxs-lookup"><span data-stu-id="04da1-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="04da1-105">Considerazioni sulla pianificazione sono [disponibili in Plan for Skype for Business in VDI environments.](../../plan-your-deployment/clients-and-devices/vdi-environments.md)</span><span class="sxs-lookup"><span data-stu-id="04da1-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="04da1-106">Un ambiente VDI (Virtual Desktop Infrastructure) viene utilizzato in alcune organizzazioni in cui i problemi di sicurezza e conformità sono particolarmente sensibili.</span><span class="sxs-lookup"><span data-stu-id="04da1-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="04da1-107">Gli utenti sono su computer Windows locali e utilizzano client su un desktop virtuale.</span><span class="sxs-lookup"><span data-stu-id="04da1-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="04da1-108">L'uso di Skype for Business in una connessione di questo tipo richiede software aggiuntivo per plug-in VDI.</span><span class="sxs-lookup"><span data-stu-id="04da1-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="04da1-109">Sono disponibili due soluzioni per il componente plug-in VDI, una offerta da Microsoft e una offerta da Citrix.</span><span class="sxs-lookup"><span data-stu-id="04da1-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="04da1-110">Microsoft consiglia di usare la nuova soluzione HDX RealTime Optimization Pack nelle nuove distribuzioni, ma continuerà a supportare il plug-in VDI di Lync originale per il resto del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="04da1-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="04da1-111">Questo argomento fornisce informazioni dettagliate sulla distribuzione del plug-in VDI di Microsoft Lync, supportato solo in Windows 7 e Windows 8 o Windows Server 2008, e supporta solo i client Lync 2013 o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="04da1-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="04da1-112">Non ci sono piani per aggiornare questo plug-in, ma [citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) per Skype for Business verrà aggiornato in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="04da1-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="04da1-113">Preparare l'ambiente per il plug-in VDI di Lync</span><span class="sxs-lookup"><span data-stu-id="04da1-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="04da1-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="04da1-114"><a name="Prepare_vdi"> </a></span></span>

1. <span data-ttu-id="04da1-115">In Skype for Business Server, verificare che EnableMediaRedirection sia impostato su TRUE per tutti gli utenti del plug-in VDI di Lync.</span><span class="sxs-lookup"><span data-stu-id="04da1-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="04da1-116">Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) e al cmdlet [Set-CsClientPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="04da1-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="04da1-117">Nel server del data center, installare il client Skype for Business su tutti i desktop virtuali.</span><span class="sxs-lookup"><span data-stu-id="04da1-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="04da1-118">Nei computer locali installare il plug-in VDI di Lync.</span><span class="sxs-lookup"><span data-stu-id="04da1-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="04da1-119">Gli utenti devono ora connettere un dispositivo come un headset o una webcam al computer locale.</span><span class="sxs-lookup"><span data-stu-id="04da1-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="04da1-120">Configurare le impostazioni di Connessione Desktop remoto</span><span class="sxs-lookup"><span data-stu-id="04da1-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="04da1-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="04da1-121"><a name="Prepare_vdi"> </a></span></span>

<span data-ttu-id="04da1-122">Per preparare Connessione Desktop remoto per il plug-in VDI di Lync, eseguire la procedura seguente nel computer locale:</span><span class="sxs-lookup"><span data-stu-id="04da1-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="04da1-123">Se il computer locale esegue Windows 8, ignora questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="04da1-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="04da1-124">Se nel computer locale è in esecuzione Windows 7 con SP1, installare l'ultima versione di Windows 8 del [client Servizi Desktop remoto.](https://go.microsoft.com/fwlink/p/?LinkId=268032)</span><span class="sxs-lookup"><span data-stu-id="04da1-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="04da1-125">Avviare il client Servizi Desktop remoto facendo clic sul **pulsante Start** e quindi scegliendo Connessione **Desktop remoto.**</span><span class="sxs-lookup"><span data-stu-id="04da1-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="04da1-126">Fare clic su **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="04da1-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="04da1-127">Fare clic **sulla scheda Risorse** locali. In **Audio remoto** fare clic su **Impostazioni** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="04da1-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="04da1-128">In **Riproduzione audio remota** selezionare **Riproduci nel computer.**</span><span class="sxs-lookup"><span data-stu-id="04da1-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="04da1-129">In **Registrazione audio remota** selezionare Non **registrare.**</span><span class="sxs-lookup"><span data-stu-id="04da1-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="04da1-130">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="04da1-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="04da1-131">Fare clic **sulla scheda** Esperienza. In **Prestazioni** deselezionare la **casella di controllo Cache bitmap** persistente.</span><span class="sxs-lookup"><span data-stu-id="04da1-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="04da1-132">Fare clic **sulla scheda** Generale. In **Computer** digitare il nome del desktop virtuale e quindi fare clic su **Connetti.**</span><span class="sxs-lookup"><span data-stu-id="04da1-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="04da1-133">Accedere e usare Skype for Business sul desktop virtuale</span><span class="sxs-lookup"><span data-stu-id="04da1-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="04da1-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="04da1-134"><a name="SfB_signin"> </a></span></span>

<span data-ttu-id="04da1-135">Dopo aver abilitato il plug-in VDI di Lync, l'utente segue questi passaggi quando accede a Skype for Business sul desktop virtuale.</span><span class="sxs-lookup"><span data-stu-id="04da1-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="04da1-136">L'utente specifica le proprie credenziali nel client Skype for Business in esecuzione sul desktop virtuale.</span><span class="sxs-lookup"><span data-stu-id="04da1-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="04da1-137">Dopo che Skype for Business rileva il plug-in VDI di Lync, Skype for Business richiede all'utente di immettere nuovamente le credenziali.</span><span class="sxs-lookup"><span data-stu-id="04da1-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="04da1-138">In questa finestra di dialogo è consigliabile che l'utente selezioni la casella di controllo **Salva la password** in modo che non venga richiesta di nuovo l'immissione delle credenziali per gli accessi successivi.</span><span class="sxs-lookup"><span data-stu-id="04da1-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="04da1-139">Skype for Business inizia l'associazione con il plug-in VDI di Lync.</span><span class="sxs-lookup"><span data-stu-id="04da1-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="04da1-140">In questo caso, il client visualizza due icone nella barra di stato di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="04da1-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="04da1-141">L'icona in basso a sinistra indica che non sono disponibili dispositivi audio e l'icona lampeggiante in basso a destra indica che è in corso l'associazione VDI: a.</span><span class="sxs-lookup"><span data-stu-id="04da1-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="04da1-142">Una volta completata l'associazione VDI, le icone cambiano per indicare il dispositivo audio che verrà usato per le chiamate e l'associazione VDI ha esito positivo: b.</span><span class="sxs-lookup"><span data-stu-id="04da1-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="04da1-143">L'utente può ora vedere la propria presenza su dispositivi compatibili con Skype for Business connessi al computer locale e effettuare e rispondere alle chiamate normalmente.</span><span class="sxs-lookup"><span data-stu-id="04da1-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="04da1-144">Risolvere i problemi relativi al plug-in VDI di Lync</span><span class="sxs-lookup"><span data-stu-id="04da1-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="04da1-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="04da1-145"><a name="tshoot_VDI"> </a></span></span>

<span data-ttu-id="04da1-146">Fare riferimento alle sezioni seguenti se si verificano problemi dopo l'installazione del plug-in VDI di Lync.</span><span class="sxs-lookup"><span data-stu-id="04da1-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="04da1-147">Problemi relativi all'installazione del plug-in VDI di Lync</span><span class="sxs-lookup"><span data-stu-id="04da1-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="04da1-148">Se si verificano problemi durante l'installazione del plug-in VDI di Lync, controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="04da1-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="04da1-149">Verificare che nella cartella specificata vi sia sufficiente spazio per le variabili di sistema TEMP e TMP.</span><span class="sxs-lookup"><span data-stu-id="04da1-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="04da1-150">Verificare che la protezione dalla scrittura sia disattivata.</span><span class="sxs-lookup"><span data-stu-id="04da1-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="04da1-151">Per istruzioni, fare riferimento alla documentazione del produttore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="04da1-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="04da1-152">Risoluzione dei problemi di abbinamento</span><span class="sxs-lookup"><span data-stu-id="04da1-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="04da1-153">Quando l'associazione del plug-in VDI di Lync non riesce, l'icona di associazione in basso a destra viene visualizzata come "X" rossa, come illustrato:</span><span class="sxs-lookup"><span data-stu-id="04da1-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="04da1-154">Di seguito sono riportati i possibili motivi degli errori e le azioni che è possibile eseguire per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="04da1-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="04da1-155">**Sono state inserite credenziali non corrette durante l'accesso.**</span><span class="sxs-lookup"><span data-stu-id="04da1-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="04da1-156">L'utente deve disconnettersi da Skype for Business e accedere di nuovo con le credenziali corrette.</span><span class="sxs-lookup"><span data-stu-id="04da1-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="04da1-157">Verrà visualizzata di nuovo la finestra di dialogo di abbinamento che segnalerà se l'abbinamento è andato a buon fine.</span><span class="sxs-lookup"><span data-stu-id="04da1-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="04da1-158">**È in esecuzione un'altra istanza del client desktop remoto.**</span><span class="sxs-lookup"><span data-stu-id="04da1-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="04da1-159">Se usano Connessione Desktop remoto in Windows, gli utenti devono eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="04da1-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="04da1-160">Avviare Gestione attività: premere **Alt+Ctrl+Canc** e quindi fare clic su **Avvia Gestione attività**.</span><span class="sxs-lookup"><span data-stu-id="04da1-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="04da1-161">Fare clic sulla scheda **Processi** e cercare tutti i processi denominati **mstsc.exe** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="04da1-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="04da1-162">Selezionare ogni processo **mstsc.exe** e fare clic su **Termina processo**.</span><span class="sxs-lookup"><span data-stu-id="04da1-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="04da1-163">Avviare una nuova sessione di desktop remoto e riprovare a connettersi.</span><span class="sxs-lookup"><span data-stu-id="04da1-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="04da1-164">**I file necessari non sono installati correttamente.**</span><span class="sxs-lookup"><span data-stu-id="04da1-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="04da1-165">Dopo aver installato il plug-in nel computer locale, verificare che questi file siano presenti in C:\Programmi\Microsoft Office\Office15 (o nella lettera di unità appropriata):</span><span class="sxs-lookup"><span data-stu-id="04da1-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="04da1-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="04da1-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="04da1-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="04da1-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="04da1-168">**Il client Skype for Business è in esecuzione nel computer locale.**</span><span class="sxs-lookup"><span data-stu-id="04da1-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="04da1-169">Per usare il plug-in VDI di Lync, un client Skype for Business non deve essere in esecuzione nel computer locale, altrimenti l'associazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="04da1-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="04da1-170">Come procedura consigliata, l'utente non deve installare un client Skype for Business nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="04da1-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="04da1-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04da1-171">See also</span></span>
<span data-ttu-id="04da1-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="04da1-172"><a name="tshoot_VDI"> </a></span></span>

[<span data-ttu-id="04da1-173">Pianificare Skype for Business in ambienti VDI</span><span class="sxs-lookup"><span data-stu-id="04da1-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
