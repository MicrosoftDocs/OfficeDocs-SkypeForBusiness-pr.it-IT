---
title: Configurazione registro dispositivo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: Il servizio Web aggiornamento dispositivi crea automaticamente file di log in cui viene registrata l'attività di aggiornamento dei dispositivi. Come parte della strategia di gestione dei dati dell'organizzazione, è consigliabile impostare le soglie per la dimensione della cache dei dati del log, le dimensioni dei file di log o il periodo di tempo in cui un file di log viene mantenuto prima che venga eliminato. È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione. Se non si desidera che il servizio Web aggiornamento dispositivi elimini automaticamente i file di log, è possibile eliminarli manualmente, se necessario. Le impostazioni dei log possono essere modificate a livello globale o per singoli siti.
ms.openlocfilehash: e46811d40a7b93f5c59557c6744fb554b70aea2a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190277"
---
# <a name="device-log-configuration"></a><span data-ttu-id="7127f-107">Configurazione registro dispositivo</span><span class="sxs-lookup"><span data-stu-id="7127f-107">Device Log Configuration</span></span>

<span data-ttu-id="7127f-108">Il servizio Web aggiornamento dispositivi crea automaticamente file di log in cui viene registrata l'attività di aggiornamento dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7127f-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="7127f-109">Come parte della strategia di gestione dei dati dell'organizzazione, è consigliabile impostare le soglie per la dimensione della cache dei dati del log, le dimensioni dei file di log o il periodo di tempo in cui un file di log viene mantenuto prima che venga eliminato.</span><span class="sxs-lookup"><span data-stu-id="7127f-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="7127f-110">È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7127f-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="7127f-111">Se non si desidera che il servizio Web aggiornamento dispositivi elimini automaticamente i file di log, è possibile eliminarli manualmente, se necessario.</span><span class="sxs-lookup"><span data-stu-id="7127f-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="7127f-112">Le impostazioni dei log possono essere modificate a livello globale o per singoli siti.</span><span class="sxs-lookup"><span data-stu-id="7127f-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="7127f-113">È anche possibile configurare l'ora del giorno in cui si vuole che il servizio di aggiornamento del dispositivo web elimini automaticamente i file di log antecedenti al numero di giorni in cui il servizio è stato configurato per conservare i file di log (per impostazione predefinita, ovvero i file di log con più di 10 giorni di età).</span><span class="sxs-lookup"><span data-stu-id="7127f-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="7127f-114">Questa impostazione non può essere modificata usando il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7127f-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="7127f-115">Devi invece usare Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7127f-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="7127f-116">Per specificare l'ora del giorno in cui eliminare i file di log scaduti, usare il cmdlet **New-CsDeviceUpdateConfiguration** con il parametro-LogCleanUpTimeOfDay.</span><span class="sxs-lookup"><span data-stu-id="7127f-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="7127f-117">Per informazioni dettagliate, vedere [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7127f-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="7127f-p104">L'eliminazione dei file comporta la rimozione permanente dal file system. Dopo l'eliminazione di un file non sarà possibile recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="7127f-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="7127f-120">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="7127f-120">Tasks you can perform</span></span>

<span data-ttu-id="7127f-121">Nella pagina **Configurazione log dispositivo** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="7127f-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="7127f-122">Aggiungere una configurazione dei log dispositivo a livello globale o per un sito o pool specifico.</span><span class="sxs-lookup"><span data-stu-id="7127f-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="7127f-123">Modificare le opzioni per una configurazione del log del dispositivo esistente.</span><span class="sxs-lookup"><span data-stu-id="7127f-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7127f-124">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="7127f-124">UI Reference</span></span>

<span data-ttu-id="7127f-125">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="7127f-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="7127f-126">**Nuovo** È possibile aggiungere una nuova configurazione del log dei dispositivi con l'ambito seguente:</span><span class="sxs-lookup"><span data-stu-id="7127f-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="7127f-127">Globale</span><span class="sxs-lookup"><span data-stu-id="7127f-127">Global</span></span>

  - <span data-ttu-id="7127f-128">Sito</span><span class="sxs-lookup"><span data-stu-id="7127f-128">Site</span></span>

- <span data-ttu-id="7127f-129">**Modifica** È possibile modificare le opzioni di una configurazione del log dei dispositivi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7127f-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="7127f-130">Usando questa voce, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7127f-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="7127f-131">**Mostra dettagli** Questa opzione apre una finestra di dialogo in cui è possibile modificare le opzioni per una configurazione del log dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7127f-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="7127f-132">**Seleziona tutto** Questa opzione Seleziona tutta la configurazione del log dei dispositivi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7127f-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="7127f-133">**Eliminare** Questa opzione Elimina tutta la configurazione del log del dispositivo selezionata.</span><span class="sxs-lookup"><span data-stu-id="7127f-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="7127f-134">**Aggiornare** È possibile aggiornare l'elenco di configurazione del log dei dispositivi per verificare lo stato delle opzioni di tutta la configurazione del log dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="7127f-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="7127f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7127f-135">See also</span></span>

[<span data-ttu-id="7127f-136">Modify Settings for Log Files of Device Update Activity</span><span class="sxs-lookup"><span data-stu-id="7127f-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
