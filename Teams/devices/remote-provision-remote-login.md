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
ms.openlocfilehash: f39b93a048cee84cf6890d063e272edbef5edb4e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059190"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="23720-103">Provisioning remoto e accesso per i dispositivi Android di Teams</span><span class="sxs-lookup"><span data-stu-id="23720-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="23720-104">Gli amministratori IT possono eseguire il provisioning in remoto e accedere a un dispositivo Android di Teams.</span><span class="sxs-lookup"><span data-stu-id="23720-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="23720-105">Per eseguire il provisioning di un dispositivo in remoto, l'amministratore deve caricare gli ID MAC dei dispositivi di cui viene eseguito il provisioning e creare un codice di verifica.</span><span class="sxs-lookup"><span data-stu-id="23720-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="23720-106">L'intero processo può essere completato in remoto dall'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="23720-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="23720-107">Esaminare i dispositivi supportati</span><span class="sxs-lookup"><span data-stu-id="23720-107">Review the supported devices</span></span>

<span data-ttu-id="23720-108">L'elenco seguente mostra i requisiti del firmware del dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="23720-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="23720-109">Categoria dispositivo</span><span class="sxs-lookup"><span data-stu-id="23720-109">Device category</span></span>|<span data-ttu-id="23720-110">Modello di dispositivo</span><span class="sxs-lookup"><span data-stu-id="23720-110">Device model</span></span>|<span data-ttu-id="23720-111">Versione firmware</span><span class="sxs-lookup"><span data-stu-id="23720-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="23720-112">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="23720-112">Teams phones</span></span>|<span data-ttu-id="23720-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="23720-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="23720-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="23720-114">58.15.0.124</span></span>|
|<span data-ttu-id="23720-115">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="23720-115">Teams phones</span></span>|<span data-ttu-id="23720-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="23720-116">Yealink VP59</span></span>|<span data-ttu-id="23720-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="23720-117">91.15.0.58</span></span>|
|<span data-ttu-id="23720-118">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="23720-118">Teams phones</span></span>|<span data-ttu-id="23720-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="23720-119">Yealink CP960</span></span>|<span data-ttu-id="23720-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="23720-120">73.15.0.117</span></span>|
|<span data-ttu-id="23720-121">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="23720-121">Teams phones</span></span>|<span data-ttu-id="23720-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="23720-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="23720-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="23720-123">122.15.0.36</span></span>|
|<span data-ttu-id="23720-124">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="23720-124">Teams phones</span></span>|<span data-ttu-id="23720-125">Crestron UC-2</span><span class="sxs-lookup"><span data-stu-id="23720-125">Crestron UC-2</span></span>|<span data-ttu-id="23720-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="23720-126">1.0.3.52</span></span>|
|<span data-ttu-id="23720-127">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="23720-127">Teams phones</span></span>|  <span data-ttu-id="23720-128">Poly Trio C60</span><span class="sxs-lookup"><span data-stu-id="23720-128">Poly Trio C60</span></span>|  <span data-ttu-id="23720-129">7.0.2.1071</span><span class="sxs-lookup"><span data-stu-id="23720-129">7.0.2.1071</span></span>|
|<span data-ttu-id="23720-130">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="23720-130">Teams phones</span></span>|  <span data-ttu-id="23720-131">CCX400/CCX500/CCX600</span><span class="sxs-lookup"><span data-stu-id="23720-131">CCX400/CCX500/CCX600</span></span>    |<span data-ttu-id="23720-132">7.0.2.1072</span><span class="sxs-lookup"><span data-stu-id="23720-132">7.0.2.1072</span></span>|
|<span data-ttu-id="23720-133">Telefoni di Teams</span><span class="sxs-lookup"><span data-stu-id="23720-133">Teams phones</span></span>|  <span data-ttu-id="23720-134">Codici audio C448HD/C450HD/C470HD</span><span class="sxs-lookup"><span data-stu-id="23720-134">Audio Codes C448HD/C450HD/C470HD</span></span>|   <span data-ttu-id="23720-135">1.10.120</span><span class="sxs-lookup"><span data-stu-id="23720-135">1.10.120</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="23720-136">Aggiungere un indirizzo MAC del dispositivo</span><span class="sxs-lookup"><span data-stu-id="23720-136">Add a device MAC address</span></span>

<span data-ttu-id="23720-137">Completare la procedura seguente per eseguire il provisioning di un nuovo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23720-137">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="23720-138">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="23720-138">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="23720-139">Espandere **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="23720-139">Expand **Devices**.</span></span>
3. <span data-ttu-id="23720-140">Selezionare **Provisioning nuovo dispositivo** nella **scheda** Azioni.</span><span class="sxs-lookup"><span data-stu-id="23720-140">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="23720-141">Nella finestra **Provisioning nuovi dispositivi** è possibile aggiungere manualmente l'indirizzo MAC o caricare un file.</span><span class="sxs-lookup"><span data-stu-id="23720-141">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="23720-142">Aggiungere manualmente un indirizzo MAC del dispositivo</span><span class="sxs-lookup"><span data-stu-id="23720-142">Manually add a device MAC address</span></span>

1. <span data-ttu-id="23720-143">Nella scheda **In attesa di attivazione** selezionare Aggiungi ID **MAC.**</span><span class="sxs-lookup"><span data-stu-id="23720-143">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![aggiungere manualmente un indirizzo Mac del dispositivo](../media/remote-provision-6.png)

1. <span data-ttu-id="23720-145">Immettere l'ID MAC.</span><span class="sxs-lookup"><span data-stu-id="23720-145">Enter the MAC ID.</span></span>
1. <span data-ttu-id="23720-146">Immettere una posizione che consente ai tecnici di identificare la posizione in cui installare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="23720-146">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="23720-147">Al **termine, selezionare** Applica.</span><span class="sxs-lookup"><span data-stu-id="23720-147">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="23720-148">Caricare un file per aggiungere un indirizzo MAC del dispositivo</span><span class="sxs-lookup"><span data-stu-id="23720-148">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="23720-149">Nella scheda **In attesa di attivazione** selezionare Carica ID **MAC.**</span><span class="sxs-lookup"><span data-stu-id="23720-149">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="23720-150">Scaricare il modello di file.</span><span class="sxs-lookup"><span data-stu-id="23720-150">Download the file template.</span></span>
3. <span data-ttu-id="23720-151">Immettere l'ID MAC e il percorso e quindi salvare il file.</span><span class="sxs-lookup"><span data-stu-id="23720-151">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="23720-152">**Selezionare file** e quindi **carica**.</span><span class="sxs-lookup"><span data-stu-id="23720-152">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="23720-153">Generare un codice di verifica</span><span class="sxs-lookup"><span data-stu-id="23720-153">Generate a verification code</span></span>

<span data-ttu-id="23720-154">È necessario un codice di verifica per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="23720-154">You need a verification code for the devices.</span></span> <span data-ttu-id="23720-155">Il codice di verifica viene generato in blocco o a livello di dispositivo ed è valido per 24 ore.</span><span class="sxs-lookup"><span data-stu-id="23720-155">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="23720-156">Nella scheda **In attesa di attivazione** selezionare un ID MAC esistente.</span><span class="sxs-lookup"><span data-stu-id="23720-156">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="23720-157">Viene creata una password per l'indirizzo MAC e visualizzata nella **colonna Codice di** verifica.</span><span class="sxs-lookup"><span data-stu-id="23720-157">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="23720-158">Fornire l'elenco di ID MAC e codici di verifica ai tecnici del campo.</span><span class="sxs-lookup"><span data-stu-id="23720-158">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="23720-159">È possibile esportare i dettagli direttamente in un file e condividerlo con il tecnico che sta eseguendo il lavoro di installazione effettivo.</span><span class="sxs-lookup"><span data-stu-id="23720-159">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="23720-160">Eseguire il provisioning del dispositivo</span><span class="sxs-lookup"><span data-stu-id="23720-160">Provision the device</span></span>

<span data-ttu-id="23720-161">Quando il dispositivo è acceso e connesso alla rete, il tecnico esegue il provisioning del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23720-161">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="23720-162">Questi passaggi vengono completati nel dispositivo Teams.</span><span class="sxs-lookup"><span data-stu-id="23720-162">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="23720-163">Il tecnico seleziona **Provisioning dispositivo** in **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="23720-163">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![Opzione Effettua il provisioning di un nuovo dispositivo dalla scheda Azioni](../media/provision-device1.png)
  
2. <span data-ttu-id="23720-165">Il tecnico immette il codice di verifica specifico del dispositivo nel campo di input fornito.</span><span class="sxs-lookup"><span data-stu-id="23720-165">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![Eseguire il provisioning della verifica del nuovo dispositivo](../media/provision-device-verification1.png)

   <span data-ttu-id="23720-167">Dopo il provisioning del dispositivo, il nome del tenant viene visualizzato nella pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="23720-167">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![Nome tenant nella pagina di accesso](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="23720-169">Accedere in remoto</span><span class="sxs-lookup"><span data-stu-id="23720-169">Sign in remotely</span></span>

<span data-ttu-id="23720-170">Il dispositivo di cui è stato eseguito il provisioning viene visualizzato nella **scheda In** attesa di accesso. Avviare il processo di accesso remoto selezionando il singolo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23720-170">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="23720-171">Selezionare un dispositivo nella scheda In attesa **di** accesso.</span><span class="sxs-lookup"><span data-stu-id="23720-171">Select a device from the **Awaiting sign in** tab.</span></span>

   ![Finestra con un elenco di dispositivi pronti per l'accesso.](../media/remote-device1.png)

2. <span data-ttu-id="23720-173">Seguire le istruzioni in **Accedere a un utente** e quindi selezionare **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="23720-173">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![Finestra Accedi a un utente per un singolo dispositivo](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="23720-175">Articolo correlato</span><span class="sxs-lookup"><span data-stu-id="23720-175">Related article</span></span>

- [<span data-ttu-id="23720-176">Gestire i dispositivi in Teams</span><span class="sxs-lookup"><span data-stu-id="23720-176">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="23720-177">Aggiornare i dispositivi di Teams in remoto</span><span class="sxs-lookup"><span data-stu-id="23720-177">Update Teams devices remotely</span></span>](remote-update.md)
