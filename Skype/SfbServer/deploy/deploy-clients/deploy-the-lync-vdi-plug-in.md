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
description: In questo argomento vengono illustrate le procedure di distribuzione per l'utilizzo di Skype for business durante la connessione a un desktop virtuale remoto.
ms.openlocfilehash: f7ff99045c861c4435675d9e9e86deaedd499c10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805936"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="8334e-103">Distribuire il plug-in VDI di Lync con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8334e-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="8334e-104">In questo argomento vengono illustrate le procedure di distribuzione per l'utilizzo di Skype for business durante la connessione a un desktop virtuale remoto.</span><span class="sxs-lookup"><span data-stu-id="8334e-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="8334e-105">Le considerazioni relative alla pianificazione sono disponibili [in Plan for Skype for business in VDI Environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span><span class="sxs-lookup"><span data-stu-id="8334e-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="8334e-106">Un ambiente VDI (Virtual Desktop Infrastructure) viene utilizzato in alcune organizzazioni in cui i problemi di sicurezza e conformità sono particolarmente sensibili.</span><span class="sxs-lookup"><span data-stu-id="8334e-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="8334e-107">Gli utenti si trovano nei computer Windows locali e utilizzano client su un desktop virtuale.</span><span class="sxs-lookup"><span data-stu-id="8334e-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="8334e-108">L'utilizzo di Skype for business su una connessione di questo tipo richiede un ulteriore software plug-in VDI.</span><span class="sxs-lookup"><span data-stu-id="8334e-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="8334e-109">Sono disponibili due soluzioni per il componente plug-in VDI-uno offerto da Microsoft e uno offerto da Citrix.</span><span class="sxs-lookup"><span data-stu-id="8334e-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="8334e-110">Microsoft consiglia di utilizzare la nuova soluzione per il pacchetto di ottimizzazione in tempo reale HDX in nuove distribuzioni, ma continuerà a supportare il plug-in VDI originale di Lync per il resto del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="8334e-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="8334e-111">In questo argomento vengono fornite informazioni dettagliate sulla distribuzione del plug-in Microsoft Lync VDI, che è supportato solo in Windows 7 e Windows 8 o Windows Server 2008 e supporta solo i client Lync 2013 o Skype for business.</span><span class="sxs-lookup"><span data-stu-id="8334e-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="8334e-112">Non vi sono piani per l'aggiornamento di questo plugin, ma il [pacchetto di ottimizzazione in tempo reale di Citrix HDX](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) per Skype for business verrà aggiornato in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8334e-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="8334e-113">Preparare l'ambiente per il plug-in VDI di Lync</span><span class="sxs-lookup"><span data-stu-id="8334e-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="8334e-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="8334e-114"><a name="Prepare_vdi"> </a></span></span>

1. <span data-ttu-id="8334e-115">In Skype for Business Server, assicurarsi che EnableMediaRedirection sia impostato su TRUE per tutti gli utenti di plug-in di Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="8334e-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="8334e-116">Per informazioni dettagliate, vedere gli argomenti della Guida per il cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) e il cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="8334e-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="8334e-117">Nel server Data Center, installare il client Skype for business su tutti i desktop virtuali.</span><span class="sxs-lookup"><span data-stu-id="8334e-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="8334e-118">Nei computer locali installare il plug-in VDI di Lync.</span><span class="sxs-lookup"><span data-stu-id="8334e-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="8334e-119">Gli utenti dovrebbero ora connettere un dispositivo come un auricolare o una webcam al computer locale.</span><span class="sxs-lookup"><span data-stu-id="8334e-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="8334e-120">Configurare le impostazioni di connessione Desktop remoto</span><span class="sxs-lookup"><span data-stu-id="8334e-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="8334e-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="8334e-121"><a name="Prepare_vdi"> </a></span></span>

<span data-ttu-id="8334e-122">Per preparare la connessione Desktop remoto per il plug-in VDI di Lync, eseguire la procedura seguente nel computer locale:</span><span class="sxs-lookup"><span data-stu-id="8334e-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="8334e-123">Se il computer locale esegue Windows 8, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="8334e-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="8334e-124">Se il computer locale esegue Windows 7 con SP1, installare la versione più recente di Windows 8 del [client Servizi Desktop remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span><span class="sxs-lookup"><span data-stu-id="8334e-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="8334e-125">Avviare il client Servizi Desktop remoto facendo clic sul pulsante **Start** e quindi su **Connessione desktop remoto**.</span><span class="sxs-lookup"><span data-stu-id="8334e-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="8334e-126">Fare clic su **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="8334e-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="8334e-127">Fare clic sulla scheda **risorse locali** . In **audio remoto** fare clic su **Impostazioni** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8334e-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="8334e-128">In **riproduzione audio remota** selezionare **Riproduci su questo computer**.</span><span class="sxs-lookup"><span data-stu-id="8334e-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="8334e-129">In **registrazione audio remota** selezionare **non registrare**.</span><span class="sxs-lookup"><span data-stu-id="8334e-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="8334e-130">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8334e-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="8334e-131">Fare clic sulla scheda **Experience** . In **prestazioni**, deselezionare la casella di controllo relativa alla **memorizzazione nella cache della bitmap persistente** .</span><span class="sxs-lookup"><span data-stu-id="8334e-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="8334e-132">Fare clic sulla scheda **generale** . In **computer**, digitare il nome del desktop virtuale e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="8334e-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="8334e-133">Accedere e usare Skype for business sul desktop virtuale</span><span class="sxs-lookup"><span data-stu-id="8334e-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="8334e-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="8334e-134"><a name="SfB_signin"> </a></span></span>

<span data-ttu-id="8334e-135">Dopo aver abilitato il plug-in VDI di Lync, l'utente segue questa procedura quando si accede a Skype for business sul desktop virtuale.</span><span class="sxs-lookup"><span data-stu-id="8334e-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="8334e-136">L'utente digita le proprie credenziali nel client Skype for business in esecuzione sul desktop virtuale.</span><span class="sxs-lookup"><span data-stu-id="8334e-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="8334e-137">Dopo che Skype for business ha rilevato il plug-in VDI di Lync, Skype for business richiede all'utente di immettere di nuovo le credenziali.</span><span class="sxs-lookup"><span data-stu-id="8334e-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="8334e-138">In questa finestra di dialogo è consigliabile che l'utente selezioni la casella di controllo **Salva la password** in modo che non venga richiesta di nuovo l'immissione delle credenziali per gli accessi successivi.</span><span class="sxs-lookup"><span data-stu-id="8334e-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="8334e-139">Skype for business inizia l'accoppiamento con il plug-in VDI di Lync.</span><span class="sxs-lookup"><span data-stu-id="8334e-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="8334e-140">In questo caso, il client visualizza due icone nella barra di stato di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="8334e-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="8334e-141">L'icona in basso a sinistra indica che non sono disponibili dispositivi audio e l'icona lampeggiante in basso a destra indica che l'accoppiamento VDI è in corso: a.</span><span class="sxs-lookup"><span data-stu-id="8334e-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="8334e-142">Dopo che l'accoppiamento VDI ha esito positivo, le icone cambiano per indicare il dispositivo audio che verrà utilizzato per le chiamate e il successo dell'accoppiamento VDI: b.</span><span class="sxs-lookup"><span data-stu-id="8334e-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="8334e-143">L'utente può ora vedere la propria presenza sui dispositivi compatibili con Skype for business che sono connessi al computer locale e rispondere alle chiamate come al solito.</span><span class="sxs-lookup"><span data-stu-id="8334e-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="8334e-144">Risoluzione dei problemi relativi al plug-in VDI di Lync</span><span class="sxs-lookup"><span data-stu-id="8334e-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="8334e-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="8334e-145"><a name="tshoot_VDI"> </a></span></span>

<span data-ttu-id="8334e-146">Se si verificano problemi dopo l'installazione del plug-in VDI di Lync, fare riferimento alle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8334e-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="8334e-147">Problemi relativi all'installazione del plug-in VDI di Lync</span><span class="sxs-lookup"><span data-stu-id="8334e-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="8334e-148">Se si verificano problemi relativi all'installazione del plug-in VDI di Lync, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8334e-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="8334e-149">Verificare che nella cartella specificata vi sia sufficiente spazio per le variabili di sistema TEMP e TMP.</span><span class="sxs-lookup"><span data-stu-id="8334e-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="8334e-150">Verificare che la protezione dalla scrittura sia disattivata.</span><span class="sxs-lookup"><span data-stu-id="8334e-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="8334e-151">Per istruzioni, fare riferimento alla documentazione del produttore del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8334e-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="8334e-152">Risoluzione dei problemi di abbinamento</span><span class="sxs-lookup"><span data-stu-id="8334e-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="8334e-153">Quando l'accoppiamento di plug-in di Lync VDI ha esito negativo, l'icona di accoppiamento in basso a destra viene visualizzata come "X" rossa, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8334e-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="8334e-154">Di seguito sono riportate le possibili cause degli errori e le azioni che è possibile eseguire per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="8334e-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="8334e-155">**Sono state inserite credenziali non corrette durante l'accesso.**</span><span class="sxs-lookup"><span data-stu-id="8334e-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="8334e-156">L'utente deve disconnettersi da Skype for business e accedere di nuovo con le credenziali corrette.</span><span class="sxs-lookup"><span data-stu-id="8334e-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="8334e-157">Verrà visualizzata di nuovo la finestra di dialogo di abbinamento che segnalerà se l'abbinamento è andato a buon fine.</span><span class="sxs-lookup"><span data-stu-id="8334e-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="8334e-158">**È in esecuzione un'altra istanza del client desktop remoto.**</span><span class="sxs-lookup"><span data-stu-id="8334e-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="8334e-159">Se si utilizza la connessione Desktop remoto in Windows, gli utenti devono eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8334e-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="8334e-160">Avviare Gestione attività: premere **Alt+Ctrl+Canc** e quindi fare clic su **Avvia Gestione attività**.</span><span class="sxs-lookup"><span data-stu-id="8334e-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="8334e-161">Fare clic sulla scheda **Processi** e cercare tutti i processi denominati **mstsc.exe** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8334e-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="8334e-162">Selezionare ogni processo **mstsc.exe** e fare clic su **Termina processo**.</span><span class="sxs-lookup"><span data-stu-id="8334e-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="8334e-163">Avviare una nuova sessione di desktop remoto e riprovare a connettersi.</span><span class="sxs-lookup"><span data-stu-id="8334e-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="8334e-164">**I file necessari non sono installati correttamente.**</span><span class="sxs-lookup"><span data-stu-id="8334e-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="8334e-165">Dopo aver installato il plug-in nel computer locale, verificare che questi file siano presenti in C:\Programmi\Microsoft Office\Office15 (o nella lettera di unità appropriata):</span><span class="sxs-lookup"><span data-stu-id="8334e-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="8334e-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="8334e-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="8334e-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="8334e-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="8334e-168">**Il client Skype for business è in esecuzione nel computer locale.**</span><span class="sxs-lookup"><span data-stu-id="8334e-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="8334e-169">Per utilizzare il plug-in VDI di Lync, non è necessario che un client Skype for business sia in esecuzione nel computer locale, altrimenti l'accoppiamento avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8334e-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="8334e-170">Come procedura consigliata, l'utente non deve installare un client Skype for business nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="8334e-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8334e-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8334e-171">See also</span></span>
<span data-ttu-id="8334e-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="8334e-172"><a name="tshoot_VDI"> </a></span></span>

[<span data-ttu-id="8334e-173">Pianificare Skype for business in ambienti VDI</span><span class="sxs-lookup"><span data-stu-id="8334e-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
