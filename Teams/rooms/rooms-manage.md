---
title: Panoramica della gestione per le sale di Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Panoramica della gestione per le sale di Microsoft teams.
ms.openlocfilehash: 3a56a03342ca0edb0da9dc9ed3a4cada77816bc7
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825884"
---
# <a name="management-overview"></a><span data-ttu-id="1d114-103">Panoramica della gestione</span><span class="sxs-lookup"><span data-stu-id="1d114-103">Management overview</span></span>

<span data-ttu-id="1d114-104">È essenziale sviluppare ed eseguire la manutenzione e le operazioni in corso per garantire che i sistemi Microsoft teams Rooms siano disponibili per gli utenti e per offrire un'esperienza utente ottimale.</span><span class="sxs-lookup"><span data-stu-id="1d114-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="1d114-105">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="1d114-105">Monitoring</span></span> 

<span data-ttu-id="1d114-106">Il monitoraggio dei sistemi Microsoft teams Rooms è costituito da due attività principali:</span><span class="sxs-lookup"><span data-stu-id="1d114-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

- <span data-ttu-id="1d114-107">Monitoraggio di dispositivi, applicazioni e periferiche</span><span class="sxs-lookup"><span data-stu-id="1d114-107">Device, application, and peripheral device monitoring</span></span>
- <span data-ttu-id="1d114-108">Monitoraggio qualità e affidabilità (Call Quality Dashboard)</span><span class="sxs-lookup"><span data-stu-id="1d114-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="1d114-109">Monitoraggio di dispositivi, applicazioni e periferiche Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="1d114-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="1d114-110">Per fare in modo che gli utenti siano in grado di usare le unità di Microsoft teams rooms, le unità devono essere accese, connesse alla rete con l'applicazione Microsoft teams Rooms correttamente configurata e connessa ai dispositivi periferici funzionanti.</span><span class="sxs-lookup"><span data-stu-id="1d114-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 

<span data-ttu-id="1d114-111">Le informazioni sullo stato dell'applicazione Microsoft teams Rooms e delle periferiche connesse vengono scritte dall'applicazione Microsoft teams Rooms nel registro eventi di Windows e documentate in [comprendere le voci del log](azure-monitor-manage.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="1d114-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="1d114-112">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="1d114-112">**Setting**</span></span>|<span data-ttu-id="1d114-113">**Permette**</span><span class="sxs-lookup"><span data-stu-id="1d114-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d114-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (DWORD) 1</span><span class="sxs-lookup"><span data-stu-id="1d114-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="1d114-115">Consente l'avvio delle sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d114-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="1d114-116">Power Management-\> in AC, disattivare lo schermo dopo 10 minuti</span><span class="sxs-lookup"><span data-stu-id="1d114-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="1d114-117">Power Management-\> su AC, non posizionare mai il sistema in modalità Sleep</span><span class="sxs-lookup"><span data-stu-id="1d114-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="1d114-118">Consente alle sale di Microsoft teams di disattivare i display allegati e di riattivarsi automaticamente</span><span class="sxs-lookup"><span data-stu-id="1d114-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="1d114-119">NET account/maxpwage: illimitato</span><span class="sxs-lookup"><span data-stu-id="1d114-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="1d114-120">O un mezzo equivalente per disabilitare la scadenza della password per l'account locale.</span><span class="sxs-lookup"><span data-stu-id="1d114-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="1d114-121">La mancata esecuzione di questa operazione causerà l'errore di accesso dell'account Skype che lamenta una password scaduta.</span><span class="sxs-lookup"><span data-stu-id="1d114-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="1d114-122">Tieni presente che questo ha un impatto su tutti gli account locali nel computer e quindi la mancata impostazione di questa operazione causerà anche l'eventuale scadenza dell'account amministrativo nella casella.</span><span class="sxs-lookup"><span data-stu-id="1d114-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="1d114-123">Consente all'account Skype di accedere sempre</span><span class="sxs-lookup"><span data-stu-id="1d114-123">Enables Skype account to always log in</span></span>  <br/> |

<span data-ttu-id="1d114-124">Il trasferimento di file tramite criteri di gruppo è illustrato in [configurare un elemento del file](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1d114-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="1d114-125">Gestione remota tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d114-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="1d114-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="1d114-126"><a name="RemotePS"> </a></span></span>

<span data-ttu-id="1d114-127">È consigliabile usare Microsoft Operations Manager Suite per monitorare i sistemi Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="1d114-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="1d114-128">Per informazioni su come configurare il monitoraggio e gli avvisi di base, vedere [distribuire Gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="1d114-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="1d114-129">Usando queste linee guida, puoi creare un dashboard semplice da usare per identificare eventuali problemi con le unità delle sale di Microsoft teams in tutta la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1d114-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="1d114-130">Punti decisionali</span><span class="sxs-lookup"><span data-stu-id="1d114-130">Decision points</span></span>|<ul><li><span data-ttu-id="1d114-131">Verificare che sia possibile usare Operations Management Suite per monitorare la distribuzione di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="1d114-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="1d114-132">Decidi la lista di distribuzione di destinazione che userai per gli avvisi tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1d114-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="1d114-133">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="1d114-133">Next steps</span></span>|<ul><li><span data-ttu-id="1d114-134">Definire l'approccio di monitoraggio qualità e affidabilità.</span><span class="sxs-lookup"><span data-stu-id="1d114-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="1d114-135">Monitoraggio qualità e affidabilità (Call Quality Dashboard)</span><span class="sxs-lookup"><span data-stu-id="1d114-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="1d114-136">Ti consigliamo di implementare procedure di monitoraggio della qualità e affidabilità operative in corso come parte della tua distribuzione per monitorare l'andamento della qualità e dell'affidabilità delle chiamate e delle riunioni, identificando le aree di interesse e lavorando verso una risoluzione.</span><span class="sxs-lookup"><span data-stu-id="1d114-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="1d114-137">Quando si caricano le informazioni sull'edificio in Call Quality dashboard, è possibile esaminare le tendenze per la qualità delle chiamate e l'affidabilità in base a un livello per edificio, che consente di confrontare facilmente gli edifici e di attirare l'attenzione su problemi specifici.</span><span class="sxs-lookup"><span data-stu-id="1d114-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span>

<span data-ttu-id="1d114-138">Ti consigliamo di rivedere e seguire la [Guida alla revisione della qualità dell'esperienza](https://aka.ms/qerguide) per identificare le tendenze di qualità e affidabilità e creare un piano di azione per risolverli.</span><span class="sxs-lookup"><span data-stu-id="1d114-138">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="1d114-139">Aggiornamento del sistema operativo Microsoft teams Rooms e dell'applicazione Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="1d114-139">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="1d114-140">È consigliabile aggiornare l'applicazione Microsoft teams Rooms OS e Microsoft teams Rooms per trarre vantaggio da aggiornamenti e miglioramenti del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1d114-140">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="1d114-141">Per informazioni dettagliate, vedere [gestire le sale di Microsoft teams](rooms-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="1d114-141">For detailed guidance, see [Manage Microsoft Teams Rooms](rooms-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="1d114-142">Aggiornamenti di Windows</span><span class="sxs-lookup"><span data-stu-id="1d114-142">Windows Updates</span></span>

<span data-ttu-id="1d114-143">Microsoft teams Rooms viene eseguito in Windows 10 Enterprise o Windows 10 Enterprise (contratto multilicenza) e riceve gli stessi aggiornamenti di Windows e le build del sistema operativo come desktop standard.</span><span class="sxs-lookup"><span data-stu-id="1d114-143">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="1d114-144">Per informazioni dettagliate, vedere [gestire gli aggiornamenti di Windows](updates.md) .</span><span class="sxs-lookup"><span data-stu-id="1d114-144">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="1d114-145">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1d114-145">Troubleshooting</span></span>

<span data-ttu-id="1d114-146">È consigliabile configurare l'avviso di Operations Management Suite come descritto nella sezione precedente, in modo che il team operativo e l'helpdesk vengano avvisati in caso di problemi con le sale di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="1d114-146">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="1d114-147">Le opzioni disponibili per la gestione remota di PowerShell sono descritte in [gestione remota tramite PowerShell](rooms-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="1d114-147">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="1d114-148">Nel caso in cui un dispositivo periferico sia disconnesso, potrebbe essere necessario affidarsi a "Smart Hand" locali o supporto IT per analizzare e riconnettere i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1d114-148">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="1d114-149">Per altre informazioni sulla risoluzione dei problemi e sulla modalità amministratore, vedere [modalità amministratore e gestione dispositivi](rooms-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="1d114-149">For more information about troubleshooting and admin mode, see [Admin mode and device management](rooms-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="1d114-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d114-150">See also</span></span>

[<span data-ttu-id="1d114-151">Guida di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="1d114-151">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="1d114-152">Pianificare le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d114-152">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="1d114-153">Distribuire le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d114-153">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="1d114-154">Configurare una console Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="1d114-154">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="1d114-155">Gestire le impostazioni della console Microsoft teams rooms in remoto con un file di configurazione XML</span><span class="sxs-lookup"><span data-stu-id="1d114-155">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
