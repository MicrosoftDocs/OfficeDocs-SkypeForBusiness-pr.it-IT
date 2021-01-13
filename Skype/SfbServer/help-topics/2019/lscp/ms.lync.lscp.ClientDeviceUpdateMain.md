---
title: Aggiornamento dispositivi
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft rilascia periodicamente un nuovo set di aggiornamenti del firmware del dispositivo per Skype for Business Phone Edition, che può essere importato nei server e distribuito agli utenti. È possibile ottenere l'ultimo set di regole di aggiornamento dei dispositivi accedendo alla pagina Guida e supporto del sito Web Microsoft e cercando forPhone Edition. scaricare il pacchetto di aggiornamento più recente ed estrarre i file in una cartella nel computer in cui devono essere caricati gli aggiornamenti. Dopo aver estratto i file, è possibile usare il cmdlet Import-CsDeviceUpdate per importare le regole di aggiornamento dei dispositivi presenti nel file CAB estratto, che sarà denominato UCUpdates.cab. Per informazioni dettagliate, vedere Import-CsDeviceUpdate.
ms.openlocfilehash: cd8b983990ff3bc5843c252a153eafaa47cd9a1e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830286"
---
# <a name="device-update"></a><span data-ttu-id="c9923-106">Aggiornamento dispositivi</span><span class="sxs-lookup"><span data-stu-id="c9923-106">Device Update</span></span>

<span data-ttu-id="c9923-107">Microsoft rilascia periodicamente un nuovo set di aggiornamenti del firmware del dispositivo per Skype for Business Phone Edition, che può essere importato nei server e distribuito agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c9923-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="c9923-108">Per ottenere il set più recente di regole di aggiornamento dei dispositivi, aprire la pagina del supporto tecnico del sito Web Microsoft e cercare "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="c9923-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="c9923-109">Scaricare il pacchetto di aggiornamento più recente ed estrarre i file in una cartella nel computer dove devono essere caricati gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="c9923-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="c9923-110">Dopo aver estratto i file, è possibile usare il cmdlet **Import-CsDeviceUpdate** per importare le regole di aggiornamento dei dispositivi presenti nel file CAB estratto, che sarà denominato UCUpdates.cab.</span><span class="sxs-lookup"><span data-stu-id="c9923-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="c9923-111">Per informazioni dettagliate, vedere [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c9923-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="c9923-112">Dopo aver importato le regole di aggiornamento dei dispositivi, è possibile utilizzare la pagina **aggiornamento dispositivi** per visualizzare e gestire tali regole per i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9923-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="c9923-113">È possibile verificare gli aggiornamenti del firmware e successivamente renderli disponibili per tutti i dispositivi pertinenti in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9923-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c9923-114">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="c9923-114">Tasks you can perform</span></span>

<span data-ttu-id="c9923-115">Nella pagina **Aggiornamento dispositivi** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9923-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="c9923-116">Approvare aggiornamenti dei dispositivi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c9923-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="c9923-117">Annullare o ripristinare aggiornamenti dei dispositivi in sospeso.</span><span class="sxs-lookup"><span data-stu-id="c9923-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="c9923-118">Eliminare aggiornamenti dei dispositivi dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="c9923-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c9923-119">Riferimento all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="c9923-119">UI Reference</span></span>

<span data-ttu-id="c9923-120">Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="c9923-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="c9923-121">**Modifica** È possibile utilizzare questa opzione per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9923-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="c9923-122">**Seleziona tutto** Questa opzione consente di selezionare tutti gli aggiornamenti dei dispositivi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c9923-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="c9923-123">**Eliminare** Questa opzione consente di eliminare tutti gli aggiornamenti dei dispositivi selezionati.</span><span class="sxs-lookup"><span data-stu-id="c9923-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="c9923-124">**Azione** È possibile selezionare uno o più aggiornamenti nell'elenco ed eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9923-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="c9923-125">**Annulla aggiornamenti in sospeso** Questa opzione impedisce la distribuzione dell'aggiornamento selezionato ai dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9923-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="c9923-126">**Approva** Questa opzione consente di distribuire l'aggiornamento selezionato ai dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9923-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="c9923-127">**Ripristino** Questa opzione consente di distribuire un aggiornamento precedentemente approvato ai dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9923-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="c9923-128">**Aggiorna** È possibile aggiornare l'elenco per verificare lo stato di tutti gli aggiornamenti dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c9923-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="c9923-129">Per informazioni dettagliate sul servizio Web Aggiornamento dispositivi, vedere [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c9923-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="c9923-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9923-130">See also</span></span>

[<span data-ttu-id="c9923-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="c9923-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
