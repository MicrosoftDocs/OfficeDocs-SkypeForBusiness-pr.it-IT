---
title: Dispositivo di testing creare nuovo o modificarne uno esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: La funzionalità Dispositivo di test opera in combinazione con la funzionalità Aggiornamento dispositivi. È possibile aggiungere un dispositivo di test nella pagina Dispositivo di test e quindi usare il dispositivo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. È possibile testare un dispositivo a livello globale (in tutto l'ambiente) o all'interno di un singolo sito. Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando si aggiunge un dispositivo, quest'ultimo viene visualizzato nell'elenco nella pagina dispositivo di test del pannello di controllo di Skype for Business Server.
ms.openlocfilehash: e1a8c570714b1096d14ac49260922c1a6dc3fecc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830326"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="9ce07-107">Dispositivo di test: crearne uno nuovo o modificarne uno esistente</span><span class="sxs-lookup"><span data-stu-id="9ce07-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="9ce07-108">La funzionalità Dispositivo di test opera in combinazione con la funzionalità Aggiornamento dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9ce07-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="9ce07-109">È possibile aggiungere un dispositivo di test nella pagina **Dispositivo di test** e quindi usare il dispositivo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione.</span><span class="sxs-lookup"><span data-stu-id="9ce07-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="9ce07-110">È possibile testare un dispositivo a livello globale (in tutto l'ambiente) o all'interno di un singolo sito.</span><span class="sxs-lookup"><span data-stu-id="9ce07-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="9ce07-111">Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie.</span><span class="sxs-lookup"><span data-stu-id="9ce07-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="9ce07-112">Quando si aggiunge un dispositivo, quest'ultimo viene visualizzato nell'elenco nella pagina **dispositivo di test** del pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ce07-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="9ce07-113">Attività eseguibili</span><span class="sxs-lookup"><span data-stu-id="9ce07-113">Tasks you can perform</span></span>

<span data-ttu-id="9ce07-114">Nella pagina **Nuovo dispositivo di test** o **Modifica dispositivo di test** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ce07-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="9ce07-115">Aggiungere un nuovo dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="9ce07-115">Add a new test device.</span></span>

- <span data-ttu-id="9ce07-116">Modificare le proprietà di un dispositivo di test esistente.</span><span class="sxs-lookup"><span data-stu-id="9ce07-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9ce07-117">Riferimento all'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="9ce07-117">UI Reference</span></span>

<span data-ttu-id="9ce07-118">Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="9ce07-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="9ce07-119">**Ambito** Identifica l'ambito (globale o sito) del dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="9ce07-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="9ce07-120">**Nome** È possibile aggiungere o modificare il nome del dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="9ce07-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="9ce07-121">**Nome dispositivo** È possibile aggiungere o modificare il nome del dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="9ce07-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="9ce07-122">**Tipo di identificatore** È possibile selezionare il metodo da utilizzare per identificare il dispositivo selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ce07-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="9ce07-123">**Indirizzo MAC**</span><span class="sxs-lookup"><span data-stu-id="9ce07-123">**MAC address**</span></span>

  - <span data-ttu-id="9ce07-124">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="9ce07-124">**Serial number**</span></span>

- <span data-ttu-id="9ce07-125">**Identificatore univoco** È possibile digitare l'indirizzo MAC o il numero di serie del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9ce07-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="9ce07-126">Per informazioni dettagliate sui dispositivi di test, vedere [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="9ce07-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="9ce07-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ce07-127">See also</span></span>

[<span data-ttu-id="9ce07-128">Dispositivo di test</span><span class="sxs-lookup"><span data-stu-id="9ce07-128">Test Device</span></span>](ms.lync.lscp.ClientDeviceTestMain.md)

[<span data-ttu-id="9ce07-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="9ce07-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="9ce07-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="9ce07-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="9ce07-131">Visualizzare gli aggiornamenti software per i dispositivi nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="9ce07-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
