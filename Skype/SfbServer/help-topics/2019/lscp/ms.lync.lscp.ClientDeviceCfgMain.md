---
title: Configurazione dei log del dispositivo
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: Il servizio Web aggiornamento dispositivi crea automaticamente file di log in cui viene registrata l'attività di aggiornamento dei dispositivi. Nell'ambito della strategia di gestione dei dati dell'organizzazione, è possibile impostare soglie per le dimensioni della cache dei dati di registro, le dimensioni dei file di registro o il periodo di tempo durante il quale un file di registro viene conservato prima di essere eliminato. È possibile modificare queste impostazioni in base alle esigenze dell'organizzazione. Se non si desidera che il servizio Web di aggiornamenti dispositivi elimini automaticamente i file di log, è possibile eliminarli manualmente, se necessario. Le impostazioni dei log possono essere modificate a livello globale o per singoli siti.
ms.openlocfilehash: 118f2e6d90e9c3f7559a5e129c844ccdf1ea9bf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830336"
---
# <a name="device-log-configuration"></a><span data-ttu-id="e2e9a-107">Configurazione dei log del dispositivo</span><span class="sxs-lookup"><span data-stu-id="e2e9a-107">Device Log Configuration</span></span>

<span data-ttu-id="e2e9a-108">Il servizio Web aggiornamento dispositivi crea automaticamente file di log in cui viene registrata l'attività di aggiornamento dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="e2e9a-109">Nell'ambito della strategia di gestione dei dati dell'organizzazione, è possibile impostare soglie per le dimensioni della cache dei dati di registro, le dimensioni dei file di registro o il periodo di tempo durante il quale un file di registro viene conservato prima di essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="e2e9a-110">È possibile modificare queste impostazioni in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="e2e9a-111">Se non si desidera che il servizio Web di aggiornamenti dispositivi elimini automaticamente i file di log, è possibile eliminarli manualmente, se necessario.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="e2e9a-112">Le impostazioni dei log possono essere modificate a livello globale o per singoli siti.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="e2e9a-113">È inoltre possibile configurare un'ora del giorno in cui si desidera che il servizio Web Aggiornamento dispositivi elimini automaticamente i file di registro precedenti al numero di giorni in cui è stato configurato il servizio in modo da conservare i file di registro (per impostazione predefinita, ovvero i file di registro che hanno più di 10 giorni).</span><span class="sxs-lookup"><span data-stu-id="e2e9a-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="e2e9a-114">Questa impostazione non può essere modificata utilizzando il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="e2e9a-115">Al contrario, è necessario utilizzare Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e2e9a-116">Per specificare l'ora del giorno in cui eliminare i file di registro scaduti, utilizzare il cmdlet **New-CsDeviceUpdateConfiguration** con il parametro -LogCleanUpTimeOfDay.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="e2e9a-117">Per informazioni dettagliate, [vedere New-CsDeviceUpdateConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e2e9a-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="e2e9a-p104">L'eliminazione dei file comporta la rimozione permanente dal file system. Dopo l'eliminazione di un file non sarà possibile recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e2e9a-120">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="e2e9a-120">Tasks you can perform</span></span>

<span data-ttu-id="e2e9a-121">Nella pagina **Configurazione log dispositivo** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2e9a-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="e2e9a-122">Aggiungere una configurazione dei log dispositivo a livello globale o per un sito o pool specifico.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="e2e9a-123">Modificare le opzioni per una configurazione dei log dispositivo esistente.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e2e9a-124">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="e2e9a-124">UI Reference</span></span>

<span data-ttu-id="e2e9a-125">Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="e2e9a-126">**Nuovo** È possibile aggiungere una nuova configurazione del log del dispositivo con l'ambito seguente:</span><span class="sxs-lookup"><span data-stu-id="e2e9a-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="e2e9a-127">Globale</span><span class="sxs-lookup"><span data-stu-id="e2e9a-127">Global</span></span>

  - <span data-ttu-id="e2e9a-128">Sito</span><span class="sxs-lookup"><span data-stu-id="e2e9a-128">Site</span></span>

- <span data-ttu-id="e2e9a-129">**Modifica** Puoi modificare le opzioni di una configurazione del log del dispositivo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="e2e9a-130">Usando questa voce, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2e9a-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="e2e9a-131">**Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per una configurazione del registro del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="e2e9a-132">**Seleziona tutto** Questa opzione consente di selezionare tutte le configurazioni dei log dei dispositivi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="e2e9a-133">**Elimina** Questa opzione consente di eliminare tutte le configurazioni dei log del dispositivo selezionate.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="e2e9a-134">**Aggiorna** Puoi aggiornare l'elenco di configurazioni dei log dei dispositivi per verificare lo stato delle opzioni di tutte le configurazioni dei log del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e2e9a-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2e9a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2e9a-135">See also</span></span>

[<span data-ttu-id="e2e9a-136">Modificare le impostazioni per i file di registro dell'attività di aggiornamento dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="e2e9a-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
