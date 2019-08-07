---
title: Manutenzione e operazioni di Microsoft teams rooms
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Leggere questo argomento per informazioni sulla gestione di Microsoft teams rooms, la nuova generazione di sistemi room Skype.
ms.openlocfilehash: b5397e3b5049b4e7945780ebba70c2aaa2fc154b
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "36183571"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="4f247-103">Manutenzione e operazioni di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="4f247-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="4f247-104">Leggere questo argomento per informazioni sulla gestione di Microsoft teams rooms, la nuova generazione di sistemi room Skype.</span><span class="sxs-lookup"><span data-stu-id="4f247-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="4f247-105">Microsoft teams Rooms è la soluzione di conferenza più recente di Microsoft progettata per trasformare la sala riunioni in un'esperienza ricca e collaborativa.</span><span class="sxs-lookup"><span data-stu-id="4f247-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="4f247-106">Gli utenti apprezzeranno l'interfaccia familiare di Microsoft o Skype for business e gli amministratori IT apprezzeranno un'app di Windows 10 Skype meeting facilmente distribuita e gestita.</span><span class="sxs-lookup"><span data-stu-id="4f247-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="4f247-107">Microsoft teams Rooms è progettato per sfruttare le attrezzature esistenti, come i pannelli LCD, per facilitare l'installazione per consentire a Microsoft teams o Skype for business di accedere alla sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="4f247-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="4f247-108">Con la configurazione aggiuntiva, la gestione remota è possibile usando Microsoft Azure monitor come descritto in [pianificare la gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-plan.md), [distribuire Gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-deploy.md), [Manage Dispositivi Microsoft teams Rooms con Azure monitor](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="4f247-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="4f247-109">È anche possibile [gestire le impostazioni della console Microsoft teams rooms in remoto con un file di configurazione XML](xml-config-file.md), che include l'applicazione di un tema di visualizzazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4f247-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="4f247-110">Raccolta di registri in Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="4f247-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="4f247-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="4f247-111"></span></span>

<span data-ttu-id="4f247-112">Per raccogliere i log, è necessario richiamare lo script di raccolta log fornito con l'app Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="4f247-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="4f247-113">In modalità amministratore avviare un prompt dei comandi con privilegi elevati ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4f247-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="4f247-114">I log verranno emessi come file ZIP in c:\rigel.</span><span class="sxs-lookup"><span data-stu-id="4f247-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="4f247-115">Inizio delle impostazioni di visualizzazione della sala</span><span class="sxs-lookup"><span data-stu-id="4f247-115">Front of Room Display Settings</span></span>
<span data-ttu-id="4f247-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="4f247-116"></span></span>

<span data-ttu-id="4f247-117">Configurare il lato anteriore della visualizzazione della sala in modalità estesa.</span><span class="sxs-lookup"><span data-stu-id="4f247-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="4f247-118">In questo modo si verificherà che l'interfaccia utente della console non sia duplicata in tale visualizzazione quando si esegue il ciclo di alimentazione sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="4f247-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f247-119">Un televisore consumer usato come parte anteriore dello schermo della sala deve supportare/abilitare la funzionalità CEC (Consumer Electronics Control) di HDMI in modo che possa passare automaticamente a un'origine video attiva dalla modalità standby.</span><span class="sxs-lookup"><span data-stu-id="4f247-119">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="4f247-120">Questa caratteristica non è supportata in tutti i televisori.</span><span class="sxs-lookup"><span data-stu-id="4f247-120">This feature is not supported on all TVs.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="4f247-121">Reimpostazione di Microsoft teams Rooms (ripristino di fabbrica)</span><span class="sxs-lookup"><span data-stu-id="4f247-121">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="4f247-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="4f247-122"></span></span>

<span data-ttu-id="4f247-123">Se Microsoft teams Rooms non è in esecuzione bene, potrebbe essere utile eseguire un ripristino di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="4f247-123">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="4f247-124">Questa operazione può essere eseguita nell'app Impostazioni nella scheda **ripristino** . sotto **Reimposta questo PC**Selezionare **inizia**e quindi **Rimuovi tutto**.</span><span class="sxs-lookup"><span data-stu-id="4f247-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="4f247-125">Seguire le istruzioni rimanenti per reimpostare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4f247-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f247-126">Si è verificato un problema noto in cui le sale di Microsoft teams possono diventare inutilizzabili se la funzione **Mantieni file-rimuove le app e le impostazioni, ma mantiene l'opzione file personali** selezionata durante il processo di ripristino di Windows.</span><span class="sxs-lookup"><span data-stu-id="4f247-126">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="4f247-127">Non __ usare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="4f247-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="4f247-128">Opzioni remote supportate</span><span class="sxs-lookup"><span data-stu-id="4f247-128">Supported Remote Options</span></span>
<span data-ttu-id="4f247-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="4f247-129"></span></span>

<span data-ttu-id="4f247-130">La tabella seguente riepiloga le possibili operazioni remote e i metodi che è possibile usare per realizzarle.</span><span class="sxs-lookup"><span data-stu-id="4f247-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="4f247-131">**Gruppo**</span><span class="sxs-lookup"><span data-stu-id="4f247-131">**Workgroup**</span></span>|<span data-ttu-id="4f247-132">**Non è stato aggiunto un dominio**</span><span class="sxs-lookup"><span data-stu-id="4f247-132">**Not domain joined**</span></span>|<span data-ttu-id="4f247-133">**Dominio Unito**</span><span class="sxs-lookup"><span data-stu-id="4f247-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4f247-134">Riavviare</span><span class="sxs-lookup"><span data-stu-id="4f247-134">Restart</span></span>  <br/> |<span data-ttu-id="4f247-135">Desktop remoto</span><span class="sxs-lookup"><span data-stu-id="4f247-135">Remote desktop</span></span>  <br/> <span data-ttu-id="4f247-136">PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="4f247-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="4f247-137">Desktop remoto (richiede ulteriore configurazione)</span><span class="sxs-lookup"><span data-stu-id="4f247-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="4f247-138">PowerShell remoto (richiede ulteriore configurazione)</span><span class="sxs-lookup"><span data-stu-id="4f247-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="4f247-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="4f247-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="4f247-140">Aggiornare il sistema operativo</span><span class="sxs-lookup"><span data-stu-id="4f247-140">Update OS</span></span>  <br/> |<span data-ttu-id="4f247-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="4f247-141">Windows Update</span></span>  <br/> |<span data-ttu-id="4f247-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="4f247-142">Windows Update</span></span>  <br/> <span data-ttu-id="4f247-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="4f247-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="4f247-144">Aggiornamento dell'app</span><span class="sxs-lookup"><span data-stu-id="4f247-144">App update</span></span>  <br/> |<span data-ttu-id="4f247-145">Windows Store</span><span class="sxs-lookup"><span data-stu-id="4f247-145">Windows Store</span></span>  <br/> |<span data-ttu-id="4f247-146">Windows Store</span><span class="sxs-lookup"><span data-stu-id="4f247-146">Windows Store</span></span>  <br/> <span data-ttu-id="4f247-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="4f247-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="4f247-148">Configurazione dell'account Skype</span><span class="sxs-lookup"><span data-stu-id="4f247-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="4f247-149">Attualmente non supportato</span><span class="sxs-lookup"><span data-stu-id="4f247-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="4f247-150">Attualmente non supportato</span><span class="sxs-lookup"><span data-stu-id="4f247-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="4f247-151">Registri di Access</span><span class="sxs-lookup"><span data-stu-id="4f247-151">Access logs</span></span>  <br/> |<span data-ttu-id="4f247-152">Attualmente non supportato</span><span class="sxs-lookup"><span data-stu-id="4f247-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="4f247-153">Attualmente non supportato</span><span class="sxs-lookup"><span data-stu-id="4f247-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="4f247-154">Configurazione dei criteri di gruppo per le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f247-154">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="4f247-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="4f247-155"></span></span>

<span data-ttu-id="4f247-156">In questa sezione vengono illustrate le impostazioni di sistema di cui le sale di Microsoft teams dipendono per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="4f247-156">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="4f247-157">Quando si partecipa a Microsoft teams Rooms a un dominio, verificare che i criteri di gruppo non eseguano l'override delle impostazioni nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4f247-157">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="4f247-158">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="4f247-158">**Setting**</span></span>|<span data-ttu-id="4f247-159">**Permette**</span><span class="sxs-lookup"><span data-stu-id="4f247-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4f247-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="4f247-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="4f247-161">Consente l'avvio delle sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f247-161">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="4f247-162">Power Management-\> in AC, disattivare lo schermo dopo 10 minuti</span><span class="sxs-lookup"><span data-stu-id="4f247-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="4f247-163">Power Management-\> su AC, non posizionare mai il sistema in modalità Sleep</span><span class="sxs-lookup"><span data-stu-id="4f247-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="4f247-164">Consente alle sale di Microsoft teams di disattivare i display allegati e di riattivarsi automaticamente</span><span class="sxs-lookup"><span data-stu-id="4f247-164">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="4f247-165">NET account/maxpwage: illimitato</span><span class="sxs-lookup"><span data-stu-id="4f247-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="4f247-166">O un mezzo equivalente per disabilitare la scadenza della password per l'account locale.</span><span class="sxs-lookup"><span data-stu-id="4f247-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="4f247-167">La mancata esecuzione di questa operazione causerà l'errore di accesso dell'account Skype che lamenta una password scaduta.</span><span class="sxs-lookup"><span data-stu-id="4f247-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="4f247-168">Tieni presente che questo ha un impatto su tutti gli account locali nel computer e quindi la mancata impostazione di questa operazione causerà anche l'eventuale scadenza dell'account amministrativo nella casella.</span><span class="sxs-lookup"><span data-stu-id="4f247-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="4f247-169">Consente all'account Skype di accedere sempre</span><span class="sxs-lookup"><span data-stu-id="4f247-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="4f247-170">Il trasferimento di file tramite criteri di gruppo è illustrato in [configurare un elemento del file](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="4f247-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="4f247-171">Quando il dispositivo Microsoft teams Rooms è compatibile con la versione successiva del sistema operativo Windows 10, il dispositivo viene aggiornato automaticamente alla versione successiva tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="4f247-171">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="4f247-172">Il dispositivo Microsoft teams Rooms non deve essere aggiornato manualmente alla prossima versione di Windows 10 o tramite l'abilitazione dei criteri di gruppo di Windows Update for business (WUFB) "Seleziona il livello di conformità di Windows per gli aggiornamenti che vuoi ricevere" e "Seleziona quando si compila l'anteprima e Gli aggiornamenti delle caratteristiche vengono ricevuti tramite GPO.</span><span class="sxs-lookup"><span data-stu-id="4f247-172">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="4f247-173">Un dispositivo con questi criteri di gruppo abilitato è noto per l'esecuzione in problemi relativi all'aggiornamento del sistema operativo Windows 10 dall'app Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="4f247-173">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="4f247-174">Gestione remota tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f247-174">Remote Management using PowerShell</span></span>
<span data-ttu-id="4f247-175"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="4f247-175"></span></span>

<span data-ttu-id="4f247-176">È possibile eseguire le operazioni di gestione seguenti in remoto usando PowerShell (vedere la tabella seguente per gli esempi di script):</span><span class="sxs-lookup"><span data-stu-id="4f247-176">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="4f247-177">Ottenere i dispositivi allegati</span><span class="sxs-lookup"><span data-stu-id="4f247-177">Get attached devices</span></span>
    
- <span data-ttu-id="4f247-178">Ottenere lo stato dell'app</span><span class="sxs-lookup"><span data-stu-id="4f247-178">Get app status</span></span>
    
- <span data-ttu-id="4f247-179">Ottenere informazioni di sistema</span><span class="sxs-lookup"><span data-stu-id="4f247-179">Get system info</span></span>
    
- <span data-ttu-id="4f247-180">Riavviare il sistema</span><span class="sxs-lookup"><span data-stu-id="4f247-180">Reboot system</span></span>
    
- <span data-ttu-id="4f247-181">Recuperare i registri</span><span class="sxs-lookup"><span data-stu-id="4f247-181">Retrieve logs</span></span>
    
- <span data-ttu-id="4f247-182">Trasferire file (richiede un dominio-joined Microsoft teams rooms)</span><span class="sxs-lookup"><span data-stu-id="4f247-182">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="4f247-183">Questa funzionalità è disinserita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4f247-183">This functionality is off by default.</span></span> <span data-ttu-id="4f247-184">Per eseguire le operazioni seguenti, è necessario abilitare Remote PowerShell per l'ambiente nel sistema Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="4f247-184">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="4f247-185">Vedere la documentazione relativa a **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** per informazioni su come abilitare Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f247-185">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="4f247-186">Ad esempio, è possibile abilitare Remote PowerShell come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4f247-186">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="4f247-187">Accedere come amministratore in un dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="4f247-187">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="4f247-188">Aprire un prompt dei comandi di PowerShell con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="4f247-188">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="4f247-189">Immettere il comando seguente: Enable-PSRemoting-force</span><span class="sxs-lookup"><span data-stu-id="4f247-189">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="4f247-190">Per eseguire un'operazione di gestione:</span><span class="sxs-lookup"><span data-stu-id="4f247-190">To perform a management operation:</span></span>
  
1. <span data-ttu-id="4f247-191">Accedere a un PC con le credenziali dell'account che dispongano delle autorizzazioni per eseguire i comandi di PowerShell in un dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="4f247-191">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="4f247-192">Aprire un prompt dei comandi di PowerShell normale nel PC.</span><span class="sxs-lookup"><span data-stu-id="4f247-192">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="4f247-193">Copiare il testo del comando dalla tabella seguente e incollarlo alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="4f247-193">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="4f247-194">Sostituire `<Device fqdn>` i campi con valori FQDN appropriati per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4f247-194">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="4f247-195">Sostituire \* \<Path\> \* con il nome file e il percorso locale del file di configurazione Master SkypeSettings. XML (o immagine del tema).</span><span class="sxs-lookup"><span data-stu-id="4f247-195">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="4f247-196">Per ottenere i dispositivi allegati</span><span class="sxs-lookup"><span data-stu-id="4f247-196">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="4f247-197">Ottenere lo stato dell'app</span><span class="sxs-lookup"><span data-stu-id="4f247-197">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="4f247-198">Ottenere informazioni di sistema</span><span class="sxs-lookup"><span data-stu-id="4f247-198">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="4f247-199">Riavviare il sistema</span><span class="sxs-lookup"><span data-stu-id="4f247-199">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="4f247-200">Recuperare i registri</span><span class="sxs-lookup"><span data-stu-id="4f247-200">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="4f247-201">Spingere un file di configurazione XML (o un elemento grafico del tema)</span><span class="sxs-lookup"><span data-stu-id="4f247-201">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="4f247-202">Aggiornamenti software</span><span class="sxs-lookup"><span data-stu-id="4f247-202">Software updates</span></span>
<span data-ttu-id="4f247-203"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="4f247-203"></span></span>

<span data-ttu-id="4f247-204">Per impostazione predefinita, Microsoft teams Rooms cerca di connettersi a Windows Store per ottenere l'ultima versione del software Microsoft teams rooms, in modo che il dispositivo necessiti di un regolare accesso a Internet.</span><span class="sxs-lookup"><span data-stu-id="4f247-204">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="4f247-205">Prima di contattare Microsoft con i problemi di supporto, assicurati che il dispositivo Microsoft teams rooms sia caricato con la versione più recente dell'app.</span><span class="sxs-lookup"><span data-stu-id="4f247-205">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="4f247-206">Per impostazione predefinita, Microsoft teams Rooms si connette a Windows Update per recuperare gli aggiornamenti del firmware del sistema operativo e del dispositivo periferico USB e li installa all'esterno degli orari di ufficio configurati.</span><span class="sxs-lookup"><span data-stu-id="4f247-206">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="4f247-207">Puoi configurare gli orari di ufficio effettuando l'accesso all'account di amministratore ed eseguendo l'app Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4f247-207">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="4f247-208">Per gestire manualmente gli aggiornamenti e non è possibile seguire la procedura normale per [Microsoft Store for business](https://businessstore.microsoft.com/store) per [distribuire le app offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), puoi acquisire il file appx appropriato e le dipendenze dal kit di [distribuzione](https://go.microsoft.com/fwlink/?linkid=851168) (da istruzioni per [configurare una console Microsoft teams Rooms](console.md)che può essere usata con SCCM.</span><span class="sxs-lookup"><span data-stu-id="4f247-208">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="4f247-209">La versione del kit di distribuzione è in ritardo rispetto alla versione dello Store, quindi potrebbe non corrispondere sempre alla build più recente disponibile.</span><span class="sxs-lookup"><span data-stu-id="4f247-209">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="4f247-210">Per eseguire l'aggiornamento usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f247-210">To update using Powershell</span></span>

1. <span data-ttu-id="4f247-211">Estrai il pacchetto dal file [MSI](https://go.microsoft.com/fwlink/?linkid=851168) di installazione a una condivisione a cui il dispositivo può accedere.</span><span class="sxs-lookup"><span data-stu-id="4f247-211">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="4f247-212">Eseguire lo script seguente per la destinazione dei dispositivi Microsoft teams Rooms \<,\> modificando la condivisione alla condivisione del dispositivo in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="4f247-212">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="4f247-213">Modalità di amministrazione e gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="4f247-213">Admin mode and device management</span></span>
<span data-ttu-id="4f247-214"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="4f247-214"></span></span>

<span data-ttu-id="4f247-215">Alcune funzioni di gestione, come l'installazione manuale di un certificato CA privato, richiedono l'immissione del dispositivo Surface Pro in modalità amministratore.</span><span class="sxs-lookup"><span data-stu-id="4f247-215">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="4f247-216">Passare alla modalità amministratore e viceversa quando è in corso l'app Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="4f247-216">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="4f247-217">Riagganciare le chiamate in corso e tornare alla schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="4f247-217">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="4f247-218">Selezionare l'icona dell'ingranaggio e visualizzare il menu (le opzioni sono **Impostazioni**, accessibilità e **dispositivo di riavvio** ). \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4f247-218">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="4f247-219">Selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="4f247-219">Select **Settings**.</span></span>
    
4. <span data-ttu-id="4f247-220">Immettere la password di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4f247-220">Enter the Administrator Password.</span></span> <span data-ttu-id="4f247-221">Verrà visualizzata la schermata di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4f247-221">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4f247-222">Se il dispositivo non è collegato al dominio, per impostazione predefinita verrà usato l'account amministrativo locale (nome utente "amministratore").</span><span class="sxs-lookup"><span data-stu-id="4f247-222">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="4f247-223">La password predefinita per questo account è "SFB", ma è consigliabile che l'organizzazione modifichi questa operazione per motivi di sicurezza al più presto possibile.</span><span class="sxs-lookup"><span data-stu-id="4f247-223">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="4f247-224">Se il computer è collegato al dominio, è possibile accedere con un account di dominio con privilegi appropriati.</span><span class="sxs-lookup"><span data-stu-id="4f247-224">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="4f247-225">Selezionare **impostazioni di Windows** nella colonna sinistra.</span><span class="sxs-lookup"><span data-stu-id="4f247-225">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="4f247-226">Scegliere **Accedi ad amministratore**.</span><span class="sxs-lookup"><span data-stu-id="4f247-226">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="4f247-227">Immettere la password di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4f247-227">Enter the Administrator Password.</span></span> <span data-ttu-id="4f247-228">In questo modo si disconnetterà con garbo l'app e ti porterà alla schermata di accesso di Windows.</span><span class="sxs-lookup"><span data-stu-id="4f247-228">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="4f247-229">Accedere al desktop con le credenziali amministrative.</span><span class="sxs-lookup"><span data-stu-id="4f247-229">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="4f247-230">Avrai i privilegi necessari per gestire il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4f247-230">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="4f247-231">Eseguire le attività amministrative necessarie.</span><span class="sxs-lookup"><span data-stu-id="4f247-231">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="4f247-232">Disconnettersi dall'account di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4f247-232">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="4f247-233">Tornare a Microsoft teams Rooms selezionando l'icona dell'account utente all'estrema sinistra dello schermo e quindi selezionando **Skype**.</span><span class="sxs-lookup"><span data-stu-id="4f247-233">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="4f247-234">Se l'utente **Skype** non è elencato, potrebbe essere necessario selezionare un **altro utente** e immettere **.\skype** come nome utente ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="4f247-234">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="4f247-235">La console è ora tornata nella modalità operativa normale. La procedura seguente richiede di allegare una tastiera al dispositivo se non ne è già collegata una.</span><span class="sxs-lookup"><span data-stu-id="4f247-235">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="4f247-236">Passare alla modalità amministratore e viceversa quando l'app Microsoft teams Rooms si arresta in modo anomalo</span><span class="sxs-lookup"><span data-stu-id="4f247-236">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="4f247-237">Premere il tasto Windows cinque volte in rapida successione.</span><span class="sxs-lookup"><span data-stu-id="4f247-237">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="4f247-238">Verrà visualizzata la schermata di accesso di Windows.</span><span class="sxs-lookup"><span data-stu-id="4f247-238">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="4f247-239">Accedere al desktop con le credenziali amministrative.</span><span class="sxs-lookup"><span data-stu-id="4f247-239">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4f247-240">Questo metodo non disconnette l'utente Skype o chiude con garbo l'app, ma la userai se l'app non risponde e l'altro metodo non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="4f247-240">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="4f247-241">Eseguire le attività amministrative necessarie.</span><span class="sxs-lookup"><span data-stu-id="4f247-241">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="4f247-242">Riavviare il computer al termine.</span><span class="sxs-lookup"><span data-stu-id="4f247-242">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="4f247-243">La console viene riavviata nella modalità operativa normale, in cui è in esecuzione l'app Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="4f247-243">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="4f247-244">È possibile rimuovere la tastiera, se è stata allegata per consentire l'esecuzione di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="4f247-244">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="4f247-245">Suggerimenti per la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="4f247-245">Troubleshooting tips</span></span>
   <span data-ttu-id="4f247-246"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="4f247-246"></span></span>

- <span data-ttu-id="4f247-247">Gli inviti alle riunioni potrebbero non essere visualizzati quando vengono inviati oltre i limiti del dominio, ad esempio tra due società.</span><span class="sxs-lookup"><span data-stu-id="4f247-247">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="4f247-248">In questi casi, gli amministratori IT devono decidere se consentire agli utenti esterni di pianificare una riunione.</span><span class="sxs-lookup"><span data-stu-id="4f247-248">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="4f247-249">Microsoft teams Rooms non supporta il reindirizzamento di Exchange Autodiscover tramite Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="4f247-249">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="4f247-250">In generale, è consigliabile che gli amministratori IT disattivino eventuali endpoint audio che non intendono usare.</span><span class="sxs-lookup"><span data-stu-id="4f247-250">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="4f247-251">Se nell'anteprima della sala viene visualizzata un'immagine speculare, l'amministratore IT può correggere l'uso della videocamera in bicicletta o l'orientamento dell'immagine usando il telecomando della videocamera.</span><span class="sxs-lookup"><span data-stu-id="4f247-251">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="4f247-252">Si nota che la perdita di accesso al touchscreen da console si verifica.</span><span class="sxs-lookup"><span data-stu-id="4f247-252">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="4f247-253">In questi casi, il problema viene a volte risolto riavviando il sistema Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="4f247-253">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
    
- <span data-ttu-id="4f247-254">La perdita di audio locale durante la connessione di un PC alla console tramite l'acquisizione tramite cavo è nota.</span><span class="sxs-lookup"><span data-stu-id="4f247-254">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="4f247-255">In questi casi, il riavvio del PC può risolvere il problema di riproduzione audio locale.</span><span class="sxs-lookup"><span data-stu-id="4f247-255">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
