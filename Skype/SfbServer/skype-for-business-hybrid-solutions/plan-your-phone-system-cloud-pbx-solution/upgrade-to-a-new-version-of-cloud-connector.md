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
description: Informazioni su come eseguire l'aggiornamento della distribuzione di Cloud Connector Edition.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359292"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="50866-103">Eseguire l'aggiornamento a una nuova versione di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="50866-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="50866-104">Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="50866-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="50866-105">Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="50866-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="50866-106">Informazioni su come eseguire l'aggiornamento della distribuzione di Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="50866-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="50866-107">Se è stato configurato un account tenant di gestione online e gli aggiornamenti automatici sono stati abilitati, la distribuzione esistente di Skype for Business Cloud Connector Edition verrà aggiornata automaticamente alla versione più recente, in base alla configurazione della finestra di tempo per l'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="50866-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="50866-108">È inoltre possibile eseguire un aggiornamento manuale.</span><span class="sxs-lookup"><span data-stu-id="50866-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="50866-109">Le versioni di Cloud Connector Edition 1.4.1 e versioni successive eseguono gli aggiornamenti automatici per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="50866-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="50866-110">Se si desidera eseguire l'aggiornamento alla versione più recente (2,1) manualmente, vedere [upgrade a single site to a New Version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="50866-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="50866-111">Per l'aggiornamento automatico è necessario che il servizio Cloud Connector sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="50866-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="50866-112">Nei passaggi seguenti viene descritto il processo per gli aggiornamenti automatici:</span><span class="sxs-lookup"><span data-stu-id="50866-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="50866-113">Il processo di aggiornamento automatico verrà eseguito in base alla pianificazione configurata per gli aggiornamenti automatici.</span><span class="sxs-lookup"><span data-stu-id="50866-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="50866-114">Attività di aggiornamento del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="50866-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="50866-115">Controllare e scaricare gli aggiornamenti del sistema operativo per tutte le macchine virtuali dei connettori cloud.</span><span class="sxs-lookup"><span data-stu-id="50866-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="50866-116">Installare e aggiornare tutte le macchine virtuali del connettore Cloud una alla volta e riavviare.</span><span class="sxs-lookup"><span data-stu-id="50866-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="50866-117">Dopo il riavvio delle macchine virtuali del connettore Cloud, controllare se è necessario un altro riavvio.</span><span class="sxs-lookup"><span data-stu-id="50866-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="50866-118">Dopo che le macchine virtuali dei connettori cloud sono state patchate, ripetere il processo per il computer host del Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="50866-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="50866-119">Dopo il corretto avvio del computer host del connettore Cloud, vengono completate tutte le attività di aggiornamento del sistema operativo in sospeso.</span><span class="sxs-lookup"><span data-stu-id="50866-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="50866-120">Attività di aggiornamento del connettore Cloud</span><span class="sxs-lookup"><span data-stu-id="50866-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="50866-121">Scaricare e controllare il file di versione dal sito di download.</span><span class="sxs-lookup"><span data-stu-id="50866-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="50866-122">Scaricare il nuovo file version. msi.</span><span class="sxs-lookup"><span data-stu-id="50866-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="50866-123">Disinstallare il file MSI precedente; installare il nuovo file MSI.</span><span class="sxs-lookup"><span data-stu-id="50866-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="50866-124">Scaricare la nuova versione dei bit di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="50866-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="50866-125">Registrazione dell'accessorio tramite la chiamata a Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="50866-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="50866-126">Installare la nuova versione del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="50866-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="50866-127">Svuotare il dispositivo vecchio e cambiare la connessione di rete al nuovo accessorio.</span><span class="sxs-lookup"><span data-stu-id="50866-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="50866-128">Quando il connettore Cloud viene aggiornato a una nuova generazione, i cmdlet del connettore cloud potrebbero non essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="50866-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="50866-129">Questa situazione può verificarsi, ad esempio, se una finestra di PowerShell viene lasciata aperta quando si verifica l'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="50866-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="50866-130">Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti: > chiudere PowerShell nell'accessorio Cloud Connector e quindi riaprire PowerShell. > oppure, è possibile eseguire Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="50866-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="50866-131">Aggiornare un singolo sito a una nuova versione</span><span class="sxs-lookup"><span data-stu-id="50866-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="50866-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="50866-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="50866-133">Se è presente un solo dispositivo nel sito che si desidera aggiornare, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50866-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="50866-134">Disinstallare la versione del connettore cloud esistente nei \*\* \> \> programmi e nelle funzionalità dei programmi del pannello di controllo\*\*.</span><span class="sxs-lookup"><span data-stu-id="50866-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="50866-135">Installare la nuova versione di CloudConnector.msi da [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="50866-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="50866-136">Verificare di disporre del file CloudConnector.ini per la versione che si sta installando e di aver aggiornato tutti i valori necessari per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="50866-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="50866-137">Non è possibile utilizzare il file ini da una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="50866-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="50866-138">Se si esegue l'aggiornamento del connettore Cloud, fare riferimento all'argomento [preparare l'accessorio Cloud Connector](prepare-your-cloud-connector-appliance.md) e verificare che SiteName e EnableReferSupport siano impostati sul valore corretto nel file CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="50866-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="50866-139">Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'accessorio corrente:</span><span class="sxs-lookup"><span data-stu-id="50866-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="50866-140">Eseguire il cmdlet seguente per scaricare la versione più recente:</span><span class="sxs-lookup"><span data-stu-id="50866-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="50866-141">Per avviare l'installazione, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="50866-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="50866-142">Eseguire il cmdlet seguente per attivare la nuova distribuzione e disattivare la versione precedente:</span><span class="sxs-lookup"><span data-stu-id="50866-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="50866-143">Se nel sito sono presenti più dispositivi, seguire la procedura descritta in precedenza per aggiornare ogni accessorio uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="50866-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="50866-144">Se si desidera aggiornare l'amministratore del dominio, l'amministratore della macchina virtuale, l'amministratore della modalità provvisoria e le credenziali di amministratore tenant, è possibile eseguire il cmdlet con il parametro  _UpdateAllCredentials_ per reimpostare tutte le credenziali:</span><span class="sxs-lookup"><span data-stu-id="50866-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="50866-145">Quando si inizia a eseguire l'aggiornamento a una nuova versione, l'utente verrà quindi promosso per immettere le nuove credenziali.</span><span class="sxs-lookup"><span data-stu-id="50866-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="50866-146">Se si desidera reimpostare solo le credenziali di amministratore tenant, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="50866-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="50866-147">Aggiornare più siti a una nuova versione</span><span class="sxs-lookup"><span data-stu-id="50866-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="50866-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="50866-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="50866-149">Seguire la procedura per l'aggiornamento di un singolo sito, l'aggiornamento di un sito alla volta per ogni sito della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="50866-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="50866-150">Verificare e [convalidare la distribuzione del connettore Cloud](validate-your-cloud-connector-deployment.md) dopo l'aggiornamento di ogni sito.</span><span class="sxs-lookup"><span data-stu-id="50866-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

