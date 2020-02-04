---
title: Aggiornamento dispositivi
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft rilascia periodicamente un nuovo set di aggiornamenti del firmware del dispositivo per Skype for Business Phone Edition, che è possibile importare nei server e distribuire agli utenti. Per ottenere l'ultimo set di regole di aggiornamento dei dispositivi, passare alla pagina della guida e del supporto nel sito Web Microsoft e cercare forPhone Edition. scaricare il pacchetto di aggiornamento più recente ed estrarre i file in una cartella nel computer in cui devono essere caricati gli aggiornamenti. Dopo aver estratto i file, è possibile usare il cmdlet Import-CsDeviceUpdate per importare le regole di aggiornamento dei dispositivi presenti nel file CAB estratto, che sarà denominato UCUpdates.cab. Per informazioni dettagliate, vedere Import-CsDeviceUpdate.
ms.openlocfilehash: d82010d45ae550c49529720496fc202abb2f6e4c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705141"
---
# <a name="device-update"></a><span data-ttu-id="89902-106">Aggiornamento del dispositivo</span><span class="sxs-lookup"><span data-stu-id="89902-106">Device Update</span></span>

<span data-ttu-id="89902-107">Microsoft rilascia periodicamente un nuovo set di aggiornamenti del firmware del dispositivo per Skype for Business Phone Edition, che è possibile importare nei server e distribuire agli utenti.</span><span class="sxs-lookup"><span data-stu-id="89902-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="89902-108">Per ottenere il set più recente di regole di aggiornamento dei dispositivi, aprire la pagina del supporto tecnico del sito Web Microsoft e cercare "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="89902-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="89902-109">Scaricare il pacchetto di aggiornamento più recente ed estrarre i file in una cartella nel computer dove devono essere caricati gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="89902-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="89902-110">Dopo aver estratto i file, è possibile usare il cmdlet **Import-CsDeviceUpdate** per importare le regole di aggiornamento dei dispositivi presenti nel file CAB estratto, che sarà denominato UCUpdates.cab.</span><span class="sxs-lookup"><span data-stu-id="89902-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="89902-111">Per informazioni dettagliate, vedere [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89902-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="89902-112">Dopo aver importato le regole di aggiornamento del dispositivo, è possibile usare la pagina di **aggiornamento del dispositivo** per visualizzare e gestire queste regole per i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="89902-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="89902-113">È possibile verificare gli aggiornamenti del firmware e successivamente renderli disponibili per tutti i dispositivi pertinenti in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="89902-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="89902-114">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="89902-114">Tasks you can perform</span></span>

<span data-ttu-id="89902-115">Nella pagina **Aggiornamento dispositivi** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="89902-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="89902-116">Approvare aggiornamenti dei dispositivi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="89902-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="89902-117">Annullare o ripristinare aggiornamenti dei dispositivi in sospeso.</span><span class="sxs-lookup"><span data-stu-id="89902-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="89902-118">Eliminare aggiornamenti dei dispositivi dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="89902-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="89902-119">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="89902-119">UI Reference</span></span>

<span data-ttu-id="89902-120">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="89902-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="89902-121">**Modifica** Puoi usare questa opzione per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89902-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="89902-122">**Seleziona tutto** Questa opzione consente di selezionare tutti gli aggiornamenti dei dispositivi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="89902-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="89902-123">**Eliminare** Questa opzione consente di eliminare tutti gli aggiornamenti del dispositivo selezionati.</span><span class="sxs-lookup"><span data-stu-id="89902-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="89902-124">**Azione** È possibile selezionare uno o più aggiornamenti nell'elenco e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89902-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="89902-125">**Annullare gli aggiornamenti in sospeso** Questa opzione impedisce la distribuzione dell'aggiornamento selezionato nei dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="89902-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="89902-126">**Approva** Questa opzione consente di distribuire l'aggiornamento selezionato nei dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="89902-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="89902-127">**Ripristinare** Questa opzione consente di distribuire un aggiornamento approvato in precedenza ai dispositivi dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="89902-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="89902-128">**Aggiornare** Puoi aggiornare l'elenco per verificare lo stato di tutti gli aggiornamenti del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="89902-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="89902-129">Per informazioni dettagliate sul servizio Web Aggiornamento dispositivi, vedere [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="89902-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="89902-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89902-130">See also</span></span>

[<span data-ttu-id="89902-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="89902-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
