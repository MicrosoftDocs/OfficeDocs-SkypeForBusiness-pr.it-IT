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
ms.openlocfilehash: d2f9d2a2720f67a2110ba97b7d100e5673a0015c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814144"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="1689d-103">Eseguire l'aggiornamento a una nuova versione di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1689d-103">Upgrade to a new version of Cloud Connector</span></span>
 
<span data-ttu-id="1689d-104">Informazioni su come aggiornare la distribuzione di Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="1689d-104">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="1689d-105">Se è stato configurato un account del tenant di gestione online e sono stati abilitati gli aggiornamenti automatici, la distribuzione esistente di Skype for Business Cloud Connector Edition verrà aggiornata automaticamente alla versione più recente, in base alla finestra del periodo di aggiornamento automatico configurazione.</span><span class="sxs-lookup"><span data-stu-id="1689d-105">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="1689d-106">È anche possibile eseguire un aggiornamento manuale.</span><span class="sxs-lookup"><span data-stu-id="1689d-106">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="1689d-107">Le versioni di Cloud Connector Edition 1.4.1 e successive eseguono gli aggiornamenti automatici per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1689d-107">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="1689d-108">Se si vuole eseguire l'aggiornamento manualmente alla versione più recente (2,1), vedere [aggiornare un singolo sito a una nuova versione](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1689d-108">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="1689d-109">L'aggiornamento automatico richiede che il servizio Cloud Connector sia in funzione.</span><span class="sxs-lookup"><span data-stu-id="1689d-109">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="1689d-110">I passaggi seguenti descrivono il processo per gli aggiornamenti automatici:</span><span class="sxs-lookup"><span data-stu-id="1689d-110">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="1689d-111">Il processo di aggiornamento automatico verrà eseguito in base alla programmazione configurata per gli aggiornamenti automatici.</span><span class="sxs-lookup"><span data-stu-id="1689d-111">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="1689d-112">Attività di aggiornamento del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="1689d-112">Operating system update tasks</span></span>
    
  - <span data-ttu-id="1689d-113">Controllare e scaricare gli aggiornamenti del sistema operativo in tutte le VM Connector di cloud.</span><span class="sxs-lookup"><span data-stu-id="1689d-113">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="1689d-114">Installare e aggiornare tutte le VM del connettore Cloud una alla volta e riavviare.</span><span class="sxs-lookup"><span data-stu-id="1689d-114">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="1689d-115">Dopo il riavvio del Cloud Connector VM, verificare se è necessario un altro riavvio.</span><span class="sxs-lookup"><span data-stu-id="1689d-115">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="1689d-116">Dopo la corretta correzione delle VM Connector cloud, ripetere il processo per il computer host Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1689d-116">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="1689d-117">Dopo che il computer host del Cloud Connector si avvia correttamente, vengono completate le attività di aggiornamento del sistema operativo in sospeso.</span><span class="sxs-lookup"><span data-stu-id="1689d-117">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="1689d-118">Attività di aggiornamento di Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1689d-118">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="1689d-119">Scaricare e controllare il file di versione dal sito di download.</span><span class="sxs-lookup"><span data-stu-id="1689d-119">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="1689d-120">Scaricare il nuovo file version. msi.</span><span class="sxs-lookup"><span data-stu-id="1689d-120">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="1689d-121">Disinstallare il vecchio file MSI; installare il nuovo file MSI.</span><span class="sxs-lookup"><span data-stu-id="1689d-121">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="1689d-122">Scaricare la nuova versione di bit di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="1689d-122">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="1689d-123">Registrare l'accessorio chiamando Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="1689d-123">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="1689d-124">Installare la nuova versione del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="1689d-124">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="1689d-125">Svuotare il vecchio elettrodomestico e passare alla connessione di rete al nuovo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1689d-125">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="1689d-126">Quando Cloud Connector viene aggiornato a una nuova build, i cmdlet di Cloud Connector potrebbero non essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="1689d-126">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="1689d-127">Questo può accadere, ad esempio, se una finestra di PowerShell viene aperta mentre si verifica l'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="1689d-127">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="1689d-128">Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti: > chiudere PowerShell nell'appliance di Cloud Connector e quindi riaprire PowerShell. > oppure, è possibile avviare Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="1689d-128">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="1689d-129">Aggiornare un singolo sito a una nuova versione</span><span class="sxs-lookup"><span data-stu-id="1689d-129">Upgrade a single site to a new version</span></span>
<span data-ttu-id="1689d-130"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="1689d-130"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="1689d-131">Se nel sito si vuole aggiornare un solo dispositivo, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1689d-131">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="1689d-132">Disinstallare la versione del connettore cloud esistente nei **programmi \> e \> nelle funzionalità dei programmi del pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="1689d-132">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="1689d-133">Installare la nuova versione di CloudConnector. msi da [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="1689d-133">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="1689d-134">Verificare di avere il file CloudConnector. ini per la versione che si sta installando e di avere aggiornato tutti i valori necessari per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="1689d-134">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="1689d-135">Non è possibile usare il file ini da una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="1689d-135">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="1689d-136">Se si sta aggiornando il connettore Cloud, vedere l'argomento [preparare l'accessorio Cloud Connector](prepare-your-cloud-connector-appliance.md) e verificare che SiteName e EnableReferSupport siano impostati sul valore corretto nel file CloudConnector. ini.</span><span class="sxs-lookup"><span data-stu-id="1689d-136">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="1689d-137">Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'accessorio corrente:</span><span class="sxs-lookup"><span data-stu-id="1689d-137">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="1689d-138">Eseguire il cmdlet seguente per scaricare la versione più recente:</span><span class="sxs-lookup"><span data-stu-id="1689d-138">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="1689d-139">Eseguire il cmdlet seguente per avviare l'installazione:</span><span class="sxs-lookup"><span data-stu-id="1689d-139">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="1689d-140">Eseguire il cmdlet seguente per attivare la nuova distribuzione e disattivare la versione precedente:</span><span class="sxs-lookup"><span data-stu-id="1689d-140">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="1689d-141">Se nel sito sono presenti più dispositivi, seguire la procedura descritta in precedenza per aggiornare ogni appliance uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="1689d-141">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="1689d-142">Se si vuole aggiornare l'amministratore di dominio, l'amministratore della macchina virtuale, l'amministratore della modalità provvisoria e le credenziali di amministratore del tenant, è possibile eseguire il cmdlet con il parametro _UpdateAllCredentials_ per reimpostare tutte le credenziali:</span><span class="sxs-lookup"><span data-stu-id="1689d-142">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="1689d-143">Quando si inizia a eseguire l'aggiornamento a una nuova versione, verrà promosso per l'immissione delle nuove credenziali.</span><span class="sxs-lookup"><span data-stu-id="1689d-143">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="1689d-144">Se si vuole reimpostare solo le credenziali di amministratore del tenant, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="1689d-144">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="1689d-145">Aggiornare più siti a una nuova versione</span><span class="sxs-lookup"><span data-stu-id="1689d-145">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="1689d-146"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="1689d-146"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="1689d-147">Seguire la procedura per l'aggiornamento di un singolo sito, l'aggiornamento di un sito alla volta per ogni sito della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1689d-147">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="1689d-148">Verificare e [convalidare la distribuzione di Cloud Connector](validate-your-cloud-connector-deployment.md) dopo l'aggiornamento di ogni sito.</span><span class="sxs-lookup"><span data-stu-id="1689d-148">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

