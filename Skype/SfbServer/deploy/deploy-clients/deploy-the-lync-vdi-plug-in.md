---
title: Distribuire il plug-in di Lync VDI con Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: In questo argomento vengono illustrate le procedure di distribuzione per l'uso di Skype for business durante la connessione a un desktop virtuale remoto.
ms.openlocfilehash: a3955ac3634dbf52b47b70482772e7302876bf1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191141"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="f65c7-103">Distribuire il plug-in di Lync VDI con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f65c7-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="f65c7-104">In questo argomento vengono illustrate le procedure di distribuzione per l'uso di Skype for business durante la connessione a un desktop virtuale remoto.</span><span class="sxs-lookup"><span data-stu-id="f65c7-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="f65c7-105">Le considerazioni sulla pianificazione sono disponibili [in piano per Skype for business in ambienti VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span><span class="sxs-lookup"><span data-stu-id="f65c7-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="f65c7-106">In alcune organizzazioni viene usato un ambiente VDI (Virtual Desktop Infrastructure) in cui i problemi di sicurezza e conformità sono particolarmente sensibili.</span><span class="sxs-lookup"><span data-stu-id="f65c7-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="f65c7-107">I loro utenti si trovano in computer Windows locali e usano i client su un desktop virtuale.</span><span class="sxs-lookup"><span data-stu-id="f65c7-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="f65c7-108">L'uso di Skype for business su una connessione simile richiede un ulteriore software di plug-in VDI.</span><span class="sxs-lookup"><span data-stu-id="f65c7-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="f65c7-109">Sono disponibili due soluzioni per il componente plug-in VDI-uno offerto da Microsoft e uno offerto da Citrix.</span><span class="sxs-lookup"><span data-stu-id="f65c7-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="f65c7-110">Microsoft consiglia di usare la nuova soluzione per l'ottimizzazione in tempo reale di HDX in nuove distribuzioni, ma continuerà a supportare il plug-in originale di Lync VDI per il resto del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="f65c7-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="f65c7-111">Questo argomento fornisce informazioni dettagliate sulla distribuzione del plug-in Microsoft Lync VDI, supportato solo in Windows 7 e Windows 8 o Windows Server 2008, e supporta solo i client Lync 2013 o Skype for business.</span><span class="sxs-lookup"><span data-stu-id="f65c7-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="f65c7-112">Non ci sono piani per aggiornare questo plug-in, ma il [pacchetto di ottimizzazione in realtime di Citrix HDX](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) per Skype for business verrà aggiornato in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="f65c7-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="f65c7-113">Preparare l'ambiente per il plug-in di Lync VDI</span><span class="sxs-lookup"><span data-stu-id="f65c7-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="f65c7-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="f65c7-114"></span></span>

1. <span data-ttu-id="f65c7-115">In Skype for Business Server verificare che EnableMediaRedirection sia impostato su TRUE per tutti gli utenti del plug-in di Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f65c7-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="f65c7-116">Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) e al cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f65c7-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="f65c7-117">Nel server Data Center installare il client Skype for business in tutti i desktop virtuali.</span><span class="sxs-lookup"><span data-stu-id="f65c7-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="f65c7-118">Nei computer locali installare il plug-in di Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f65c7-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="f65c7-119">Gli utenti devono ora connettere un dispositivo come un auricolare o una webcam al computer locale.</span><span class="sxs-lookup"><span data-stu-id="f65c7-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="f65c7-120">Configurare le impostazioni di connessione Desktop remoto</span><span class="sxs-lookup"><span data-stu-id="f65c7-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="f65c7-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="f65c7-121"></span></span>

<span data-ttu-id="f65c7-122">Per preparare la connessione Desktop remoto per il plug-in di Lync VDI, seguire questa procedura nel computer locale:</span><span class="sxs-lookup"><span data-stu-id="f65c7-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="f65c7-123">Se il computer locale è in uso in Windows 8, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="f65c7-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="f65c7-124">Se nel computer locale è in esecuzione Windows 7 con SP1, installare la versione più recente di Windows 8 del [client di Servizi Desktop remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span><span class="sxs-lookup"><span data-stu-id="f65c7-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="f65c7-125">Avviare il client Servizi Desktop remoto facendo clic su **Start**e quindi su **Connessione desktop remoto**.</span><span class="sxs-lookup"><span data-stu-id="f65c7-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="f65c7-126">Fare clic su **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="f65c7-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="f65c7-127">Fare clic sulla scheda **risorse locali** . In **audio remoto**fare clic su **Impostazioni**e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f65c7-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="f65c7-128">In **riproduzione audio remota**selezionare Riproduci **in questo computer**.</span><span class="sxs-lookup"><span data-stu-id="f65c7-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="f65c7-129">In **registrazione audio remota**selezionare non **registrare**.</span><span class="sxs-lookup"><span data-stu-id="f65c7-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="f65c7-130">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f65c7-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="f65c7-131">Fare clic sulla scheda **esperienza** . In **prestazioni**deselezionare la casella di controllo **memorizzazione nella cache persistente della bitmap** .</span><span class="sxs-lookup"><span data-stu-id="f65c7-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="f65c7-132">Fare clic sulla scheda **generale** . In **computer**Digitare il nome del desktop virtuale e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="f65c7-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="f65c7-133">Accedere e usare Skype for business sul desktop virtuale</span><span class="sxs-lookup"><span data-stu-id="f65c7-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="f65c7-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="f65c7-134"></span></span>

<span data-ttu-id="f65c7-135">Dopo aver abilitato il plug-in di Lync VDI, l'utente seguirà questi passaggi quando si accede a Skype for business sul desktop virtuale.</span><span class="sxs-lookup"><span data-stu-id="f65c7-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="f65c7-136">L'utente digita le proprie credenziali nel client Skype for business in uso sul desktop virtuale.</span><span class="sxs-lookup"><span data-stu-id="f65c7-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="f65c7-137">Dopo che Skype for business ha rilevato il plug-in di Lync VDI, Skype for business chiede all'utente di immettere di nuovo le credenziali.</span><span class="sxs-lookup"><span data-stu-id="f65c7-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="f65c7-138">In questa finestra di dialogo è consigliabile selezionare la casella di controllo **Salva la password** in modo che non venga richiesto di immettere le credenziali durante l'accesso successivo.</span><span class="sxs-lookup"><span data-stu-id="f65c7-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="f65c7-139">Skype for business inizia l'associazione con il plug-in di Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f65c7-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="f65c7-140">In questo caso, il client visualizza due icone nella barra di stato di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="f65c7-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="f65c7-141">L'icona nell'angolo in basso a sinistra indica che non sono disponibili dispositivi audio e l'icona lampeggiante in basso a destra indica che è in corso l'associazione VDI: a.</span><span class="sxs-lookup"><span data-stu-id="f65c7-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="f65c7-142">Dopo aver completato l'associazione VDI, le icone cambiano per indicare il dispositivo audio che verrà usato per le chiamate e il successo dell'associazione VDI: b.</span><span class="sxs-lookup"><span data-stu-id="f65c7-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="f65c7-143">L'utente può ora vedere la sua presenza nei dispositivi compatibili con Skype for business collegati al computer locale e rispondere alle chiamate come di consueto.</span><span class="sxs-lookup"><span data-stu-id="f65c7-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="f65c7-144">Risolvere i problemi relativi al plug-in di Lync VDI</span><span class="sxs-lookup"><span data-stu-id="f65c7-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="f65c7-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="f65c7-145"></span></span>

<span data-ttu-id="f65c7-146">Se si verificano problemi dopo l'installazione del plug-in di Lync VDI, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f65c7-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="f65c7-147">Problemi con l'installazione del plug-in di Lync VDI</span><span class="sxs-lookup"><span data-stu-id="f65c7-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="f65c7-148">In caso di problemi con l'installazione del plug-in di Lync VDI, verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f65c7-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="f65c7-149">Verificare che nella cartella specificata nelle variabili di sistema TEMP e TMP sia disponibile spazio sufficiente.</span><span class="sxs-lookup"><span data-stu-id="f65c7-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="f65c7-150">Verificare che la protezione da scrittura sia disattivata.</span><span class="sxs-lookup"><span data-stu-id="f65c7-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="f65c7-151">Per istruzioni, vedere la documentazione del produttore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f65c7-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="f65c7-152">Risoluzione dei problemi di associazione</span><span class="sxs-lookup"><span data-stu-id="f65c7-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="f65c7-153">Quando l'associazione dei plug-in di Lync VDI non riesce, l'icona di associazione nell'angolo in basso a destra viene visualizzata come "X" rossa, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f65c7-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="f65c7-154">Di seguito sono riportate le possibili cause degli errori e le azioni che è possibile eseguire per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="f65c7-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="f65c7-155">**L'utente ha immesso credenziali non corrette durante l'accesso.**</span><span class="sxs-lookup"><span data-stu-id="f65c7-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="f65c7-156">L'utente deve disconnettersi da Skype for business ed eseguire di nuovo l'accesso con le credenziali corrette.</span><span class="sxs-lookup"><span data-stu-id="f65c7-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="f65c7-157">La finestra di dialogo Associazione verrà ricomparsa e mostrerà se l'associazione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f65c7-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="f65c7-158">**È in corso un'altra istanza del client desktop remoto.**</span><span class="sxs-lookup"><span data-stu-id="f65c7-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="f65c7-159">Se si usa la connessione Desktop remoto in Windows, gli utenti devono eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f65c7-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="f65c7-160">Avviare Task Manager: premere **ALT + CTRL + CANC**e quindi fare clic su **Avvia Gestione attività**.</span><span class="sxs-lookup"><span data-stu-id="f65c7-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="f65c7-161">Fare clic sulla scheda **processi** e cercare tutti i processi denominati **mstsc. exe** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f65c7-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="f65c7-162">Evidenziare ogni processo **mstsc. exe** e quindi fare clic su **Termina processo**.</span><span class="sxs-lookup"><span data-stu-id="f65c7-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="f65c7-163">Avviare una nuova sessione di desktop remoto e riprovare a connettersi.</span><span class="sxs-lookup"><span data-stu-id="f65c7-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="f65c7-164">**I file necessari non sono stati installati correttamente.**</span><span class="sxs-lookup"><span data-stu-id="f65c7-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="f65c7-165">Dopo avere installato il plug-in nel computer locale, verificare che questi file siano presenti in C:\Programmi\Microsoft Office\Office15 (o nella lettera di unità appropriata):</span><span class="sxs-lookup"><span data-stu-id="f65c7-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="f65c7-166">LyncVdiPlugin. dll</span><span class="sxs-lookup"><span data-stu-id="f65c7-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="f65c7-167">UcVdi. dll</span><span class="sxs-lookup"><span data-stu-id="f65c7-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="f65c7-168">**Il client Skype for business è in uso nel computer locale.**</span><span class="sxs-lookup"><span data-stu-id="f65c7-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="f65c7-169">Per usare il plug-in di Lync VDI, non è necessario che un client Skype for business sia in esecuzione nel computer locale, altrimenti l'associazione non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="f65c7-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="f65c7-170">Come procedura consigliata, l'utente non deve installare un client Skype for business nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="f65c7-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f65c7-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f65c7-171">See also</span></span>
<span data-ttu-id="f65c7-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="f65c7-172"></span></span>

[<span data-ttu-id="f65c7-173">Pianificare Skype for business in ambienti VDI</span><span class="sxs-lookup"><span data-stu-id="f65c7-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
