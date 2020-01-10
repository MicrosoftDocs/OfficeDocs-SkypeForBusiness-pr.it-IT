---
title: Predisporre l'appliance di Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Informazioni su come preparare l'accessorio Cloud Connector per la distribuzione e l'uso con il sistema telefonico in Office 365 (cloud PBX).
ms.openlocfilehash: 779cb53dd19d627d8864da65e3e41f5d6dabee99
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001946"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="8c029-103">Predisporre l'appliance di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="8c029-103">Prepare your Cloud Connector appliance</span></span>

<span data-ttu-id="8c029-104">Informazioni su come preparare l'accessorio Cloud Connector per la distribuzione e l'uso con il sistema telefonico in Office 365 (cloud PBX).</span><span class="sxs-lookup"><span data-stu-id="8c029-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>

<span data-ttu-id="8c029-105">Questa sezione descrive come ottenere i file di installazione di Skype for Business Cloud Connector Edition, installare il software Cloud Connector e preparare l'appliance per il Cloud Connector per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8c029-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="8c029-106">Dopo aver completato tutti i passaggi di questa sezione, si sarà pronti per distribuire il connettore Cloud per un singolo sito o più siti.</span><span class="sxs-lookup"><span data-stu-id="8c029-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="8c029-107">Se si dispone di una distribuzione di Cloud Connector esistente e non è stato ancora eseguito l'aggiornamento a Cloud Connector versione 2,1, vedere [eseguire l'aggiornamento a una nuova versione di Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8c029-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8c029-108">Microsoft supporta la versione corrente di Cloud Connector Edition, versione 2,1.</span><span class="sxs-lookup"><span data-stu-id="8c029-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="8c029-109">Se è stato configurato l'aggiornamento automatico, il Cloud Connector verrà aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8c029-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="8c029-110">Se è stato configurato l'aggiornamento manuale, sarà necessario eseguire l'aggiornamento alla versione 2,1 entro 60 giorni dalla relativa versione.</span><span class="sxs-lookup"><span data-stu-id="8c029-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="8c029-111">Microsoft sosterrà la versione precedente per 60 giorni dopo il rilascio di 2,1 per consentire il tempo necessario per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="8c029-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="8c029-112">Per Cloud Connector versione 2,1 e successive, l'accessorio host deve avere .NET Framework 4.6.1 o versioni successive installate.</span><span class="sxs-lookup"><span data-stu-id="8c029-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8c029-113">Per la distribuzione corretta, quando si eseguono i cmdlet per configurare Skype for Business Cloud Connector Edition, usare sempre la stessa sessione di console di quella avviata.</span><span class="sxs-lookup"><span data-stu-id="8c029-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="8c029-114">Evitare di passare a sessioni diverse durante la distribuzione e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8c029-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="8c029-115">Ci sono alcuni passaggi da eseguire solo per il primo appliance della distribuzione: creare una condivisione per la directory del sito, scaricare i bit e preparare un file VHDX (Virtual Hard disk) dall'immagine ISO di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8c029-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="8c029-116">Scaricare il programma di installazione di Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="8c029-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="8c029-117">Nel server host in cui verrà eseguita la VM Connector cloud, scaricare i file di installazione [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller):.</span><span class="sxs-lookup"><span data-stu-id="8c029-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="8c029-118">Il server host deve essere in grado di accedere a Internet durante l'installazione di Cloud Connector perché vengono scaricati altri file durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="8c029-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="8c029-119">Eseguire il programma di installazione e accettare i valori predefiniti durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="8c029-119">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="8c029-120">Verificare che l'installazione sia stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8c029-120">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="8c029-121">Verificare l'installazione e configurare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="8c029-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="8c029-122">Aprire una console di PowerShell come amministratore e verificare che i cmdlet Skype for Business Cloud Connector Edition siano disponibili con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8c029-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="8c029-123">Il comando deve restituire un elenco di cmdlet per Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="8c029-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="8c029-124">I file VHD, SfBBits e VersionInfo verranno archiviati nella **directory del sito**.</span><span class="sxs-lookup"><span data-stu-id="8c029-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="8c029-125">È possibile trovare la posizione della **directory del sito** con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8c029-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="8c029-126">Il comando deve restituire una posizione nel file System.</span><span class="sxs-lookup"><span data-stu-id="8c029-126">The command should return a location in your file system.</span></span> <span data-ttu-id="8c029-127">La posizione può essere una cartella locale o una condivisione file.</span><span class="sxs-lookup"><span data-stu-id="8c029-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="8c029-128">Il percorso predefinito della **directory del sito** è:%UserProfile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="8c029-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="8c029-129">La posizione predefinita deve essere modificata in una condivisione file nel primo appliance creato in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="8c029-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="8c029-130">La posizione selezionata deve essere:</span><span class="sxs-lookup"><span data-stu-id="8c029-130">The location you select must be:</span></span>

   - <span data-ttu-id="8c029-131">Creato nel primo appliance creato in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="8c029-131">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="8c029-132">Una cartella condivisa accessibile dagli altri server host nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="8c029-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="8c029-133">Per impostare la **directory del sito** su una posizione diversa da quella predefinita, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8c029-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="8c029-134">Se si sta distribuendo la disponibilità elevata (HA) per il sito, assicurarsi di eseguire il cmdlet per impostare la **directory del sito** nella stessa posizione in ogni server host all'interno del sito.</span><span class="sxs-lookup"><span data-stu-id="8c029-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="8c029-135">Quando si accede e si distribuisce ogni appliance nel sito, verificare che l'account di accesso corrente disponga dell'accesso corretto alla **directory del sito**.</span><span class="sxs-lookup"><span data-stu-id="8c029-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="8c029-136">La **directory appliance** è la directory radice locale di lavoro per Skype for Business Cloud Connector Edition e la posizione in cui vengono salvati i certificati, le istanze e i registri esterni.</span><span class="sxs-lookup"><span data-stu-id="8c029-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="8c029-137">Il percorso predefinito è:%USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="8c029-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="8c029-138">Per trovare la posizione della **directory appliance**, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8c029-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="8c029-139">Per impostare la **directory appliance** su una posizione diversa da quella predefinita, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8c029-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="8c029-140">La directory appliance deve essere impostata su una cartella locale nell'appliance.</span><span class="sxs-lookup"><span data-stu-id="8c029-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="8c029-141">Devi impostare la **directory appliance** solo prima di avviare la distribuzione di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="8c029-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="8c029-142">Se viene modificata dopo la distribuzione, sarà necessario ridistribuire il server host.</span><span class="sxs-lookup"><span data-stu-id="8c029-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8c029-143">Il percorso della **directory appliance** non deve contenere spazi.</span><span class="sxs-lookup"><span data-stu-id="8c029-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="8c029-144">Impostare il percorso per il certificato perimetrale esterno</span><span class="sxs-lookup"><span data-stu-id="8c029-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="8c029-145">Eseguire il cmdlet seguente per impostare il percorso, incluso il nome del file, sul certificato perimetrale esterno.</span><span class="sxs-lookup"><span data-stu-id="8c029-145">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="8c029-146">Ad esempio: C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="8c029-146">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="8c029-147">Il certificato deve contenere chiavi private.</span><span class="sxs-lookup"><span data-stu-id="8c029-147">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="8c029-148">Tieni presente che il parametro-target è specifico delle versioni 1.4.2 e successive.</span><span class="sxs-lookup"><span data-stu-id="8c029-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="8c029-149">Specificare il percorso completo del certificato esterno, incluso il nome del file.</span><span class="sxs-lookup"><span data-stu-id="8c029-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="8c029-150">Il certificato può essere archiviato localmente o in una condivisione file.</span><span class="sxs-lookup"><span data-stu-id="8c029-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="8c029-151">Se il certificato è archiviato in una cartella condivisa, la cartella condivisa deve essere creata nel primo dispositivo di ogni sito e deve essere accessibile da altri dispositivi appartenenti allo stesso sito.</span><span class="sxs-lookup"><span data-stu-id="8c029-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="8c029-152">Questo cmdlet copia il certificato esterno nella **directory appliance**.</span><span class="sxs-lookup"><span data-stu-id="8c029-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8c029-153">**Se è stato aggiornato a Cloud Connector versione 1.4.2 o successiva**, verificare che il certificato esterno preparato contenga le chiavi private e la catena di certificati completa, incluso il certificato della CA radice e i certificati intermedi della CA.</span><span class="sxs-lookup"><span data-stu-id="8c029-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="8c029-154">**Se non è stato ancora aggiornato a Cloud Connector versione 1.4.2**, verificare che il certificato esterno preparato contenga chiavi private.</span><span class="sxs-lookup"><span data-stu-id="8c029-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="8c029-155">Questo certificato esterno deve essere emesso da un'autorità di certificazione considerata attendibile da Windows per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8c029-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="8c029-156">Impostare il percorso per il certificato del gateway PSTN/SBC esterno</span><span class="sxs-lookup"><span data-stu-id="8c029-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="8c029-157">Se si usa TLS tra il Mediation Server e il gateway/SBC PSTN, eseguire il cmdlet seguente per impostare il percorso, incluso il nome del file, sul certificato del gateway.</span><span class="sxs-lookup"><span data-stu-id="8c029-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="8c029-158">Ad esempio: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="8c029-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="8c029-159">Il certificato deve contenere la CA radice e la catena intermedia per il certificato assegnato al gateway:</span><span class="sxs-lookup"><span data-stu-id="8c029-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="8c029-160">Tieni presente che il parametro-target è specifico delle versioni 1.4.2 e successive.</span><span class="sxs-lookup"><span data-stu-id="8c029-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="8c029-161">Creare switch virtuali in gestione Hyper-V</span><span class="sxs-lookup"><span data-stu-id="8c029-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="8c029-162">Aprire **Hyper-V Manager** > **Virtual Switch Manager**e selezionare **nuovo Virtual Switch Manager**.</span><span class="sxs-lookup"><span data-stu-id="8c029-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="8c029-163">Creare uno switch virtuale esterno e associarlo alla scheda di rete fisica connessa al dominio di rete interno:</span><span class="sxs-lookup"><span data-stu-id="8c029-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="8c029-164">Selezionare **Consenti sistema operativo di gestione per condividere questa scheda di rete** per questo switch virtuale.</span><span class="sxs-lookup"><span data-stu-id="8c029-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="8c029-165">Creare un interruttore virtuale esterno e associarlo alla scheda di rete fisica che viene instradata a Internet:</span><span class="sxs-lookup"><span data-stu-id="8c029-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="8c029-166">Deselezionare Consenti il **sistema operativo di gestione per condividere questa scheda di rete** per questo switch virtuale.</span><span class="sxs-lookup"><span data-stu-id="8c029-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="8c029-167">Impostare il nome dell'opzione che connette la rete perimetrale al dominio di rete interno **SFB CCE corpnet**.</span><span class="sxs-lookup"><span data-stu-id="8c029-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="8c029-168">Impostare il nome dell'opzione che connette la rete perimetrale a Internet **SFB CCE Internet switch**.</span><span class="sxs-lookup"><span data-stu-id="8c029-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="8c029-169">Aggiornare il file di configurazione CloudConnector. ini</span><span class="sxs-lookup"><span data-stu-id="8c029-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="8c029-170">Preparare il file CloudConnector. ini usando le informazioni raccolte in [determinare i parametri di distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) nell'argomento [piano per Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="8c029-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="8c029-171">Per aggiornare il file, eseguire prima di tutto il cmdlet seguente per ottenere il modello di esempio (CloudConnector. Sample. ini):</span><span class="sxs-lookup"><span data-stu-id="8c029-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="8c029-172">Il modello di esempio è archiviato nella **directory appliance**.</span><span class="sxs-lookup"><span data-stu-id="8c029-172">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="8c029-173">Dopo averla aggiornata con i valori per l'ambiente, salvare il file come CloudConnector. ini nella **directory appliance**.</span><span class="sxs-lookup"><span data-stu-id="8c029-173">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="8c029-174">Puoi eseguire **Get-CcApplianceDirectory** per determinare il percorso della **directory appliance**.</span><span class="sxs-lookup"><span data-stu-id="8c029-174">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="8c029-175">Quando si aggiorna il file ini, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8c029-175">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="8c029-176">Non tutti i valori per il file ini sono discussi in questa sezione, ma solo quelli con una considerazione particolare sono descritti qui.</span><span class="sxs-lookup"><span data-stu-id="8c029-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="8c029-177">Per un elenco completo, vedi la sezione [determinare i parametri di distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) dell'argomento [piano per Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="8c029-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="8c029-178">Per altre informazioni sui valori che devono essere modificati per altri dispositivi o nuovi siti, vedere [sito singolo con elevata disponibilità (ha) rispetto alle distribuzioni multisito](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) nell'argomento [distribuire più siti in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8c029-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="8c029-179">**SiteName:** Il valore predefinito è **Microsoft1**.</span><span class="sxs-lookup"><span data-stu-id="8c029-179">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="8c029-180">È necessario aggiornarlo prima di distribuire Cloud Connector, perché quando si esegue **Register-CcAppliance** per registrare un dispositivo in un sito nuovo o esistente, il cmdlet userà **nomesito** per determinare il sito da registrare.</span><span class="sxs-lookup"><span data-stu-id="8c029-180">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="8c029-181">Se si vuole registrare l'appliance in un nuovo sito, il valore di **nomesito** deve essere univoco e diverso dai siti esistenti.</span><span class="sxs-lookup"><span data-stu-id="8c029-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="8c029-182">Se si vuole registrare l'appliance in un sito esistente, il valore per **siteName** nel file ini deve corrispondere al nome definito nella configurazione del tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c029-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 tenant configuration.</span></span> <span data-ttu-id="8c029-183">Se si sta copiando un file di configurazione da un sito a un altro, assicurarsi di aggiornare di conseguenza il valore per **siteName** per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="8c029-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="8c029-184">**NomeServer:** Il nome del server non deve contenere il nome di dominio e deve essere limitato a 15 caratteri.</span><span class="sxs-lookup"><span data-stu-id="8c029-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="8c029-185">**HardwareType:** Se non si imposta o non si lascia il valore null, verrà usato il valore predefinito **Normal** .</span><span class="sxs-lookup"><span data-stu-id="8c029-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="8c029-186">Usare **Normal** se si prevede di distribuire la versione più grande di Cloud Connector per supportare le chiamate simultanee di 500 per ogni computer host, come descritto in [piano per Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="8c029-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="8c029-187">Usare **Minimum** per una distribuzione più piccola che supporta le chiamate simultanee di 50.</span><span class="sxs-lookup"><span data-stu-id="8c029-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="8c029-188">**Switch virtuali Internet/corpnet/Management:**: aggiungere il nome delle opzioni virtuali create.</span><span class="sxs-lookup"><span data-stu-id="8c029-188">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="8c029-189">Per l'opzione di gestione virtuale, lascia il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8c029-189">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="8c029-190">Lo script di distribuzione creerà l'opzione di gestione virtuale all'inizio della distribuzione ed eliminarla al termine della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8c029-190">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="8c029-191">**ManagementIPPrefix:** ManagementIPPrefix nella sezione rete deve essere una subnet diversa da altri IPs interni.</span><span class="sxs-lookup"><span data-stu-id="8c029-191">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="8c029-192">Ad esempio, come viene visualizzato il valore predefinito, ManagementIPPrefix è 192.168.213.0, mentre AD IPAddress è 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="8c029-192">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="8c029-193">Gli script di distribuzione creano una scheda di rete di gestione in ogni macchina virtuale, assegnano un IP di gestione e la collegano a un interruttore virtuale di gestione.</span><span class="sxs-lookup"><span data-stu-id="8c029-193">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="8c029-194">Questo consente al server host di connettersi e gestire ogni macchina virtuale tramite questa rete di gestione.</span><span class="sxs-lookup"><span data-stu-id="8c029-194">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="8c029-195">L'opzione di gestione virtuale viene eliminata al termine della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8c029-195">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="8c029-196">**Configurazioni specifiche della VM di base:** Le impostazioni in questa sezione devono essere configurate per il cmdlet **Convert-CcIsoToVhdx** .</span><span class="sxs-lookup"><span data-stu-id="8c029-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="8c029-197">Durante la preparazione delle immagini di base della VM, la VM di base verrà connessa allo switch di rete interna.</span><span class="sxs-lookup"><span data-stu-id="8c029-197">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="8c029-198">Le impostazioni seguenti sono critiche per consentire alla VM di accedere a Internet:</span><span class="sxs-lookup"><span data-stu-id="8c029-198">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="8c029-199">Comune BaseVMIP: l'indirizzo IP di corpnet da assegnare alla VM di base.</span><span class="sxs-lookup"><span data-stu-id="8c029-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="8c029-200">Rete CorpnetDefaultGateway: il gateway predefinito da assegnare alla VM di base.</span><span class="sxs-lookup"><span data-stu-id="8c029-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="8c029-201">Rete CorpnetDNSIPAddress: l'indirizzo IP DNS da assegnare alla VM di base.</span><span class="sxs-lookup"><span data-stu-id="8c029-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="8c029-202">Rete WSUSServer: l'indirizzo IP del servizio di aggiornamento di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8c029-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="8c029-203">Rete WSUSStatusServer: l'indirizzo IP del server di stato del servizio Windows Server Update.</span><span class="sxs-lookup"><span data-stu-id="8c029-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="8c029-204">Rete EnableReferSupport: Questo definirà se il supporto SIP REFER è abilitato o disabilitato nella configurazione trunk per il tuo IP/PBX.</span><span class="sxs-lookup"><span data-stu-id="8c029-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="8c029-205">**IPs interno:**</span><span class="sxs-lookup"><span data-stu-id="8c029-205">**Internal IPs:**</span></span>

  - <span data-ttu-id="8c029-206">Verificare che CorpnetIPPrefixLength della subnet mask sia corretto.</span><span class="sxs-lookup"><span data-stu-id="8c029-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="8c029-207">Verificare che non ci siano conflitti IP per questi IPs interni.</span><span class="sxs-lookup"><span data-stu-id="8c029-207">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="8c029-208">**IPs esterni:**</span><span class="sxs-lookup"><span data-stu-id="8c029-208">**External IPs:**</span></span>

  - <span data-ttu-id="8c029-209">Per MR Public IP: specificare ExternalMRIPs per non NAT o ExternalMRPublicIPs per NAT.</span><span class="sxs-lookup"><span data-stu-id="8c029-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="8c029-210">ExternalSIPIPs e ExternalMRIPs possono essere uguali.</span><span class="sxs-lookup"><span data-stu-id="8c029-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="8c029-211">Verificare che InternetIPPrefixLength della subnet mask sia corretto.</span><span class="sxs-lookup"><span data-stu-id="8c029-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="8c029-212">Verificare che non ci siano conflitti IP per questi IPs esterni.</span><span class="sxs-lookup"><span data-stu-id="8c029-212">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="8c029-213">**Gateway**</span><span class="sxs-lookup"><span data-stu-id="8c029-213">**Gateways:**</span></span>

  - <span data-ttu-id="8c029-214">Se si ha un solo gateway, rimuovere la sezione per il gateway secondario.</span><span class="sxs-lookup"><span data-stu-id="8c029-214">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="8c029-215">Se sono presenti più di due gateway, creare altre sezioni copiando e incollando quello esistente e quindi aggiornando il testo.</span><span class="sxs-lookup"><span data-stu-id="8c029-215">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="8c029-216">Verificare che l'indirizzo IP e la porta dei gateway siano corretti.</span><span class="sxs-lookup"><span data-stu-id="8c029-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="8c029-217">Per supportare il livello HA del gateway PSTN, lascia il gateway secondario e Aggiungi eventuali gateway aggiuntivi che userai.</span><span class="sxs-lookup"><span data-stu-id="8c029-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="8c029-218">È possibile copiare e incollare una voce esistente e quindi aggiornarla.</span><span class="sxs-lookup"><span data-stu-id="8c029-218">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="8c029-219">Facoltativamente, puoi aggiornare il valore LocalRoute per limitare i numeri di chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="8c029-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="8c029-220">Scaricare i bit nella directory del sito</span><span class="sxs-lookup"><span data-stu-id="8c029-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="8c029-221">Eseguire il cmdlet seguente per scaricare i file di informazioni sulla versione e i bit nella **directory del sito**:</span><span class="sxs-lookup"><span data-stu-id="8c029-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="8c029-222">È necessario eseguire questo passaggio solo per la prima Appliance.</span><span class="sxs-lookup"><span data-stu-id="8c029-222">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="8c029-223">Preparare il disco virtuale di base (VHDX) dal file ISO scaricato</span><span class="sxs-lookup"><span data-stu-id="8c029-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="8c029-224">Questo passaggio prepara un file VHDX (Virtual Hard disk) dall'immagine ISO di Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="8c029-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="8c029-225">Il VHDX verrà usato per creare macchine virtuali durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8c029-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="8c029-226">Verrà creata una macchina virtuale temporanea (VM di base) e il file ISO verrà installato in Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="8c029-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="8c029-227">Dopo la creazione della VM, verranno installati alcuni componenti necessari e verrà applicato l'ultimo aggiornamento di Windows.</span><span class="sxs-lookup"><span data-stu-id="8c029-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="8c029-228">Alla fine, la VM di base verrà generalizzata (Sysprep) e sarà pulita, lasciando solo il file del disco virtuale generato.</span><span class="sxs-lookup"><span data-stu-id="8c029-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="8c029-229">È necessario eseguire questo passaggio solo per la prima Appliance.</span><span class="sxs-lookup"><span data-stu-id="8c029-229">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="8c029-230">Prima di procedere con questo passaggio, verificare che l'opzione corpnet sia stata creata.</span><span class="sxs-lookup"><span data-stu-id="8c029-230">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="8c029-231">Verificare inoltre che le impostazioni seguenti siano configurate correttamente nel file CloudConnector. ini:</span><span class="sxs-lookup"><span data-stu-id="8c029-231">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="8c029-232">Rete CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="8c029-232">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="8c029-233">Comune BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="8c029-233">[Common]BaseVMIP</span></span>

- <span data-ttu-id="8c029-234">Rete CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="8c029-234">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="8c029-235">Rete CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="8c029-235">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="8c029-236">Rete CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="8c029-236">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="8c029-237">Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per convertire l'immagine ISO in un disco rigido virtuale (VHD):</span><span class="sxs-lookup"><span data-stu-id="8c029-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="8c029-238">Specificare il percorso completo, incluso il nome del file, nell'immagine ISO.</span><span class="sxs-lookup"><span data-stu-id="8c029-238">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="8c029-239">Ad esempio: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="8c029-239">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="8c029-240">Il file VHD creato è archiviato nella cartella \Bits\VHD **directory del sito** .</span><span class="sxs-lookup"><span data-stu-id="8c029-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="8c029-241">Puoi ottenere il percorso della directory del **sito** eseguendo il **Get-CcSiteDirectory**.</span><span class="sxs-lookup"><span data-stu-id="8c029-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c029-242">Per impostazione predefinita, le impostazioni proxy non sono configurate nella VM di base.</span><span class="sxs-lookup"><span data-stu-id="8c029-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="8c029-243">Se è necessario un proxy nell'ambiente di rete per aggiornare la VM tramite Windows Update, è necessario aggiungere il parametro-PauseBeforeUpdate quando si esegue "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="8c029-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="8c029-244">Lo script verrà sospeso prima di Windows Update e si avrà la possibilità di impostare manualmente proxy sulla VM.</span><span class="sxs-lookup"><span data-stu-id="8c029-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="8c029-245">Dopo l'installazione del proxy e la VM può accedere a Internet, è possibile riprendere lo script per completare i passaggi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="8c029-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="8c029-246">Creare VHD per una distribuzione multisito</span><span class="sxs-lookup"><span data-stu-id="8c029-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="8c029-247">Si tratta di un passaggio facoltativo che si applica solo alle distribuzioni multisito.</span><span class="sxs-lookup"><span data-stu-id="8c029-247">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="8c029-248">Se si sta distribuendo una distribuzione multisito, non è necessario convertire la ISO in un VHD per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="8c029-248">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="8c029-249">È possibile copiare il VHDX creato per il primo sito nel server host per un secondo sito.</span><span class="sxs-lookup"><span data-stu-id="8c029-249">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="8c029-250">Copiare il file nella stessa posizione del file (cartella **directory** \Bits\VHD) e con lo stesso nome file nel server host per un altro sito.</span><span class="sxs-lookup"><span data-stu-id="8c029-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="8c029-251">Impostare i criteri di esecuzione di PowerShell su RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="8c029-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="8c029-252">Gli script di PowerShell forniti richiedono che il criterio di esecuzione sia impostato su RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="8c029-252">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="8c029-253">Per visualizzare l'impostazione corrente, aprire una console di PowerShell come amministratore e quindi eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8c029-253">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="8c029-254">Se non è impostato su "RemoteSigned", eseguire il cmdlet seguente per modificarlo:</span><span class="sxs-lookup"><span data-stu-id="8c029-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="8c029-255">Modificare i criteri di gruppo locali nel computer host (versioni 1.4.1 e precedenti)</span><span class="sxs-lookup"><span data-stu-id="8c029-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="8c029-256">Questa attività non è necessaria per le versioni 1.4.2 e successive del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="8c029-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="8c029-257">L'account CceService viene creato durante la distribuzione di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="8c029-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="8c029-258">Esegue il servizio di gestione dei Cloud Connector e richiede l'autorizzazione per disinstallare cloudconnector. msi.</span><span class="sxs-lookup"><span data-stu-id="8c029-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="8c029-259">È necessario modificare l'impostazione di criteri di gruppo nel computer host del Cloud Connector per specificare che il registro di sistema dell'utente non deve essere scaricato quando l'utente si disconnette.</span><span class="sxs-lookup"><span data-stu-id="8c029-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="8c029-260">Eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="8c029-260">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="8c029-261">Per modificare l'impostazione di criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="8c029-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="8c029-262">Aprire l' **Editor criteri di gruppo** eseguendo gpedit. msc.</span><span class="sxs-lookup"><span data-stu-id="8c029-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="8c029-263">In **Editor criteri di gruppo**passare a modelli amministrativi > sistema > UserProfile > non scaricare con forza il registro utenti a fine sessione utente.</span><span class="sxs-lookup"><span data-stu-id="8c029-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="8c029-264">Imposta il valore su **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="8c029-264">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-office-365-tenant"></a><span data-ttu-id="8c029-265">Configurare il tenant di Office 365</span><span class="sxs-lookup"><span data-stu-id="8c029-265">Set up your Office 365 tenant</span></span>

<span data-ttu-id="8c029-266">È necessario un tenant di Office 365 con Skype for business online e il sistema telefonico in Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c029-266">An Office 365 tenant with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="8c029-267">Verificare che il tenant sia configurato e configurato prima di provare a usare Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8c029-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="8c029-268">Alcuni passaggi di configurazione di Office 365 richiedono l'uso di PowerShell remoto tenant (TRP) per configurare il tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c029-268">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 tenant.</span></span> <span data-ttu-id="8c029-269">**Questa operazione deve essere installata nel server host.**</span><span class="sxs-lookup"><span data-stu-id="8c029-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="8c029-270">È possibile scaricare il modulo Skype for business online per PowerShell da: [Skype for business online, modulo di Windows PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="8c029-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="8c029-271">Creare un account di amministratore dedicato di Skype for business per la gestione di Cloud Connector online, ad esempio CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8c029-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="8c029-272">Questo account verrà usato da appliance per aggiungere o rimuovere Appliance, abilitare o disabilitare l'aggiornamento automatico del sistema operativo, abilitare o disabilitare l'aggiornamento automatico binario.</span><span class="sxs-lookup"><span data-stu-id="8c029-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="8c029-273">Impostare la password per l'account in modo che non scada mai per non doverla modificare per il servizio ogni volta che scade.</span><span class="sxs-lookup"><span data-stu-id="8c029-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


