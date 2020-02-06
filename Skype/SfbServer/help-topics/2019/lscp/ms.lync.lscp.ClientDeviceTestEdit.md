---
title: Dispositivo di test Crea nuovo o modifica esistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: La funzionalità Dispositivo di test opera in combinazione con la funzionalità Aggiornamento dispositivi. È possibile aggiungere un dispositivo di test nella pagina Dispositivo di test e quindi usare il dispositivo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. Il dispositivo può essere testato a livello globale, ovvero in tutto l'ambiente, o in un singolo sito. Per identificare un dispositivo di test, usare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando si aggiunge un dispositivo, questo viene visualizzato nell'elenco nella pagina del dispositivo di test del pannello di controllo di Skype for Business Server.
ms.openlocfilehash: 2101fb712d1084506de617ab234e3e8e0a03a961
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794545"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="22977-107">Dispositivo di test: crearne uno nuovo o modificarne uno esistente</span><span class="sxs-lookup"><span data-stu-id="22977-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="22977-108">La funzionalità Dispositivo di test opera in combinazione con la funzionalità Aggiornamento dispositivi.</span><span class="sxs-lookup"><span data-stu-id="22977-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="22977-109">È possibile aggiungere un dispositivo di test nella pagina **Dispositivo di test** e quindi usare il dispositivo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione.</span><span class="sxs-lookup"><span data-stu-id="22977-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="22977-110">Il dispositivo può essere testato a livello globale, ovvero in tutto l'ambiente, o in un singolo sito.</span><span class="sxs-lookup"><span data-stu-id="22977-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="22977-111">Per identificare un dispositivo di test, usare il relativo indirizzo MAC (Media Access Control) o il numero di serie.</span><span class="sxs-lookup"><span data-stu-id="22977-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="22977-112">Quando si aggiunge un dispositivo, questo viene visualizzato nell'elenco nella pagina del **dispositivo di test** del pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="22977-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="22977-113">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="22977-113">Tasks you can perform</span></span>

<span data-ttu-id="22977-114">Nella pagina **Nuovo dispositivo di test** o **Modifica dispositivo di test** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="22977-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="22977-115">Aggiungere un nuovo dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="22977-115">Add a new test device.</span></span>

- <span data-ttu-id="22977-116">Modificare le proprietà di un dispositivo di test esistente.</span><span class="sxs-lookup"><span data-stu-id="22977-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="22977-117">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="22977-117">UI Reference</span></span>

<span data-ttu-id="22977-118">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="22977-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="22977-119">**Ambito** Identifica l'ambito (globale o sito) del dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="22977-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="22977-120">**Nome** È possibile aggiungere o modificare il nome del dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="22977-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="22977-121">**Nome dispositivo** È possibile aggiungere o modificare il nome del dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="22977-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="22977-122">**Tipo di identificatore** È possibile selezionare il metodo da usare per identificare il dispositivo selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="22977-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="22977-123">**Indirizzo MAC**</span><span class="sxs-lookup"><span data-stu-id="22977-123">**MAC address**</span></span>

  - <span data-ttu-id="22977-124">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="22977-124">**Serial number**</span></span>

- <span data-ttu-id="22977-125">**Identificatore univoco** È possibile digitare l'indirizzo MAC o il numero di serie del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22977-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="22977-126">Per informazioni dettagliate sui dispositivi di test, vedere [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="22977-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="22977-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22977-127">See also</span></span>

[<span data-ttu-id="22977-128">Dispositivo di test</span><span class="sxs-lookup"><span data-stu-id="22977-128">Test Device</span></span>](ms.lync.lscp.ClientDeviceTestMain.md)

[<span data-ttu-id="22977-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="22977-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="22977-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="22977-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="22977-131">Visualizzare gli aggiornamenti software per i dispositivi dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="22977-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
