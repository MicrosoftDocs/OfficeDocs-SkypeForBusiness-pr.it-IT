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
description: Informazioni su come preparare l'applicazione Cloud Connector per la distribuzione e l'utilizzo con Sistema telefonico (Cloud PBX).
ms.openlocfilehash: 74c4885a25b4176f4d5eb3ac27926bd9528387c6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358942"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="70424-103">Predisporre l'appliance di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="70424-103">Prepare your Cloud Connector appliance</span></span>

> [!Important]
> <span data-ttu-id="70424-104">Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="70424-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="70424-105">Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="70424-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="70424-106">Informazioni su come preparare l'applicazione Cloud Connector per la distribuzione e l'utilizzo con Sistema telefonico (Cloud PBX).</span><span class="sxs-lookup"><span data-stu-id="70424-106">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System (Cloud PBX).</span></span>

<span data-ttu-id="70424-107">Questa sezione descrive come ottenere i file di installazione di Skype for Business Cloud Connector Edition, installare il software Cloud Connector e preparare l'applicazione Cloud Connector per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="70424-107">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="70424-108">Dopo aver completato tutti i passaggi descritti in questa sezione, si sarà pronti per distribuire Cloud Connector per uno o più siti.</span><span class="sxs-lookup"><span data-stu-id="70424-108">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="70424-109">Se si dispone di una distribuzione di Cloud Connector esistente e non è stato ancora eseguito l'aggiornamento a Cloud Connector versione 2.1, vedere Eseguire l'aggiornamento a una nuova versione [di Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="70424-109">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="70424-110">Microsoft supporta la versione corrente di Cloud Connector Edition, versione 2.1.</span><span class="sxs-lookup"><span data-stu-id="70424-110">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="70424-111">Se è stato configurato l'aggiornamento automatico, Cloud Connector verrà aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="70424-111">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="70424-112">Se è stato configurato l'aggiornamento manuale, sarà necessario eseguire l'aggiornamento alla versione 2.1 entro 60 giorni dal rilascio.</span><span class="sxs-lookup"><span data-stu-id="70424-112">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="70424-113">Microsoft supporterà la versione precedente per 60 giorni dopo il rilascio della 2.1 per consentire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="70424-113">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="70424-114">Per Cloud Connector versione 2.1 e successive, nell'applicazione host deve essere installato .NET Framework 4.6.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="70424-114">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="70424-115">Per una distribuzione corretta, quando si eseguono i cmdlet per configurare Skype for Business Cloud Connector Edition, usare sempre la stessa sessione console di quella avviata.</span><span class="sxs-lookup"><span data-stu-id="70424-115">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="70424-116">Evitare di passare a sessioni diverse durante la distribuzione e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="70424-116">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="70424-117">Esistono alcuni passaggi da eseguire solo per il primo dispositivo nella distribuzione: creazione di una condivisione per la directory dei siti, download dei bit e preparazione di un file del disco rigido virtuale (VHDX) dall'immagine ISO di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="70424-117">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="70424-118">Scaricare il programma di installazione di Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="70424-118">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="70424-119">Nel server host in cui verranno eseguite le macchine virtuali di Cloud Connector, scaricare i file di installazione: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="70424-119">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="70424-120">Il server host deve essere in grado di accedere a Internet durante l'installazione di Cloud Connector perché durante l'installazione vengono scaricati file aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="70424-120">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="70424-121">Eseguire il programma di installazione e accettare i valori predefiniti durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="70424-121">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="70424-122">Verificare che l'installazione sia stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="70424-122">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="70424-123">Verificare l'installazione e configurare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="70424-123">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="70424-124">Aprire una console di PowerShell come amministratore e verificare che i cmdlet di Skype for Business Cloud Connector Edition siano disponibili utilizzando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="70424-124">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="70424-125">Il comando deve restituire un elenco di cmdlet per Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="70424-125">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="70424-126">I file VHD, SfBBits e VersionInfo verranno archiviati nella **directory dei siti.**</span><span class="sxs-lookup"><span data-stu-id="70424-126">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="70424-127">È possibile trovare il percorso della **directory siti** con il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="70424-127">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="70424-128">Il comando deve restituire un percorso nel file system.</span><span class="sxs-lookup"><span data-stu-id="70424-128">The command should return a location in your file system.</span></span> <span data-ttu-id="70424-129">Il percorso può essere una cartella locale o una condivisione file.</span><span class="sxs-lookup"><span data-stu-id="70424-129">The location can be a local folder or a file share.</span></span> <span data-ttu-id="70424-130">Il percorso predefinito per la **directory dei** siti è: %USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="70424-130">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="70424-131">Il percorso predefinito deve essere modificato in una condivisione file nel primo dispositivo creato in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="70424-131">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="70424-132">La posizione selezionata deve essere:</span><span class="sxs-lookup"><span data-stu-id="70424-132">The location you select must be:</span></span>

   - <span data-ttu-id="70424-133">Creato nel primo dispositivo creato in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="70424-133">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="70424-134">Cartella condivisa accessibile dagli altri server host (appliance) nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="70424-134">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="70424-135">Per impostare **la directory siti** su un percorso diverso da quello predefinito, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="70424-135">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="70424-136">Se si distribuisce la disponibilità elevata (HA) per il sito, eseguire il cmdlet per impostare la **directory** siti sullo stesso percorso in ogni server host all'interno del sito.</span><span class="sxs-lookup"><span data-stu-id="70424-136">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="70424-137">Quando si esegue l'accesso e si distribuisce ogni appliance nel sito, verificare che l'account di accesso corrente abbia il diritto di accesso alla **directory siti.**</span><span class="sxs-lookup"><span data-stu-id="70424-137">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="70424-138">La **directory appliance è** la directory radice di lavoro locale per Skype for Business Cloud Connector Edition e il percorso in cui vengono salvati certificati, istanze e log esterni.</span><span class="sxs-lookup"><span data-stu-id="70424-138">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="70424-139">Il percorso predefinito è: %USERPROFILE%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="70424-139">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="70424-140">Per trovare il percorso della **directory dell'appliance,** eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="70424-140">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="70424-141">Per impostare la **directory dell'appliance** su un percorso diverso da quello predefinito, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="70424-141">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="70424-142">La directory dell'applicazione deve essere impostata su una cartella locale nell'appliance.</span><span class="sxs-lookup"><span data-stu-id="70424-142">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="70424-143">È consigliabile impostare la **directory appliance solo** prima di avviare la distribuzione di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="70424-143">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="70424-144">Se lo si modifica dopo la distribuzione, sarà necessario ridistribuire il server host.</span><span class="sxs-lookup"><span data-stu-id="70424-144">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="70424-145">Il percorso della **directory del** dispositivo non deve contenere spazi.</span><span class="sxs-lookup"><span data-stu-id="70424-145">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="70424-146">Impostare il percorso per il certificato perimetrale esterno</span><span class="sxs-lookup"><span data-stu-id="70424-146">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="70424-147">Eseguire il cmdlet seguente per impostare il percorso, incluso il nome del file, sul certificato perimetrale esterno.</span><span class="sxs-lookup"><span data-stu-id="70424-147">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="70424-148">Ad esempio: C:\certs\cce\ap.contoso.com.pfx.</span><span class="sxs-lookup"><span data-stu-id="70424-148">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="70424-149">Il certificato deve contenere chiavi private.</span><span class="sxs-lookup"><span data-stu-id="70424-149">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="70424-150">Si noti che il parametro -Target è specifico delle versioni 1.4.2 e successive.</span><span class="sxs-lookup"><span data-stu-id="70424-150">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="70424-151">Specificare il percorso completo del certificato esterno, incluso il nome del file.</span><span class="sxs-lookup"><span data-stu-id="70424-151">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="70424-152">Il certificato può essere archiviato localmente o in una condivisione file.</span><span class="sxs-lookup"><span data-stu-id="70424-152">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="70424-153">Se il certificato è archiviato in una cartella condivisa, la cartella condivisa deve essere creata nel primo dispositivo di ogni sito e deve essere accessibile da altre appliance appartenenti allo stesso sito.</span><span class="sxs-lookup"><span data-stu-id="70424-153">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="70424-154">Questo cmdlet copia il certificato esterno nella **directory appliance.**</span><span class="sxs-lookup"><span data-stu-id="70424-154">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="70424-155">Se è stato aggiornato **a Cloud Connector versione 1.4.2** o successiva, verificare che il certificato esterno preparato contenga chiavi private e la catena di certificati completa, inclusi il certificato CA radice e i certificati della CA intermedia.</span><span class="sxs-lookup"><span data-stu-id="70424-155">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="70424-156">**Se NON è stato ancora aggiornato a Cloud Connector versione 1.4.2,** verificare che il certificato esterno preparato contenga chiavi private.</span><span class="sxs-lookup"><span data-stu-id="70424-156">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="70424-157">Questo certificato esterno deve essere emesso da un'autorità di certificazione attendibile per impostazione predefinita da Windows.</span><span class="sxs-lookup"><span data-stu-id="70424-157">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="70424-158">Impostare il percorso per il certificato SBC/gateway PSTN esterno</span><span class="sxs-lookup"><span data-stu-id="70424-158">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="70424-159">Se si utilizza TLS tra Mediation Server e il gateway PSTN/SBC, eseguire il cmdlet seguente per impostare il percorso, incluso il nome file, sul certificato del gateway.</span><span class="sxs-lookup"><span data-stu-id="70424-159">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="70424-160">Ad esempio: C:\certs\cce\sbc.contoso.com.cer.</span><span class="sxs-lookup"><span data-stu-id="70424-160">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="70424-161">Il certificato deve contenere la CA radice e la catena intermedia per il certificato assegnato al gateway:</span><span class="sxs-lookup"><span data-stu-id="70424-161">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="70424-162">Si noti che il parametro -Target è specifico delle versioni 1.4.2 e successive.</span><span class="sxs-lookup"><span data-stu-id="70424-162">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="70424-163">Creare commutatori virtuali nella console di gestione di Hyper-V</span><span class="sxs-lookup"><span data-stu-id="70424-163">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="70424-164">Aprire Virtual Switch Manager di **Hyper-V**  >  **e** selezionare **Nuova console di gestione commutatore virtuale.**</span><span class="sxs-lookup"><span data-stu-id="70424-164">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="70424-165">Creare un commutatore virtuale esterno e associarlo alla scheda di rete fisica connessa al dominio di rete interno:</span><span class="sxs-lookup"><span data-stu-id="70424-165">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="70424-166">Selezionare **Consenti al sistema operativo di gestione di condividere questa scheda di rete** per questo commutatore virtuale.</span><span class="sxs-lookup"><span data-stu-id="70424-166">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="70424-167">Creare un commutatore virtuale esterno e associarlo alla scheda di rete fisica instradata a Internet:</span><span class="sxs-lookup"><span data-stu-id="70424-167">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="70424-168">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span><span class="sxs-lookup"><span data-stu-id="70424-168">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="70424-169">Impostare il nome del commutatore che connette la rete perimetrale al dominio di rete **interno SfB CCE Corpnet Switch.**</span><span class="sxs-lookup"><span data-stu-id="70424-169">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="70424-170">Impostare il nome del commutatore che connette la rete perimetrale a Internet **SfB CCE Internet Switch.**</span><span class="sxs-lookup"><span data-stu-id="70424-170">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="70424-171">Aggiornare il file CloudConnector.ini di configurazione</span><span class="sxs-lookup"><span data-stu-id="70424-171">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="70424-172">Preparare il file CloudConnector.ini utilizzando le informazioni raccolte in [Determinare](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) i parametri di distribuzione nell'argomento [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="70424-172">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="70424-173">Per aggiornare il file, eseguire innanzitutto il cmdlet seguente per ottenere il modello di esempio (CloudConnector.Sample.ini):</span><span class="sxs-lookup"><span data-stu-id="70424-173">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="70424-174">Il modello di esempio è archiviato nella **directory appliance.**</span><span class="sxs-lookup"><span data-stu-id="70424-174">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="70424-175">Dopo l'aggiornamento con i valori per l'ambiente, salvare il file come CloudConnector.ini nella **directory appliance.**</span><span class="sxs-lookup"><span data-stu-id="70424-175">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="70424-176">È possibile eseguire **Get-CcApplianceDirectory** per determinare il percorso della **directory dell'applicazione.**</span><span class="sxs-lookup"><span data-stu-id="70424-176">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="70424-177">Quando si aggiorna il file ini, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="70424-177">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="70424-178">Non tutti i valori per il file ini vengono illustrati in questa sezione, ma solo quelli con una considerazione speciale sono trattati qui.</span><span class="sxs-lookup"><span data-stu-id="70424-178">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="70424-179">Per un elenco completo, vedere la sezione [Determinare](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) i parametri di distribuzione dell'argomento [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="70424-179">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="70424-180">Per ulteriori informazioni sui valori da modificare per ulteriori appliance o nuovi siti, vedere Single [Site with High Availability (HA)](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) rispetto alle distribuzioni multisocietà nell'argomento Distribuire più siti in Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="70424-180">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="70424-181">**SiteName:** Il valore predefinito è **Site1.**</span><span class="sxs-lookup"><span data-stu-id="70424-181">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="70424-182">È necessario aggiornarlo prima di distribuire Cloud Connector, perché quando si esegue **Register-CcAppliance** per registrare un'applicazione in un sito esistente o nuovo, il cmdlet utilizzerà **SiteName** per determinare quale sito registrare.</span><span class="sxs-lookup"><span data-stu-id="70424-182">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="70424-183">Se si desidera registrare l'applicazione in un nuovo sito, il valore **di SiteName** deve essere univoco e diverso dai siti esistenti.</span><span class="sxs-lookup"><span data-stu-id="70424-183">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="70424-184">Se si desidera registrare l'applicazione in un sito esistente, il valore di **SiteName** nel file ini deve corrispondere al nome definito nella configurazione dell'organizzazione di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="70424-184">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="70424-185">Se si copia un file di configurazione da un sito a un altro, aggiornare il valore **di SiteName** per ogni sito di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="70424-185">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="70424-186">**ServerName:** Il nome del server non deve contenere il nome di dominio e deve contenere un massimo di 15 caratteri.</span><span class="sxs-lookup"><span data-stu-id="70424-186">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="70424-187">**HardwareType:** Se non si imposta o non si lascia il valore su Null, verrà utilizzato il valore predefinito **Normal.**</span><span class="sxs-lookup"><span data-stu-id="70424-187">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="70424-188">Utilizzare **Normal** se si prevede di distribuire la versione più grande di Cloud Connector per supportare 500 chiamate simultanee per computer host, come descritto in [Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="70424-188">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="70424-189">Utilizzare **Minimum** per una distribuzione di piccole dimensioni che supporta 50 chiamate simultanee.</span><span class="sxs-lookup"><span data-stu-id="70424-189">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="70424-190">**Commutatori virtuali Internet/Corpnet/Gestione:** aggiungere il nome dei commutatori virtuali creati.</span><span class="sxs-lookup"><span data-stu-id="70424-190">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="70424-191">Per il commutatore virtuale di gestione, lasciare il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="70424-191">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="70424-192">Lo script di distribuzione creerà il commutatore virtuale di gestione all'inizio della distribuzione ed lo eliminerà al termine della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="70424-192">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="70424-193">**ManagementIPPrefix:** ManagementIPPrefix nella sezione Network deve essere una subnet diversa da altri indirizzi IP interni.</span><span class="sxs-lookup"><span data-stu-id="70424-193">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="70424-194">Ad esempio, come mostra il valore predefinito, ManagementIPPrefix è 192.168.213.0, mentre AD IPAddress è 192.168.0.238.</span><span class="sxs-lookup"><span data-stu-id="70424-194">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="70424-195">Gli script di distribuzione creano una scheda di rete di gestione in ogni macchina virtuale, assegnano un IP di gestione e la connettono a un commutatore virtuale di gestione.</span><span class="sxs-lookup"><span data-stu-id="70424-195">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="70424-196">In questo modo il server host può connettersi e gestire ogni macchina virtuale tramite questa rete di gestione.</span><span class="sxs-lookup"><span data-stu-id="70424-196">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="70424-197">Il commutatore virtuale di gestione viene eliminato al termine della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="70424-197">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="70424-198">**Configurazioni specifiche della macchina virtuale di base:** Le impostazioni in questa sezione devono essere configurate per il cmdlet **Convert-CcIsoToVhdx.**</span><span class="sxs-lookup"><span data-stu-id="70424-198">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="70424-199">Durante la preparazione dell'immagine della macchina virtuale di base, la macchina virtuale di base verrà connessa al commutatore di rete interno.</span><span class="sxs-lookup"><span data-stu-id="70424-199">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="70424-200">Le impostazioni seguenti sono fondamentali per la macchina virtuale per poter accedere a Internet:</span><span class="sxs-lookup"><span data-stu-id="70424-200">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="70424-201">[Comune] BaseVMIP: l'indirizzo IP della corpnet da assegnare alla macchina virtuale di base.</span><span class="sxs-lookup"><span data-stu-id="70424-201">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="70424-202">[Rete] CorpnetDefaultGateway: gateway predefinito da assegnare alla macchina virtuale di base.</span><span class="sxs-lookup"><span data-stu-id="70424-202">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="70424-203">[Rete] CorpnetDNSIPAddress: l'indirizzo IP DNS da assegnare alla macchina virtuale di base.</span><span class="sxs-lookup"><span data-stu-id="70424-203">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="70424-204">[Rete] WSUSServer: l'indirizzo IP di Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="70424-204">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="70424-205">[Rete] WSUSStatusServer: l'indirizzo IP del server di stato di Windows Server Update Service.</span><span class="sxs-lookup"><span data-stu-id="70424-205">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="70424-206">[Rete] EnableReferSupport: in questo modo verrà definito se il supporto SIP REFER è abilitato o disabilitato nella configurazione trunk per l'IP/PBX.</span><span class="sxs-lookup"><span data-stu-id="70424-206">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="70424-207">**IP interni:**</span><span class="sxs-lookup"><span data-stu-id="70424-207">**Internal IPs:**</span></span>

  - <span data-ttu-id="70424-208">Verificare che la subnet mask CorpnetIPPrefixLength sia corretta.</span><span class="sxs-lookup"><span data-stu-id="70424-208">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="70424-209">Assicurarsi che non vi siano conflitti IP per questi indirizzi IP interni.</span><span class="sxs-lookup"><span data-stu-id="70424-209">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="70424-210">**IP esterni:**</span><span class="sxs-lookup"><span data-stu-id="70424-210">**External IPs:**</span></span>

  - <span data-ttu-id="70424-211">Per l'IP pubblico MR: specificare ExternalMRIPs per non NAT o ExternalMRPublicIPs per NAT.</span><span class="sxs-lookup"><span data-stu-id="70424-211">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="70424-212">ExternalSIPIPs e ExternalMRIPs possono essere uguali.</span><span class="sxs-lookup"><span data-stu-id="70424-212">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="70424-213">Verificare che la subnet mask InternetIPPrefixLength sia corretta.</span><span class="sxs-lookup"><span data-stu-id="70424-213">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="70424-214">Assicurarsi che non vi siano conflitti IP per questi indirizzi IP esterni.</span><span class="sxs-lookup"><span data-stu-id="70424-214">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="70424-215">**Gateway:**</span><span class="sxs-lookup"><span data-stu-id="70424-215">**Gateways:**</span></span>

  - <span data-ttu-id="70424-216">Se si dispone di un solo gateway, rimuovere la sezione per il gateway secondario.</span><span class="sxs-lookup"><span data-stu-id="70424-216">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="70424-217">Se sono disponibili più di due gateway, creare sezioni aggiuntive copiando e incollando quello esistente e quindi aggiornarlo.</span><span class="sxs-lookup"><span data-stu-id="70424-217">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="70424-218">Verificare che l'indirizzo IP e la porta dei gateway siano corretti.</span><span class="sxs-lookup"><span data-stu-id="70424-218">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="70424-219">Per supportare la messaggistica unificata a livello di gateway PSTN, lasciare il gateway secondario e aggiungere eventuali gateway aggiuntivi che verranno utilizzati.</span><span class="sxs-lookup"><span data-stu-id="70424-219">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="70424-220">È possibile copiare e incollare una voce esistente e quindi aggiornarla.</span><span class="sxs-lookup"><span data-stu-id="70424-220">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="70424-221">Facoltativamente, è possibile aggiornare il valore LocalRoute per limitare i numeri delle chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="70424-221">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="70424-222">Scaricare i bit nella directory dei siti</span><span class="sxs-lookup"><span data-stu-id="70424-222">Download the bits to the Site Directory</span></span>

<span data-ttu-id="70424-223">Eseguire il cmdlet seguente per scaricare i bit e i file di informazioni sulla versione nella **directory dei siti:**</span><span class="sxs-lookup"><span data-stu-id="70424-223">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="70424-224">È necessario eseguire questo passaggio solo per il primo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="70424-224">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="70424-225">Preparare il disco virtuale di base (VHDX) dal file ISO scaricato</span><span class="sxs-lookup"><span data-stu-id="70424-225">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="70424-226">Questo passaggio prepara un file del disco rigido virtuale (VHDX) dall'immagine ISO di Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="70424-226">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="70424-227">Il VHDX verrà usato per creare macchine virtuali durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="70424-227">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="70424-228">Verrà creata una macchina virtuale temporanea (macchina virtuale di base) e Windows Server 2012 verrà installato dal file ISO.</span><span class="sxs-lookup"><span data-stu-id="70424-228">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="70424-229">Dopo la creazione della macchina virtuale, verranno installati alcuni componenti necessari e verrà applicato l'aggiornamento di Windows più recente.</span><span class="sxs-lookup"><span data-stu-id="70424-229">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="70424-230">Alla fine, la macchina virtuale di base verrà generalizzata (sysprep) e pulita, lasciando solo il file del disco virtuale generato.</span><span class="sxs-lookup"><span data-stu-id="70424-230">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="70424-231">È necessario eseguire questo passaggio solo per il primo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="70424-231">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="70424-232">Prima di procedere con questo passaggio, verificare che il commutatore corpnet sia stato creato.</span><span class="sxs-lookup"><span data-stu-id="70424-232">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="70424-233">Verificare inoltre che le impostazioni seguenti siano configurate correttamente nel file CloudConnector.ini seguente:</span><span class="sxs-lookup"><span data-stu-id="70424-233">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="70424-234">[Rete] CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="70424-234">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="70424-235">[Comune] BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="70424-235">[Common]BaseVMIP</span></span>

- <span data-ttu-id="70424-236">[Rete] CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="70424-236">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="70424-237">[Rete] CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="70424-237">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="70424-238">[Rete] CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="70424-238">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="70424-239">Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per convertire l'immagine ISO in un disco rigido virtuale (VHD):</span><span class="sxs-lookup"><span data-stu-id="70424-239">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="70424-240">Specifica il percorso completo, incluso il nome del file, dell'immagine ISO.</span><span class="sxs-lookup"><span data-stu-id="70424-240">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="70424-241">Ad esempio: C:\ISO\WindowsServer2012R2.iso.</span><span class="sxs-lookup"><span data-stu-id="70424-241">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="70424-242">Il file VHD creato viene archiviato nella **cartella Site Directory** \Bits\VHD.</span><span class="sxs-lookup"><span data-stu-id="70424-242">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="70424-243">È possibile ottenere il percorso della **directory** siti eseguendo **Get-CcSiteDirectory.**</span><span class="sxs-lookup"><span data-stu-id="70424-243">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70424-244">Per impostazione predefinita, le impostazioni proxy non sono configurate nella macchina virtuale di base.</span><span class="sxs-lookup"><span data-stu-id="70424-244">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="70424-245">Se nell'ambiente di rete è necessario un proxy per aggiornare la macchina virtuale tramite Windows Update, è necessario aggiungere l'opzione -PauseBeforeUpdate quando si esegue "Convert-CcIsoToVhdx".</span><span class="sxs-lookup"><span data-stu-id="70424-245">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="70424-246">Lo script verrà sospeso prima di Windows Update e avrai la possibilità di configurare manualmente il proxy nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="70424-246">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="70424-247">Dopo l'installazione del proxy e la macchina virtuale può accedere a Internet, puoi riprendere lo script per completare i passaggi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="70424-247">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="70424-248">Creare dischi rigidi virtuali per una distribuzione multisode</span><span class="sxs-lookup"><span data-stu-id="70424-248">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="70424-249">Si tratta di un passaggio facoltativo che si applica solo alle distribuzioni multisnode.</span><span class="sxs-lookup"><span data-stu-id="70424-249">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="70424-250">Se si distribuisce una distribuzione multisnodo, non è necessario convertire l'ISO in un disco rigido virtuale per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="70424-250">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="70424-251">È possibile copiare il VHDX creato per il primo sito nel server host per un secondo sito.</span><span class="sxs-lookup"><span data-stu-id="70424-251">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="70424-252">Copiare il file nello stesso percorso del file ( **Directory** siti \Bits\cartella VHD) e con lo stesso nome file nel server host per un sito aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="70424-252">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="70424-253">Impostare il criterio di esecuzione di PowerShell su RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="70424-253">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="70424-254">Gli script di PowerShell forniti richiedono che il criterio di esecuzione sia impostato su RemoteSigned.</span><span class="sxs-lookup"><span data-stu-id="70424-254">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="70424-255">Per visualizzare l'impostazione corrente, aprire una console di PowerShell come amministratore ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="70424-255">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="70424-256">Se non è impostato su "RemoteSigned", eseguire il cmdlet seguente per modificarlo:</span><span class="sxs-lookup"><span data-stu-id="70424-256">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="70424-257">Modificare Criteri di gruppo locali nel computer host (versioni 1.4.1 e precedenti)</span><span class="sxs-lookup"><span data-stu-id="70424-257">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="70424-258">Questa attività non è necessaria per Cloud Connector versioni 1.4.2 e successive.</span><span class="sxs-lookup"><span data-stu-id="70424-258">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="70424-259">L'account CceService viene creato durante la distribuzione di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="70424-259">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="70424-260">Esegue il servizio di gestione del connettore cloud e richiede l'autorizzazione per disinstallare il cloudconnector.msi.</span><span class="sxs-lookup"><span data-stu-id="70424-260">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="70424-261">È necessario modificare l'impostazione di Criteri di gruppo nel computer host Cloud Connector per specificare che il Registro di sistema dell'utente non deve essere scaricato quando l'utente si disconnette.</span><span class="sxs-lookup"><span data-stu-id="70424-261">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="70424-262">Seguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="70424-262">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="70424-263">Per modificare l'impostazione di Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="70424-263">To change the Group Policy setting</span></span>

1. <span data-ttu-id="70424-264">Apri **l'Editor Criteri di** gruppo eseguendo gpedit.msc.</span><span class="sxs-lookup"><span data-stu-id="70424-264">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="70424-265">**Nell'Editor** Criteri di gruppo passare a Modelli amministrativi > Sistema > UserProfile > Non scaricare forzatamente il Registro di sistema utente alla disconnessione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="70424-265">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="70424-266">Impostarne il valore su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="70424-266">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="70424-267">Configurare l'organizzazione di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="70424-267">Set up your Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="70424-268">È necessaria un'organizzazione di Microsoft 365 o Office 365 con Skype for Business online e Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="70424-268">A Microsoft 365 or Office 365 organization with Skype for Business Online and Phone System is required.</span></span> <span data-ttu-id="70424-269">Verificare che il tenant sia configurato e configurato prima di tentare di utilizzare Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="70424-269">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="70424-270">Alcuni passaggi di configurazione di Microsoft 365 e Office 365 richiedono l'uso di Tenant Remote PowerShell (TRPS) per configurare l'organizzazione di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="70424-270">Some Microsoft 365 and Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="70424-271">**Deve essere installato nel server host.**</span><span class="sxs-lookup"><span data-stu-id="70424-271">**This should be installed on the host server.**</span></span> <span data-ttu-id="70424-272">È possibile scaricare il modulo di Skype for Business online per PowerShell da: [Skype for Business online, Windows PowerShell modulo.](https://www.microsoft.com/download/details.aspx?id=39366)</span><span class="sxs-lookup"><span data-stu-id="70424-272">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="70424-273">Creare un account amministratore Skype for Business dedicato per la gestione online di Cloud Connector, ad esempio CceOnlineManagmentAdministrator.</span><span class="sxs-lookup"><span data-stu-id="70424-273">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="70424-274">Questo account verrà utilizzato dal dispositivo per aggiungere o rimuovere appliance, abilitare o disabilitare l'aggiornamento automatico del sistema operativo, abilitare o disabilitare l'aggiornamento binario automatico.</span><span class="sxs-lookup"><span data-stu-id="70424-274">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="70424-275">Impostare la password per questo account in modo che non scada mai, in modo che non sia necessario modificarla per il servizio ogni volta che scade.</span><span class="sxs-lookup"><span data-stu-id="70424-275">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


