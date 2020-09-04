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
ms.openlocfilehash: 327fc4e687377f5f1338bea2f623b526511a2992
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358932"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="2a627-103">Distribuire un sito singolo in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="2a627-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="2a627-104">Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="2a627-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="2a627-105">Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="2a627-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="2a627-106">Informazioni sulla distribuzione di un singolo sito PSTN in Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="2a627-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="2a627-107">È possibile distribuire Skype for Business Cloud Connector Edition con o senza il supporto per la disponibilità elevata (HA).</span><span class="sxs-lookup"><span data-stu-id="2a627-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="2a627-108">Se si desidera abilitare l'HA, è necessario distribuire due o più dispositivi all'interno di un sito.</span><span class="sxs-lookup"><span data-stu-id="2a627-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="2a627-109">È inoltre possibile convertire un dispositivo esistente per il supporto di HA dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2a627-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="2a627-110">Distribuire il primo accessorio di Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="2a627-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="2a627-111">Per distribuire il primo dispositivo in un sito, aprire una console PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'accessorio:</span><span class="sxs-lookup"><span data-stu-id="2a627-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="2a627-112">Seguire le istruzioni per fornire il nome e la password dell'account di amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="2a627-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="2a627-113">Utilizzare l'account creato per la gestione di Cloud Connector online.</span><span class="sxs-lookup"><span data-stu-id="2a627-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="2a627-114">Inoltre, seguire le istruzioni per fornire la password del certificato esterno, la password di amministratore della modalità provvisoria, la password di amministratore del dominio e la password di amministratore VM.</span><span class="sxs-lookup"><span data-stu-id="2a627-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="2a627-115">In Release 1.4.2 e versioni precedenti, seguire le istruzioni per fornire la password del certificato esterno, la password di amministratore della modalità provvisoria, la password di amministratore del dominio e la password di amministratore della VM.</span><span class="sxs-lookup"><span data-stu-id="2a627-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="2a627-116">Nella versione 2,0 e versioni successive, seguire le istruzioni per fornire la password del certificato esterno, la password di CceService e la password di CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="2a627-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="2a627-117">Per avviare l'installazione, aprire una console di PowerShell come amministratore ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2a627-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="2a627-118">Aggiungere un dispositivo a un sito esistente</span><span class="sxs-lookup"><span data-stu-id="2a627-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="2a627-119">È possibile estendere un sito del connettore cloud esistente per il supporto di HA aggiungendo altri dispositivi al sito.</span><span class="sxs-lookup"><span data-stu-id="2a627-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="2a627-120">Seguire la procedura per preparare l'accessorio Cloud Connector, come descritto in [Prepare your Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md).</span><span class="sxs-lookup"><span data-stu-id="2a627-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="2a627-121">Tenere presente che alcuni passaggi sono necessari solo per il primo dispositivo della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2a627-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="2a627-122">Verificare che la directory del sito esista e sia configurata correttamente per il supporto di HA.</span><span class="sxs-lookup"><span data-stu-id="2a627-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="2a627-123">Eseguire il seguente cmdlet solo nel server host appena aggiunto per aggiornare le informazioni sulla topologia nella configurazione dell'organizzazione di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a627-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="2a627-124">Se si desidera aggiungere più dispositivi contemporaneamente, eseguire il cmdlet su ogni server host appena aggiunto uno per uno:</span><span class="sxs-lookup"><span data-stu-id="2a627-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="2a627-125">Aggiornare la topologia negli apparecchi esistenti eseguendo il cmdlet seguente in ogni server host.</span><span class="sxs-lookup"><span data-stu-id="2a627-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="2a627-126">Eseguire solo il cmdlet negli elettrodomestici esistenti.</span><span class="sxs-lookup"><span data-stu-id="2a627-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="2a627-127">Eseguire il seguente cmdlet solo sui server host appena aggiunti.</span><span class="sxs-lookup"><span data-stu-id="2a627-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="2a627-128">Non eseguire questo cmdlet sull'accessorio esistente.</span><span class="sxs-lookup"><span data-stu-id="2a627-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="2a627-129">Se si desidera aggiungere più dispositivi contemporaneamente, eseguire il cmdlet su ogni server host appena aggiunto uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="2a627-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="2a627-130">Se la directory del sito è stata impostata su un percorso della cartella locale, è necessario definire una condivisione file per la cartella e utilizzare un percorso UNC per la directory del sito nel nuovo accessorio.</span><span class="sxs-lookup"><span data-stu-id="2a627-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="2a627-131">È possibile lasciare la directory del sito del primo dispositivo con il percorso locale o modificarla in modo da utilizzare il percorso UNC per la condivisione nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="2a627-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="2a627-132">Se il percorso della directory del sito condiviso cambia, è necessario disinstallare tutti gli apparecchi installati in precedenza e quindi reinstallarli.</span><span class="sxs-lookup"><span data-stu-id="2a627-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="2a627-133">> importante: la password per l'account CceService e l'account CABackupFile deve essere la stessa su tutti gli strumenti distribuiti all'interno del sito, in modo che gli strumenti possano accedere alla condivisione directory del sito e al file di backup della CA crittografata nella directory del sito.</span><span class="sxs-lookup"><span data-stu-id="2a627-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="2a627-134">Rimozione di un dispositivo da un sito esistente</span><span class="sxs-lookup"><span data-stu-id="2a627-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="2a627-135">Se si desidera rimuovere un dispositivo da un sito esistente:</span><span class="sxs-lookup"><span data-stu-id="2a627-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="2a627-136">Eseguire il seguente cmdlet solo nei server host che si desidera rimuovere dal sito per aggiornare le informazioni sulla topologia nella configurazione dell'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a627-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="2a627-137">Eseguire il seguente cmdlet solo nei server host da cui si desidera rimuovere tutte le macchine virtuali dell'accessorio.</span><span class="sxs-lookup"><span data-stu-id="2a627-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


