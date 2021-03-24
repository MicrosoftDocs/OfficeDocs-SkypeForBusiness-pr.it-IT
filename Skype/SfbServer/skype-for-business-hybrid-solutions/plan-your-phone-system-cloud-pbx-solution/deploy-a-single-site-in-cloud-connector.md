---
title: Distribuire un sito singolo in Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Informazioni sulla distribuzione di un singolo sito PSTN in Cloud Connector Edition.
ms.openlocfilehash: 32c981b0f7de3d596dc25c3336000871db9fee65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094834"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="1dae2-103">Distribuire un sito singolo in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1dae2-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="1dae2-104">Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="1dae2-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="1dae2-105">Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="1dae2-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="1dae2-106">Informazioni sulla distribuzione di un singolo sito PSTN in Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="1dae2-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="1dae2-107">È possibile distribuire Skype for Business Cloud Connector Edition con o senza il supporto della disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="1dae2-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="1dae2-108">Se si desidera abilitare l'ha, è necessario distribuire due o più appliance all'interno di un sito.</span><span class="sxs-lookup"><span data-stu-id="1dae2-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="1dae2-109">È inoltre possibile convertire un'appliance esistente per supportare l'ha dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1dae2-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="1dae2-110">Distribuire il primo appliance Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="1dae2-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="1dae2-111">Per distribuire la prima appliance in un sito, aprire una console di PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'appliance:</span><span class="sxs-lookup"><span data-stu-id="1dae2-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="1dae2-112">Seguire le istruzioni per specificare il nome e la password dell'account amministratore tenant.</span><span class="sxs-lookup"><span data-stu-id="1dae2-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="1dae2-113">Utilizzare l'account creato per la gestione online del connettore cloud.</span><span class="sxs-lookup"><span data-stu-id="1dae2-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="1dae2-114">Seguire inoltre le istruzioni per fornire la password del certificato esterno, la password di amministratore in modalità provvisoria, la password di amministratore di dominio e la password di amministratore della macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="1dae2-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="1dae2-115">Nella versione 1.4.2 e versioni precedenti, seguire anche le istruzioni per fornire la password del certificato esterno, la password di amministratore in modalità provvisoria, la password di amministratore di dominio e la password di amministratore della macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="1dae2-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="1dae2-116">Nella versione 2.0 e successive, seguire anche le istruzioni per fornire la password del certificato esterno, la password CceService e la password CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="1dae2-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="1dae2-117">Per avviare l'installazione, aprire una console di PowerShell come amministratore ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="1dae2-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="1dae2-118">Aggiungere un'appliance a un sito esistente</span><span class="sxs-lookup"><span data-stu-id="1dae2-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="1dae2-119">È possibile estendere un sito Cloud Connector esistente per supportare l'ha aggiungendo ulteriori appliance al sito.</span><span class="sxs-lookup"><span data-stu-id="1dae2-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="1dae2-120">Seguire i passaggi per preparare l'appliance Cloud Connector come descritto in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span><span class="sxs-lookup"><span data-stu-id="1dae2-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="1dae2-121">Tenere presente che alcuni passaggi sono necessari solo per la prima appliance della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1dae2-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="1dae2-122">Verificare che la directory del sito esista e che sia configurata correttamente per il supporto dell'ha.</span><span class="sxs-lookup"><span data-stu-id="1dae2-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="1dae2-123">Eseguire il cmdlet seguente solo nel server host appena aggiunto per aggiornare le informazioni sulla topologia nella configurazione dell'organizzazione di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="1dae2-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="1dae2-124">Se si desidera aggiungere più appliance contemporaneamente, eseguire il cmdlet in ogni server host appena aggiunto uno alla volta:</span><span class="sxs-lookup"><span data-stu-id="1dae2-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="1dae2-125">Aggiornare la topologia nelle appliance esistenti eseguendo il cmdlet seguente in ogni server host.</span><span class="sxs-lookup"><span data-stu-id="1dae2-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="1dae2-126">Eseguire il cmdlet solo nelle appliance esistenti.</span><span class="sxs-lookup"><span data-stu-id="1dae2-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="1dae2-127">Eseguire il cmdlet seguente solo nei server host appena aggiunti.</span><span class="sxs-lookup"><span data-stu-id="1dae2-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="1dae2-128">Non eseguire questo cmdlet nell'appliance esistente.</span><span class="sxs-lookup"><span data-stu-id="1dae2-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="1dae2-129">Se si desidera aggiungere più appliance contemporaneamente, eseguire il cmdlet in ogni server host appena aggiunto uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="1dae2-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="1dae2-130">Se la directory del sito è stata impostata su un percorso di cartella locale, è necessario definire una condivisione file per questa cartella e utilizzare un percorso UNC per la directory dei siti nel nuovo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1dae2-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="1dae2-131">È possibile lasciare la prima directory del sito dell'appliance con il percorso locale o modificarla per utilizzare il percorso UNC per la condivisione nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="1dae2-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="1dae2-132">Se il percorso della directory del sito condiviso cambia, tutte le appliance installate in precedenza devono essere disinstallate e quindi reinstallate.</span><span class="sxs-lookup"><span data-stu-id="1dae2-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="1dae2-133">> Importante: la password sia per l'account CceService che per l'account CABackupFile deve essere la stessa in tutte le appliance distribuite all'interno del sito, in modo che le appliance possano accedere alla condivisione della directory del sito e al file di backup della CA crittografato nella directory dei siti.</span><span class="sxs-lookup"><span data-stu-id="1dae2-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="1dae2-134">Rimuovere un'appliance da un sito esistente</span><span class="sxs-lookup"><span data-stu-id="1dae2-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="1dae2-135">Se si desidera rimuovere un'appliance da un sito esistente:</span><span class="sxs-lookup"><span data-stu-id="1dae2-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="1dae2-136">Eseguire il cmdlet seguente solo sui server host che si desidera rimuovere dal sito per aggiornare le informazioni sulla topologia nella configurazione dell'organizzazione di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="1dae2-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="1dae2-137">Eseguire il cmdlet seguente solo sui server host da cui si desidera rimuovere tutte le macchine virtuali dell'appliance.</span><span class="sxs-lookup"><span data-stu-id="1dae2-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```