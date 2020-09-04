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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Informazioni su come preparare l'accessorio Cloud Connector per la distribuzione e l'utilizzo con il sistema telefonico (cloud PBX).
ms.openlocfilehash: 74c4885a25b4176f4d5eb3ac27926bd9528387c6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358942"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="fb3da-103">Predisporre l'appliance di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="fb3da-103">Prepare your Cloud Connector appliance</span></span>

> [!Important]
> <span data-ttu-id="fb3da-104">Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="fb3da-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="fb3da-105">Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="fb3da-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="fb3da-106">Informazioni su come preparare l'accessorio Cloud Connector per la distribuzione e l'utilizzo con il sistema telefonico (cloud PBX).</span><span class="sxs-lookup"><span data-stu-id="fb3da-106">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System (Cloud PBX).</span></span>

<span data-ttu-id="fb3da-107">In questa sezione viene descritto come ottenere i file di installazione di Skype for Business Cloud Connector Edition, installare il software Cloud Connector e preparare l'accessorio Cloud Connector per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb3da-107">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="fb3da-108">Dopo aver completato tutti i passaggi illustrati in questa sezione, sarà possibile distribuire il connettore Cloud per un singolo sito o più siti.</span><span class="sxs-lookup"><span data-stu-id="fb3da-108">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="fb3da-109">Se si dispone di una distribuzione del connettore cloud esistente e non è stato ancora eseguito l'aggiornamento a Cloud Connector versione 2,1, vedere [upgrade to a New Version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="fb3da-109">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fb3da-110">Microsoft supporta la versione corrente di Cloud Connector Edition, versione 2,1.</span><span class="sxs-lookup"><span data-stu-id="fb3da-110">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="fb3da-111">Se è stato configurato l'aggiornamento automatico, il connettore Cloud verrà aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fb3da-111">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="fb3da-112">Se è stata configurata l'aggiornamento manuale, è necessario eseguire l'aggiornamento alla versione 2,1 entro 60 giorni dalla relativa versione.</span><span class="sxs-lookup"><span data-stu-id="fb3da-112">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="fb3da-113">Microsoft supporterà la versione precedente per 60 giorni dopo il rilascio di 2,1 per consentire il tempo necessario per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="fb3da-113">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="fb3da-114">Per il connettore Cloud versione 2,1 e versioni successive, è necessario che l'accessorio host disponga di .NET Framework 4.6.1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="fb3da-114">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="fb3da-115">Per una distribuzione corretta, quando si eseguono i cmdlet per configurare Skype for Business Cloud Connector Edition, utilizzare sempre la stessa sessione di console di quella in cui è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="fb3da-115">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="fb3da-116">Evitare di passare a sessioni diverse durante la distribuzione e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="fb3da-116">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="fb3da-117">Esistono alcuni passaggi da eseguire solo per il primo dispositivo nella distribuzione: creazione di una condivisione per la directory del sito, download dei bit e preparazione di un file del disco rigido virtuale (VHDX) dall'immagine ISO di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="fb3da-117">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="fb3da-118">Scaricare il programma di installazione di Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="fb3da-118">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="fb3da-119">Nel server host in cui verranno eseguite le macchine virtuali dei connettori cloud, scaricare i file di installazione: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="fb3da-119">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="fb3da-120">Il server host deve essere in grado di accedere a Internet durante l'installazione del connettore cloud perché sono stati scaricati ulteriori file durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="fb3da-120">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="fb3da-121">Eseguire il programma di installazione e accettare i valori predefiniti durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="fb3da-121">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="fb3da-122">Verificare che l'installazione sia stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="fb3da-122">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="fb3da-123">Verifica dell'installazione e della configurazione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="fb3da-123">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="fb3da-124">Aprire una console di PowerShell come amministratore e verificare che i cmdlet di Skype for Business Cloud Connector Edition siano disponibili utilizzando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="fb3da-124">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="fb3da-125">Il comando deve restituire un elenco di cmdlet per Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="fb3da-125">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="fb3da-126">I file VHD, SfBBits e VersionInfo verranno archiviati nella **directory del sito**.</span><span class="sxs-lookup"><span data-stu-id="fb3da-126">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="fb3da-127">È possibile trovare il percorso della **directory del sito** con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="fb3da-127">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="fb3da-128">Il comando deve restituire una posizione nel file System.</span><span class="sxs-lookup"><span data-stu-id="fb3da-128">The command should return a location in your file system.</span></span> <span data-ttu-id="fb3da-129">Il percorso può essere una cartella locale o una condivisione file.</span><span class="sxs-lookup"><span data-stu-id="fb3da-129">The location can be a local folder or a file share.</span></span> <span data-ttu-id="fb3da-130">Il percorso predefinito della **directory del sito** è:%UserProfile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="fb3da-130">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="fb3da-131">Il percorso predefinito deve essere modificato in una condivisione file sul primo dispositivo creato in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="fb3da-131">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="fb3da-132">Il percorso selezionato deve essere:</span><span class="sxs-lookup"><span data-stu-id="fb3da-132">The location you select must be:</span></span>

   - <span data-ttu-id="fb3da-133">Creato nel primo dispositivo creato in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="fb3da-133">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="fb3da-134">Una cartella condivisa accessibile dagli altri server host nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="fb3da-134">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="fb3da-135">Per impostare la **directory del sito** su un percorso diverso da quello predefinito, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="fb3da-135">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="fb3da-136">Se si sta distribuendo disponibilità elevata (HA) per il sito, assicurarsi di eseguire il cmdlet per impostare la **directory del sito** nello stesso percorso su ogni server host all'interno del sito.</span><span class="sxs-lookup"><span data-stu-id="fb3da-136">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="fb3da-137">Quando si esegue l'accesso e si distribuisce ogni accessorio nel sito, verificare che l'account di accesso corrente disponga del diritto di accedere alla **directory del sito**.</span><span class="sxs-lookup"><span data-stu-id="fb3da-137">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="fb3da-138">La **directory appliance** è la directory radice di lavoro locale per Skype for Business Cloud Connector Edition e il percorso in cui vengono salvati i certificati esterni, le istanze e i registri.</span><span class="sxs-lookup"><span data-stu-id="fb3da-138">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="fb3da-139">Il percorso predefinito è:%USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="fb3da-139">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="fb3da-140">Per trovare il percorso della **directory degli elettrodomestici**, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="fb3da-140">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="fb3da-141">Per impostare la **directory degli elettrodomestici** su una posizione diversa da quella predefinita, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="fb3da-141">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="fb3da-142">La directory appliance deve essere impostata su una cartella locale dell'accessorio.</span><span class="sxs-lookup"><span data-stu-id="fb3da-142">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="fb3da-143">È consigliabile impostare la **directory appliance** solo prima di avviare la distribuzione di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="fb3da-143">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="fb3da-144">Se viene modificato dopo la distribuzione, sarà necessario ridistribuire il server host.</span><span class="sxs-lookup"><span data-stu-id="fb3da-144">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fb3da-145">Il percorso della **directory appliance** non deve contenere spazi.</span><span class="sxs-lookup"><span data-stu-id="fb3da-145">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="fb3da-146">Impostare il percorso per il certificato perimetrale esterno</span><span class="sxs-lookup"><span data-stu-id="fb3da-146">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="fb3da-147">Eseguire il cmdlet seguente per impostare il percorso, incluso il nome del file, sul certificato del perimetro esterno.</span><span class="sxs-lookup"><span data-stu-id="fb3da-147">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="fb3da-148">Ad esempio: C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="fb3da-148">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="fb3da-149">Il certificato deve contenere chiavi private.</span><span class="sxs-lookup"><span data-stu-id="fb3da-149">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="fb3da-150">Si noti che il parametro-target è specifico per le versioni 1.4.2 e successive.</span><span class="sxs-lookup"><span data-stu-id="fb3da-150">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="fb3da-151">Specificare il percorso completo del certificato esterno, incluso il nome del file.</span><span class="sxs-lookup"><span data-stu-id="fb3da-151">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="fb3da-152">Il certificato può essere archiviato localmente o in una condivisione file.</span><span class="sxs-lookup"><span data-stu-id="fb3da-152">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="fb3da-153">Se il certificato è archiviato in una cartella condivisa, è necessario creare la cartella condivisa sul primo dispositivo di ogni sito e deve essere accessibile da altri dispositivi che appartengono allo stesso sito.</span><span class="sxs-lookup"><span data-stu-id="fb3da-153">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="fb3da-154">Questo cmdlet copia il certificato esterno nella **directory appliance**.</span><span class="sxs-lookup"><span data-stu-id="fb3da-154">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fb3da-155">**Se è stato aggiornato a Cloud Connector versione 1.4.2 o versioni successive**, verificare che il certificato esterno preparato contenga chiavi private e la catena di certificati completa, inclusi il certificato della CA radice e i certificati di CA intermedi.</span><span class="sxs-lookup"><span data-stu-id="fb3da-155">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="fb3da-156">**Se non è stato ancora aggiornato a Cloud Connector versione 1.4.2**, verificare che il certificato esterno preparato contenga chiavi private.</span><span class="sxs-lookup"><span data-stu-id="fb3da-156">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="fb3da-157">Questo certificato esterno deve essere emesso da un'autorità di certificazione considerata attendibile da Windows per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fb3da-157">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="fb3da-158">Impostare il percorso per il gateway PSTN esterno/certificato SBC</span><span class="sxs-lookup"><span data-stu-id="fb3da-158">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="fb3da-159">Se si utilizza TLS tra il Mediation Server e il gateway/SBC PSTN, eseguire il seguente cmdlet per impostare il percorso, incluso il nome del file, sul certificato del gateway.</span><span class="sxs-lookup"><span data-stu-id="fb3da-159">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="fb3da-160">Ad esempio: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="fb3da-160">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="fb3da-161">Il certificato deve contenere la CA radice e la catena intermedia per il certificato assegnato al gateway:</span><span class="sxs-lookup"><span data-stu-id="fb3da-161">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="fb3da-162">Si noti che il parametro-target è specifico per le versioni 1.4.2 e successive.</span><span class="sxs-lookup"><span data-stu-id="fb3da-162">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="fb3da-163">Creare switch virtuali in gestione di Hyper-V</span><span class="sxs-lookup"><span data-stu-id="fb3da-163">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="fb3da-164">Aprire gestione switch virtuale di **Hyper-V Manager**  >  **Virtual Switch Manager**e selezionare **nuovo Virtual Switch Manager**.</span><span class="sxs-lookup"><span data-stu-id="fb3da-164">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="fb3da-165">Creare un'opzione virtuale esterna e associarla alla scheda di rete fisica connessa al dominio di rete interno:</span><span class="sxs-lookup"><span data-stu-id="fb3da-165">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="fb3da-166">Selezionare **Consenti sistema operativo di gestione per condividere questa scheda di rete** per questo switch virtuale.</span><span class="sxs-lookup"><span data-stu-id="fb3da-166">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="fb3da-167">Creare un'opzione virtuale esterna e associarla alla scheda di rete fisica che viene instradata a Internet:</span><span class="sxs-lookup"><span data-stu-id="fb3da-167">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="fb3da-168">Deselezionare **Consenti al sistema operativo di gestione di condividere questa scheda di rete** per questo switch virtuale.</span><span class="sxs-lookup"><span data-stu-id="fb3da-168">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="fb3da-169">Impostare il nome dell'opzione che connette la rete perimetrale all'opzione del dominio di rete **questo CCE corpnet**.</span><span class="sxs-lookup"><span data-stu-id="fb3da-169">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="fb3da-170">Impostare il nome dell'opzione che connette la rete perimetrale all'opzione Internet **questo CCE Internet**.</span><span class="sxs-lookup"><span data-stu-id="fb3da-170">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="fb3da-171">Aggiornare il file di configurazione di CloudConnector.ini</span><span class="sxs-lookup"><span data-stu-id="fb3da-171">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="fb3da-172">Preparare il file CloudConnector.ini utilizzando le informazioni raccolte in [Determine Deployment Parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) nell'argomento [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="fb3da-172">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="fb3da-173">Per aggiornare il file, eseguire prima il cmdlet seguente per ottenere il modello di esempio (CloudConnector.Sample.ini):</span><span class="sxs-lookup"><span data-stu-id="fb3da-173">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="fb3da-174">Il modello di esempio è archiviato nella **directory appliance**.</span><span class="sxs-lookup"><span data-stu-id="fb3da-174">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="fb3da-175">Dopo averlo aggiornato con i valori dell'ambiente, salvare il file come CloudConnector.ini nella **directory appliance**.</span><span class="sxs-lookup"><span data-stu-id="fb3da-175">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="fb3da-176">È possibile eseguire **Get-CcApplianceDirectory** per determinare il percorso della **directory degli elettrodomestici**.</span><span class="sxs-lookup"><span data-stu-id="fb3da-176">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="fb3da-177">Quando si aggiorna il file ini, prendere in considerazione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fb3da-177">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="fb3da-178">Non tutti i valori per il file ini sono descritti in questa sezione, ma solo quelli con una considerazione particolare sono descritti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="fb3da-178">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="fb3da-179">Per un elenco completo, vedere la sezione [Determine Deployment Parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) dell'argomento [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .</span><span class="sxs-lookup"><span data-stu-id="fb3da-179">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="fb3da-180">Per ulteriori informazioni sui valori che devono essere modificati per altri dispositivi o nuovi siti, vedere [Single site with High Availability (ha) rispetto alle distribuzioni multisito](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) nell'argomento [deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="fb3da-180">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="fb3da-181">**SiteName:** Il valore predefinito è **site1**.</span><span class="sxs-lookup"><span data-stu-id="fb3da-181">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="fb3da-182">È necessario aggiornarlo prima di distribuire il connettore Cloud, poiché quando si esegue **Register-CcAppliance** per registrare un dispositivo in un sito esistente o nuovo, il cmdlet utilizzerà **siteName** per determinare il sito da registrare.</span><span class="sxs-lookup"><span data-stu-id="fb3da-182">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="fb3da-183">Se si desidera registrare l'accessorio in un nuovo sito, è necessario che il valore di **siteName** sia univoco e diverso rispetto ai siti esistenti.</span><span class="sxs-lookup"><span data-stu-id="fb3da-183">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="fb3da-184">Se si desidera registrare l'accessorio in un sito esistente, il valore per **siteName** nel file. ini deve corrispondere al nome definito nella configurazione dell'organizzazione di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb3da-184">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="fb3da-185">Se si sta copiando un file di configurazione da un sito a un altro, accertarsi di aver aggiornato di conseguenza il valore per **siteName** per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="fb3da-185">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="fb3da-186">**NomeServer:** Il nome del server non deve contenere il nome di dominio e deve essere limitato a 15 caratteri.</span><span class="sxs-lookup"><span data-stu-id="fb3da-186">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="fb3da-187">**HardwareType:** Se non si imposta o non si lascia il valore a null, verrà utilizzato il valore predefinito **Normal** .</span><span class="sxs-lookup"><span data-stu-id="fb3da-187">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="fb3da-188">Utilizzo **normale** se si prevede di distribuire la versione più grande del connettore Cloud per supportare le chiamate simultanee di 500 per ogni computer host, come descritto in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="fb3da-188">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="fb3da-189">Utilizzare il **valore minimo** per una distribuzione più piccola che supporta le chiamate simultanee 50.</span><span class="sxs-lookup"><span data-stu-id="fb3da-189">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="fb3da-190">**Switch virtuali Internet/corpnet/Management:**: aggiungere il nome delle opzioni virtuali create.</span><span class="sxs-lookup"><span data-stu-id="fb3da-190">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="fb3da-191">Per l'opzione gestione virtuale, lasciare il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="fb3da-191">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="fb3da-192">Lo script di distribuzione creerà l'opzione di gestione virtuale all'inizio della distribuzione ed eliminerà la distribuzione al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="fb3da-192">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="fb3da-193">**ManagementIPPrefix:** ManagementIPPrefix nella sezione rete deve essere una subnet diversa da altri indirizzi IP interni.</span><span class="sxs-lookup"><span data-stu-id="fb3da-193">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="fb3da-194">Ad esempio, come indicato nel valore predefinito, ManagementIPPrefix è 192.168.213.0, mentre AD IPAddress è 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="fb3da-194">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="fb3da-195">Gli script di distribuzione creano una scheda di rete di gestione su ogni macchina virtuale, assegnano un IP di gestione e la collegano a una switch virtuale di gestione.</span><span class="sxs-lookup"><span data-stu-id="fb3da-195">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="fb3da-196">In questo modo il server host è in grado di connettersi e gestire ogni macchina virtuale tramite questa rete di gestione.</span><span class="sxs-lookup"><span data-stu-id="fb3da-196">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="fb3da-197">L'opzione di gestione virtuale viene eliminata al termine della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb3da-197">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="fb3da-198">**Configurazioni specifiche per VM di base:** Per il cmdlet **Convert-CcIsoToVhdx** è necessario configurare le impostazioni di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="fb3da-198">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="fb3da-199">Durante la preparazione dell'immagine di base della VM, la VM di base verrà connessa all'opzione di rete interna.</span><span class="sxs-lookup"><span data-stu-id="fb3da-199">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="fb3da-200">Le impostazioni seguenti sono critiche affinché la VM sia in grado di accedere a Internet:</span><span class="sxs-lookup"><span data-stu-id="fb3da-200">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="fb3da-201">Comune BaseVMIP: l'indirizzo IP di corpnet da assegnare alla VM di base.</span><span class="sxs-lookup"><span data-stu-id="fb3da-201">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="fb3da-202">Rete CorpnetDefaultGateway: il gateway predefinito da assegnare alla VM di base.</span><span class="sxs-lookup"><span data-stu-id="fb3da-202">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="fb3da-203">Rete CorpnetDNSIPAddress: l'indirizzo IP DNS da assegnare alla VM di base.</span><span class="sxs-lookup"><span data-stu-id="fb3da-203">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="fb3da-204">Rete WSUSServer: l'indirizzo IP del servizio Windows Server Update.</span><span class="sxs-lookup"><span data-stu-id="fb3da-204">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="fb3da-205">Rete WSUSStatusServer: l'indirizzo IP del server di stato del servizio Windows Server Update.</span><span class="sxs-lookup"><span data-stu-id="fb3da-205">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="fb3da-206">Rete EnableReferSupport: consente di definire se il supporto SIP REFER è abilitato o disabilitato sulla configurazione trunk nell'IP/PBX.</span><span class="sxs-lookup"><span data-stu-id="fb3da-206">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="fb3da-207">**IPs interno:**</span><span class="sxs-lookup"><span data-stu-id="fb3da-207">**Internal IPs:**</span></span>

  - <span data-ttu-id="fb3da-208">Assicurarsi che la subnet mask CorpnetIPPrefixLength sia corretta.</span><span class="sxs-lookup"><span data-stu-id="fb3da-208">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="fb3da-209">Verificare che non vi siano conflitti IP per questi indirizzi IPs interni.</span><span class="sxs-lookup"><span data-stu-id="fb3da-209">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="fb3da-210">**Indirizzi IP esterni:**</span><span class="sxs-lookup"><span data-stu-id="fb3da-210">**External IPs:**</span></span>

  - <span data-ttu-id="fb3da-211">Per l'indirizzo IP pubblico di MR: specificare ExternalMRIPs per non NAT o ExternalMRPublicIPs per NAT.</span><span class="sxs-lookup"><span data-stu-id="fb3da-211">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="fb3da-212">ExternalSIPIPs e ExternalMRIPs possono essere uguali.</span><span class="sxs-lookup"><span data-stu-id="fb3da-212">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="fb3da-213">Assicurarsi che la subnet mask InternetIPPrefixLength sia corretta.</span><span class="sxs-lookup"><span data-stu-id="fb3da-213">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="fb3da-214">Verificare che non vi siano conflitti IP per questi indirizzi IPs esterni.</span><span class="sxs-lookup"><span data-stu-id="fb3da-214">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="fb3da-215">**Gateway**</span><span class="sxs-lookup"><span data-stu-id="fb3da-215">**Gateways:**</span></span>

  - <span data-ttu-id="fb3da-216">Se si dispone di un solo gateway, rimuovere la sezione per il gateway secondario.</span><span class="sxs-lookup"><span data-stu-id="fb3da-216">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="fb3da-217">Se si dispone di più di due gateway, creare sezioni aggiuntive copiando e incollando quella esistente e quindi aggiornando.</span><span class="sxs-lookup"><span data-stu-id="fb3da-217">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="fb3da-218">Verificare che l'indirizzo IP e la porta del gateway siano corretti.</span><span class="sxs-lookup"><span data-stu-id="fb3da-218">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="fb3da-219">Per supportare l'HA a livello di gateway PSTN, lasciare il gateway secondario e aggiungere eventuali gateway aggiuntivi che verranno utilizzati.</span><span class="sxs-lookup"><span data-stu-id="fb3da-219">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="fb3da-220">È possibile copiare e incollare una voce esistente e quindi aggiornarla.</span><span class="sxs-lookup"><span data-stu-id="fb3da-220">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="fb3da-221">Facoltativamente, è possibile aggiornare il valore LocalRoute per limitare i numeri di chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="fb3da-221">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="fb3da-222">Scaricare i bit nella directory del sito</span><span class="sxs-lookup"><span data-stu-id="fb3da-222">Download the bits to the Site Directory</span></span>

<span data-ttu-id="fb3da-223">Eseguire il cmdlet seguente per scaricare i file di informazioni sui bit e la versione nella **directory del sito**:</span><span class="sxs-lookup"><span data-stu-id="fb3da-223">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="fb3da-224">È necessario eseguire questo passaggio solo per il primo accessorio.</span><span class="sxs-lookup"><span data-stu-id="fb3da-224">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="fb3da-225">Preparare il disco virtuale di base (VHDX) dal file ISO scaricato</span><span class="sxs-lookup"><span data-stu-id="fb3da-225">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="fb3da-226">Questo passaggio prepara un file del disco rigido virtuale (VHDX) dall'immagine ISO di Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="fb3da-226">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="fb3da-227">Il VHDX verrà utilizzato per creare macchine virtuali durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fb3da-227">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="fb3da-228">Verrà creata una macchina virtuale temporanea (VM di base) e verrà installato Windows Server 2012 dal file ISO.</span><span class="sxs-lookup"><span data-stu-id="fb3da-228">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="fb3da-229">Dopo aver creato la VM, verranno installati alcuni componenti necessari e verrà applicato l'ultimo aggiornamento di Windows.</span><span class="sxs-lookup"><span data-stu-id="fb3da-229">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="fb3da-230">Alla fine, la VM di base verrà generalizzata (Sysprep) e ripulita, lasciando solo il file del disco virtuale generato.</span><span class="sxs-lookup"><span data-stu-id="fb3da-230">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="fb3da-231">È necessario eseguire questo passaggio solo per il primo accessorio.</span><span class="sxs-lookup"><span data-stu-id="fb3da-231">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="fb3da-232">Prima di procedere con questo passaggio, assicurarsi che l'opzione corpnet sia stata creata.</span><span class="sxs-lookup"><span data-stu-id="fb3da-232">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="fb3da-233">Verificare inoltre che le impostazioni seguenti siano state configurate correttamente nel file CloudConnector.ini:</span><span class="sxs-lookup"><span data-stu-id="fb3da-233">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="fb3da-234">Rete CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="fb3da-234">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="fb3da-235">Comune BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="fb3da-235">[Common]BaseVMIP</span></span>

- <span data-ttu-id="fb3da-236">Rete CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="fb3da-236">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="fb3da-237">Rete CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="fb3da-237">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="fb3da-238">Rete CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="fb3da-238">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="fb3da-239">Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per convertire l'immagine ISO in un disco rigido virtuale (VHD):</span><span class="sxs-lookup"><span data-stu-id="fb3da-239">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="fb3da-240">Specificare il percorso completo, incluso il nome del file, nell'immagine ISO.</span><span class="sxs-lookup"><span data-stu-id="fb3da-240">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="fb3da-241">Ad esempio: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="fb3da-241">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="fb3da-242">Il file VHD creato è archiviato nella cartella \Bits\VHD **directory del sito** .</span><span class="sxs-lookup"><span data-stu-id="fb3da-242">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="fb3da-243">È possibile ottenere il percorso della **directory del sito** eseguendo il **Get-CcSiteDirectory**.</span><span class="sxs-lookup"><span data-stu-id="fb3da-243">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb3da-244">Per impostazione predefinita, le impostazioni proxy non sono configurate sulla VM di base.</span><span class="sxs-lookup"><span data-stu-id="fb3da-244">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="fb3da-245">Se nell'ambiente di rete è necessario un proxy per aggiornare la VM tramite Windows Update, è necessario aggiungere l'opzione-PauseBeforeUpdate quando si esegue "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="fb3da-245">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="fb3da-246">Lo script interromperà prima di Windows Update e si avrà la possibilità di configurare manualmente proxy sulla macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="fb3da-246">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="fb3da-247">Dopo l'installazione del proxy e la VM può accedere a Internet, è possibile riprendere lo script per completare i passaggi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="fb3da-247">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="fb3da-248">Creare dischi rigidi virtuali per una distribuzione a più siti</span><span class="sxs-lookup"><span data-stu-id="fb3da-248">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="fb3da-249">Si tratta di un passaggio facoltativo che si applica solo alle distribuzioni multisito.</span><span class="sxs-lookup"><span data-stu-id="fb3da-249">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="fb3da-250">Se si sta distribuendo una distribuzione a più siti, non è necessario convertire la ISO in un disco rigido virtuale per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="fb3da-250">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="fb3da-251">È possibile copiare il VHDX creato per il primo sito nel server host per un secondo sito.</span><span class="sxs-lookup"><span data-stu-id="fb3da-251">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="fb3da-252">Copiare il file nello stesso percorso di file (cartella \Bits\VHD **directory del sito** ) e con lo stesso nome file nel server host per un sito aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="fb3da-252">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="fb3da-253">Impostare il criterio di esecuzione di PowerShell su RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="fb3da-253">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="fb3da-254">Gli script di PowerShell forniti richiedono che il criterio di esecuzione sia impostato su RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="fb3da-254">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="fb3da-255">Per visualizzare l'impostazione corrente, aprire una console PowerShell come amministratore ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="fb3da-255">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="fb3da-256">Se non è impostato su "RemoteSigned", eseguire il seguente cmdlet per modificarlo:</span><span class="sxs-lookup"><span data-stu-id="fb3da-256">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="fb3da-257">Modificare criteri di gruppo locali nel computer host (versioni 1.4.1 e precedenti)</span><span class="sxs-lookup"><span data-stu-id="fb3da-257">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="fb3da-258">Questa attività non è obbligatoria per le versioni 1.4.2 e successive del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="fb3da-258">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="fb3da-259">L'account CceService viene creato durante la distribuzione di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="fb3da-259">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="fb3da-260">Esegue il servizio di gestione Cloud Connector e richiede l'autorizzazione per disinstallare il cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="fb3da-260">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="fb3da-261">È necessario modificare l'impostazione di criteri di gruppo nel computer host del connettore Cloud per specificare che il registro di sistema dell'utente non deve essere scaricato quando l'utente si disconnette.</span><span class="sxs-lookup"><span data-stu-id="fb3da-261">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="fb3da-262">Attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="fb3da-262">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="fb3da-263">Per modificare l'impostazione di criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="fb3da-263">To change the Group Policy setting</span></span>

1. <span data-ttu-id="fb3da-264">Aprire l' **Editor criteri di gruppo** eseguendo gpedit. msc.</span><span class="sxs-lookup"><span data-stu-id="fb3da-264">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="fb3da-265">Nell' **Editor criteri di gruppo**, passare a modelli amministrativi > System > UserProfile > non scaricare con forza il registro di sistema dell'utente alla disconnessione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fb3da-265">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="fb3da-266">Impostarne il valore su **attivato**.</span><span class="sxs-lookup"><span data-stu-id="fb3da-266">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="fb3da-267">Configurare l'organizzazione Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="fb3da-267">Set up your Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="fb3da-268">È necessaria un'organizzazione Microsoft 365 o Office 365 con Skype for business online e il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="fb3da-268">A Microsoft 365 or Office 365 organization with Skype for Business Online and Phone System is required.</span></span> <span data-ttu-id="fb3da-269">Verificare che il tenant sia configurato e configurato prima di tentare di utilizzare il connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="fb3da-269">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="fb3da-270">Alcuni passaggi di installazione di Microsoft 365 e Office 365 richiedono l'utilizzo di TRPS (tenant Remote PowerShell) per configurare l'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb3da-270">Some Microsoft 365 and Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="fb3da-271">**Tale operazione deve essere installata nel server host.**</span><span class="sxs-lookup"><span data-stu-id="fb3da-271">**This should be installed on the host server.**</span></span> <span data-ttu-id="fb3da-272">È possibile scaricare il modulo Skype for business online per PowerShell da: [Skype for business online, modulo di Windows PowerShell](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="fb3da-272">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="fb3da-273">Creare un account di amministratore di Skype for business dedicato per la gestione di Cloud Connector online, ad esempio CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fb3da-273">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="fb3da-274">Questo account verrà utilizzato dall'accessorio per aggiungere o rimuovere Appliance, abilitare o disabilitare l'aggiornamento automatico del sistema operativo, abilitare o disabilitare l'aggiornamento automatico binario.</span><span class="sxs-lookup"><span data-stu-id="fb3da-274">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="fb3da-275">Impostare la password per l'account affinché non scada mai in modo che non sia necessario modificarla per il servizio ogni volta che scade.</span><span class="sxs-lookup"><span data-stu-id="fb3da-275">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


