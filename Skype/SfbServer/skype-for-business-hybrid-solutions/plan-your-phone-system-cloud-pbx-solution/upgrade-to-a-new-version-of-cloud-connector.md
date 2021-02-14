---
title: Eseguire l'aggiornamento a una nuova versione di Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Informazioni su come aggiornare la distribuzione di Cloud Connector Edition.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359292"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="393bd-103">Eseguire l'aggiornamento a una nuova versione di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="393bd-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="393bd-104">Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="393bd-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="393bd-105">Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="393bd-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="393bd-106">Informazioni su come aggiornare la distribuzione di Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="393bd-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="393bd-107">Se è stato configurato un account tenant di gestione online e sono stati abilitati gli aggiornamenti automatici, la distribuzione esistente di Skype for Business Cloud Connector Edition verrà aggiornata automaticamente alla versione più recente, in base alla configurazione dell'intervallo di tempo di aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="393bd-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="393bd-108">È inoltre possibile eseguire un aggiornamento manuale.</span><span class="sxs-lookup"><span data-stu-id="393bd-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="393bd-109">Cloud Connector Edition versione 1.4.1 e successive esegue gli aggiornamenti automatici per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="393bd-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="393bd-110">Se si desidera eseguire manualmente l'aggiornamento alla versione più recente (2.1), vedere Aggiornare un singolo sito a una [nuova versione](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="393bd-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="393bd-111">L'aggiornamento automatico richiede che il servizio Cloud Connector sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="393bd-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="393bd-112">I passaggi seguenti descrivono il processo per gli aggiornamenti automatici:</span><span class="sxs-lookup"><span data-stu-id="393bd-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="393bd-113">Il processo di aggiornamento automatico verrà eseguito in base alla pianificazione configurata per gli aggiornamenti automatici.</span><span class="sxs-lookup"><span data-stu-id="393bd-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="393bd-114">Attività di aggiornamento del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="393bd-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="393bd-115">Controllare e scaricare gli aggiornamenti del sistema operativo per tutte le macchine virtuali del connettore cloud.</span><span class="sxs-lookup"><span data-stu-id="393bd-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="393bd-116">Installare e aggiornare tutte le macchine virtuali di Cloud Connector una alla volta e riavviare.</span><span class="sxs-lookup"><span data-stu-id="393bd-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="393bd-117">Dopo il riavvio delle macchine virtuali di Cloud Connector, verificare se è necessario un altro riavvio.</span><span class="sxs-lookup"><span data-stu-id="393bd-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="393bd-118">Dopo aver corretto l'applicazione di patch alle macchine virtuali del connettore Cloud, ripetere il processo per il computer host cloud connector.</span><span class="sxs-lookup"><span data-stu-id="393bd-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="393bd-119">Dopo l'avvio corretto del computer host cloud Connector, vengono completate tutte le attività di aggiornamento del sistema operativo in sospeso.</span><span class="sxs-lookup"><span data-stu-id="393bd-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="393bd-120">Attività di aggiornamento di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="393bd-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="393bd-121">Scaricare e controllare il file della versione dal sito di download.</span><span class="sxs-lookup"><span data-stu-id="393bd-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="393bd-122">Scaricare il file MSI della nuova versione.</span><span class="sxs-lookup"><span data-stu-id="393bd-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="393bd-123">Disinstallare il vecchio file msi; installare il nuovo file msi.</span><span class="sxs-lookup"><span data-stu-id="393bd-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="393bd-124">Scaricare la nuova versione dei bit di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="393bd-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="393bd-125">Registrare l'applicazione chiamando Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="393bd-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="393bd-126">Installare la nuova versione di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="393bd-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="393bd-127">Svuotare il vecchio dispositivo e passare la connessione di rete al nuovo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="393bd-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="393bd-128">Quando Cloud Connector esegue l'aggiornamento a una nuova build, i cmdlet di Cloud Connector potrebbero non essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="393bd-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="393bd-129">Ciò può verificarsi, ad esempio, se una finestra di PowerShell viene lasciata aperta durante l'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="393bd-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="393bd-130">Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti:> Chiudere PowerShell nell'applicazione Cloud Connector e quindi riaprire PowerShell.> Oppure, è possibile eseguire Import-Module CloudConnector -Force.</span><span class="sxs-lookup"><span data-stu-id="393bd-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="393bd-131">Aggiornare un singolo sito a una nuova versione</span><span class="sxs-lookup"><span data-stu-id="393bd-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="393bd-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="393bd-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="393bd-133">Se nel sito è presente un solo dispositivo da aggiornare, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="393bd-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="393bd-134">Disinstallare la versione esistente di Cloud Connector in **Programmi e funzionalità del Pannello di \> \> controllo.**</span><span class="sxs-lookup"><span data-stu-id="393bd-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="393bd-135">Installare la nuova versione di CloudConnector.msi da [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="393bd-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="393bd-136">Verificare di disporre del CloudConnector.ini per la versione che si sta installando e di aver aggiornato tutti i valori necessari per il proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="393bd-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="393bd-137">Non è possibile utilizzare il file ini di una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="393bd-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="393bd-138">Se si sta aggiornando Cloud Connector, fare riferimento all'argomento Preparare l'applicazione [Cloud Connector](prepare-your-cloud-connector-appliance.md) e assicurarsi che SiteName e EnableReferSupport siano impostati sul valore corretto nel file CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="393bd-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="393bd-139">Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'applicazione corrente:</span><span class="sxs-lookup"><span data-stu-id="393bd-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="393bd-140">Eseguire il cmdlet seguente per scaricare la versione più recente:</span><span class="sxs-lookup"><span data-stu-id="393bd-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="393bd-141">Eseguire il cmdlet seguente per avviare l'installazione:</span><span class="sxs-lookup"><span data-stu-id="393bd-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="393bd-142">Eseguire il cmdlet seguente per attivare la nuova distribuzione e disattivare la versione precedente:</span><span class="sxs-lookup"><span data-stu-id="393bd-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="393bd-143">Se nel sito sono presenti più appliance, seguire i passaggi precedenti per aggiornare ogni appliance uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="393bd-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="393bd-144">Se si desidera aggiornare le credenziali di amministratore di dominio, amministratore della macchina virtuale, amministratore in modalità provvisoria e amministratore tenant, è possibile eseguire il cmdlet con il parametro  _UpdateAllCredentials_ per reimpostare tutte le credenziali:</span><span class="sxs-lookup"><span data-stu-id="393bd-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="393bd-145">Quindi, quando si inizia l'aggiornamento a una nuova versione, si verrà alzati di livello per immettere le nuove credenziali.</span><span class="sxs-lookup"><span data-stu-id="393bd-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="393bd-146">Se si desidera solo reimpostare le credenziali di amministratore tenant, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="393bd-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="393bd-147">Aggiornare più siti a una nuova versione</span><span class="sxs-lookup"><span data-stu-id="393bd-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="393bd-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="393bd-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="393bd-149">Eseguire la procedura per aggiornare un singolo sito, aggiornando un sito alla volta per ogni sito della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="393bd-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="393bd-150">Verificare e [convalidare la distribuzione di Cloud Connector](validate-your-cloud-connector-deployment.md) dopo l'aggiornamento di ogni sito.</span><span class="sxs-lookup"><span data-stu-id="393bd-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

