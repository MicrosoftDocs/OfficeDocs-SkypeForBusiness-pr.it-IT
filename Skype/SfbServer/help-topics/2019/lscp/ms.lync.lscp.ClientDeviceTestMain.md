---
title: Dispositivo di test
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
ROBOTS: NOINDEX, NOFOLLOW
description: È possibile aggiungere un dispositivo di test nella pagina Dispositivo di test e quindi utilizzarlo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. È possibile testare un dispositivo a livello globale (in tutto l'ambiente) o all'interno di un singolo sito. Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando si aggiunge un dispositivo, quest'ultimo viene visualizzato nell'elenco nella pagina dispositivo di test del pannello di controllo di Skype for Business Server.
ms.openlocfilehash: 78365c32f54307eb9b557a8ac2a7287a59acd81f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830316"
---
# <a name="test-device"></a><span data-ttu-id="127a0-106">Dispositivo di test</span><span class="sxs-lookup"><span data-stu-id="127a0-106">Test Device</span></span>

<span data-ttu-id="127a0-107">È possibile aggiungere un dispositivo di test nella pagina **Dispositivo di test** e quindi utilizzarlo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione.</span><span class="sxs-lookup"><span data-stu-id="127a0-107">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="127a0-108">È possibile testare un dispositivo a livello globale (in tutto l'ambiente) o all'interno di un singolo sito.</span><span class="sxs-lookup"><span data-stu-id="127a0-108">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="127a0-109">Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie.</span><span class="sxs-lookup"><span data-stu-id="127a0-109">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="127a0-110">Quando si aggiunge un dispositivo, quest'ultimo viene visualizzato nell'elenco nella pagina **dispositivo di test** del pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="127a0-110">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="127a0-111">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="127a0-111">Tasks you can perform</span></span>

<span data-ttu-id="127a0-112">Nella pagina **Dispositivo di test** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="127a0-112">You can perform the following tasks on the **Test Device** page:</span></span>

- <span data-ttu-id="127a0-113">Aggiungere un dispositivo di test a livello globale o per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="127a0-113">Add a test device globally or for a particular site.</span></span>

- <span data-ttu-id="127a0-114">Modificare le opzioni per un dispositivo di test esistente.</span><span class="sxs-lookup"><span data-stu-id="127a0-114">Modify the options for an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="127a0-115">Riferimento all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="127a0-115">UI Reference</span></span>

<span data-ttu-id="127a0-116">Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="127a0-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="127a0-117">**Nuovo** È possibile aggiungere un nuovo dispositivo di test con l'ambito seguente:</span><span class="sxs-lookup"><span data-stu-id="127a0-117">**New** You can add a new test device with the following scope:</span></span>

  - <span data-ttu-id="127a0-118">Globale</span><span class="sxs-lookup"><span data-stu-id="127a0-118">Global</span></span>

  - <span data-ttu-id="127a0-119">Sito</span><span class="sxs-lookup"><span data-stu-id="127a0-119">Site</span></span>

- <span data-ttu-id="127a0-120">**Modifica** È possibile modificare le opzioni di un dispositivo di test nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="127a0-120">**Edit** You can change the options of a test device in the list.</span></span> <span data-ttu-id="127a0-121">Usando questa voce, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="127a0-121">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="127a0-122">**Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per un dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="127a0-122">**Show details** This option opens a dialog box in which you can change the options for a test device.</span></span>

  - <span data-ttu-id="127a0-123">**Seleziona tutto** Questa opzione consente di selezionare tutti i dispositivi di test nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="127a0-123">**Select All** This option selects all test devices in the list.</span></span>

  - <span data-ttu-id="127a0-124">**Eliminare** Questa opzione consente di eliminare tutti i dispositivi di test selezionati.</span><span class="sxs-lookup"><span data-stu-id="127a0-124">**Delete** This option deletes all selected test devices.</span></span>

- <span data-ttu-id="127a0-125">**Aggiorna** È possibile aggiornare l'elenco del dispositivo di test per verificare lo stato delle opzioni di tutti i dispositivi di test.</span><span class="sxs-lookup"><span data-stu-id="127a0-125">**Refresh** You can refresh the test device list to verify the status of the options of all test devices.</span></span>

<span data-ttu-id="127a0-126">Per informazioni dettagliate sui dispositivi di test, vedere [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="127a0-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="127a0-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="127a0-127">See also</span></span>

[<span data-ttu-id="127a0-128">Dispositivo di test: crearne uno nuovo o modificarne uno esistente</span><span class="sxs-lookup"><span data-stu-id="127a0-128">Test Device: Create New or Edit Existing</span></span>](ms.lync.lscp.ClientDeviceTestEdit.md)

[<span data-ttu-id="127a0-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="127a0-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="127a0-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="127a0-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="127a0-131">Visualizzare gli aggiornamenti software per i dispositivi nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="127a0-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
