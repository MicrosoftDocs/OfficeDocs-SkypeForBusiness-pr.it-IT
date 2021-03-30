---
title: Provisioning remoto e accesso per i dispositivi Android di Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Scopri come eseguire il provisioning remoto e accedere per i dispositivi Android di Teams
ms.openlocfilehash: 43a025c0cc68fb7f10015d69298f8dd75f9003e8
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410356"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="f6621-103">Provisioning remoto e accesso per i dispositivi Android di Teams</span><span class="sxs-lookup"><span data-stu-id="f6621-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="f6621-104">Gli amministratori IT possono eseguire il provisioning in remoto e accedere a un dispositivo Android di Teams.</span><span class="sxs-lookup"><span data-stu-id="f6621-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="f6621-105">Per eseguire il provisioning di un dispositivo in remoto, l'amministratore deve caricare gli ID MAC dei dispositivi di cui viene eseguito il provisioning e creare un codice di verifica.</span><span class="sxs-lookup"><span data-stu-id="f6621-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="f6621-106">L'intero processo può essere completato in remoto dall'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="f6621-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="f6621-107">Esaminare i dispositivi supportati</span><span class="sxs-lookup"><span data-stu-id="f6621-107">Review the supported devices</span></span>

<span data-ttu-id="f6621-108">L'elenco seguente mostra i requisiti del firmware del dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="f6621-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="f6621-109">Categoria dispositivo</span><span class="sxs-lookup"><span data-stu-id="f6621-109">Device category</span></span>|<span data-ttu-id="f6621-110">Modello di dispositivo</span><span class="sxs-lookup"><span data-stu-id="f6621-110">Device model</span></span>|<span data-ttu-id="f6621-111">Versione firmware</span><span class="sxs-lookup"><span data-stu-id="f6621-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="f6621-112">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="f6621-112">Teams phones</span></span>|<span data-ttu-id="f6621-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="f6621-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="f6621-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="f6621-114">58.15.0.124</span></span>|
|<span data-ttu-id="f6621-115">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="f6621-115">Teams phones</span></span>|<span data-ttu-id="f6621-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="f6621-116">Yealink VP59</span></span>|<span data-ttu-id="f6621-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="f6621-117">91.15.0.58</span></span>|
|<span data-ttu-id="f6621-118">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="f6621-118">Teams phones</span></span>|<span data-ttu-id="f6621-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="f6621-119">Yealink CP960</span></span>|<span data-ttu-id="f6621-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="f6621-120">73.15.0.117</span></span>|
|<span data-ttu-id="f6621-121">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="f6621-121">Teams phones</span></span>|<span data-ttu-id="f6621-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="f6621-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="f6621-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="f6621-123">122.15.0.36</span></span>|
|<span data-ttu-id="f6621-124">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="f6621-124">Teams phones</span></span>|<span data-ttu-id="f6621-125">Crestron UC-2</span><span class="sxs-lookup"><span data-stu-id="f6621-125">Crestron UC-2</span></span>|<span data-ttu-id="f6621-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="f6621-126">1.0.3.52</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="f6621-127">Aggiungere un indirizzo MAC del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f6621-127">Add a device MAC address</span></span>

<span data-ttu-id="f6621-128">Completare la procedura seguente per eseguire il provisioning di un nuovo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f6621-128">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="f6621-129">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="f6621-129">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="f6621-130">Espandere **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="f6621-130">Expand **Devices**.</span></span>
3. <span data-ttu-id="f6621-131">Selezionare **Provisioning nuovo dispositivo** nella **scheda** Azioni.</span><span class="sxs-lookup"><span data-stu-id="f6621-131">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="f6621-132">Nella finestra **Provisioning nuovi dispositivi** è possibile aggiungere manualmente l'indirizzo MAC o caricare un file.</span><span class="sxs-lookup"><span data-stu-id="f6621-132">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="f6621-133">Aggiungere manualmente un indirizzo MAC del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f6621-133">Manually add a device MAC address</span></span>

1. <span data-ttu-id="f6621-134">Nella scheda **In attesa di attivazione** selezionare Aggiungi ID **MAC.**</span><span class="sxs-lookup"><span data-stu-id="f6621-134">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![aggiungere manualmente un indirizzo Mac del dispositivo](../media/remote-provision-6.png)

1. <span data-ttu-id="f6621-136">Immettere l'ID MAC.</span><span class="sxs-lookup"><span data-stu-id="f6621-136">Enter the MAC ID.</span></span>
1. <span data-ttu-id="f6621-137">Immettere una posizione che consente ai tecnici di identificare la posizione in cui installare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f6621-137">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="f6621-138">Al **termine, selezionare** Applica.</span><span class="sxs-lookup"><span data-stu-id="f6621-138">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="f6621-139">Caricare un file per aggiungere un indirizzo MAC del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f6621-139">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="f6621-140">Nella scheda **In attesa di attivazione** selezionare Carica ID **MAC.**</span><span class="sxs-lookup"><span data-stu-id="f6621-140">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="f6621-141">Scaricare il modello di file.</span><span class="sxs-lookup"><span data-stu-id="f6621-141">Download the file template.</span></span>
3. <span data-ttu-id="f6621-142">Immettere l'ID MAC e il percorso e quindi salvare il file.</span><span class="sxs-lookup"><span data-stu-id="f6621-142">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="f6621-143">**Selezionare file** e quindi **carica**.</span><span class="sxs-lookup"><span data-stu-id="f6621-143">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="f6621-144">Generare un codice di verifica</span><span class="sxs-lookup"><span data-stu-id="f6621-144">Generate a verification code</span></span>

<span data-ttu-id="f6621-145">È necessario un codice di verifica per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f6621-145">You need a verification code for the devices.</span></span> <span data-ttu-id="f6621-146">Il codice di verifica viene generato in blocco o a livello di dispositivo ed è valido per 24 ore.</span><span class="sxs-lookup"><span data-stu-id="f6621-146">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="f6621-147">Nella scheda **In attesa di attivazione** selezionare un ID MAC esistente.</span><span class="sxs-lookup"><span data-stu-id="f6621-147">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="f6621-148">Viene creata una password per l'indirizzo MAC e visualizzata nella **colonna Codice di** verifica.</span><span class="sxs-lookup"><span data-stu-id="f6621-148">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="f6621-149">Fornire l'elenco di ID MAC e codici di verifica ai tecnici del campo.</span><span class="sxs-lookup"><span data-stu-id="f6621-149">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="f6621-150">È possibile esportare i dettagli direttamente in un file e condividerlo con il tecnico che sta eseguendo il lavoro di installazione effettivo.</span><span class="sxs-lookup"><span data-stu-id="f6621-150">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="f6621-151">Eseguire il provisioning del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f6621-151">Provision the device</span></span>

<span data-ttu-id="f6621-152">Quando il dispositivo è acceso e connesso alla rete, il tecnico esegue il provisioning del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f6621-152">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="f6621-153">Questi passaggi vengono completati nel dispositivo Teams.</span><span class="sxs-lookup"><span data-stu-id="f6621-153">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="f6621-154">Il tecnico seleziona **Provisioning dispositivo** in **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="f6621-154">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![Opzione Effettua il provisioning di un nuovo dispositivo dalla scheda Azioni](../media/provision-device1.png)
  
2. <span data-ttu-id="f6621-156">Il tecnico immette il codice di verifica specifico del dispositivo nel campo di input fornito.</span><span class="sxs-lookup"><span data-stu-id="f6621-156">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![Eseguire il provisioning della verifica del nuovo dispositivo](../media/provision-device-verification1.png)

   <span data-ttu-id="f6621-158">Dopo il provisioning del dispositivo, il nome del tenant viene visualizzato nella pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="f6621-158">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![Nome tenant nella pagina di accesso](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="f6621-160">Accedere in remoto</span><span class="sxs-lookup"><span data-stu-id="f6621-160">Sign in remotely</span></span>

<span data-ttu-id="f6621-161">Il dispositivo di cui è stato eseguito il provisioning viene visualizzato nella **scheda In** attesa di accesso. Avviare il processo di accesso remoto selezionando il singolo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f6621-161">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="f6621-162">Selezionare un dispositivo nella scheda In attesa **di** accesso.</span><span class="sxs-lookup"><span data-stu-id="f6621-162">Select a device from the **Awaiting sign in** tab.</span></span>

   ![Finestra con un elenco di dispositivi pronti per l'accesso.](../media/remote-device1.png)

2. <span data-ttu-id="f6621-164">Seguire le istruzioni in **Accedere a un utente** e quindi selezionare **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="f6621-164">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![Finestra Accedi a un utente per un singolo dispositivo](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="f6621-166">Articolo correlato</span><span class="sxs-lookup"><span data-stu-id="f6621-166">Related article</span></span>

- [<span data-ttu-id="f6621-167">Gestire i dispositivi in Teams</span><span class="sxs-lookup"><span data-stu-id="f6621-167">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="f6621-168">Aggiornare i dispositivi di Teams in remoto</span><span class="sxs-lookup"><span data-stu-id="f6621-168">Update Teams devices remotely</span></span>](remote-update.md)
