---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Il cmdlet Install-CcAppliance installa l'accessorio Cloud Connector Edition di Skype for business, tra cui le macchine virtuali AD, Central Management store, Mediation Server e Edge Server nel server host.
ms.openlocfilehash: cccf500c6506c8ba3459631d5c823940907ad213
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003326"
---
# <a name="install-ccappliance"></a><span data-ttu-id="fe496-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fe496-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="fe496-104">Il cmdlet Install-CcAppliance installa l'accessorio Cloud Connector Edition di Skype for business, tra cui le macchine virtuali AD, Central Management store, Mediation Server e Edge Server nel server host.</span><span class="sxs-lookup"><span data-stu-id="fe496-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="fe496-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="fe496-105">Examples</span></span>
<span data-ttu-id="fe496-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fe496-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="fe496-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="fe496-107">Example 1</span></span>

<span data-ttu-id="fe496-108">L'esempio seguente installa un nuovo accessorio Cloud Connector nel server host:</span><span class="sxs-lookup"><span data-stu-id="fe496-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="fe496-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="fe496-109">Example 2</span></span>

<span data-ttu-id="fe496-110">L'esempio seguente aggiorna Cloud Connector alla versione più recente:</span><span class="sxs-lookup"><span data-stu-id="fe496-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="fe496-111">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="fe496-111">Example 3</span></span>

<span data-ttu-id="fe496-112">L'esempio seguente rimuove tutte le credenziali di Cloud Connector memorizzate nella cache nel server host, chiede all'utente di specificare di nuovo tutte le informazioni sulle credenziali e quindi installa Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="fe496-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="fe496-113">Esempio 4</span><span class="sxs-lookup"><span data-stu-id="fe496-113">Example 4</span></span>

<span data-ttu-id="fe496-114">L'esempio seguente mostra tutti i passaggi di distribuzione nella console di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fe496-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="fe496-115">Il parametro-ShowStepsOnly è solo per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="fe496-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="fe496-116">Esempio 5</span><span class="sxs-lookup"><span data-stu-id="fe496-116">Example 5</span></span>

<span data-ttu-id="fe496-117">L'esempio seguente genera i file di configurazione per ogni passaggio di distribuzione nel server host.</span><span class="sxs-lookup"><span data-stu-id="fe496-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="fe496-118">I file di configurazione vengono salvati \<nella\>cartella\\ ApplianceRoot \Instances\><-default\ExportedConfig nel server host:</span><span class="sxs-lookup"><span data-stu-id="fe496-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```powershell
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="fe496-119">Per determinare la radice dell'accessorio, eseguire il cmdlet Get-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="fe496-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="fe496-120">Esempio 6</span><span class="sxs-lookup"><span data-stu-id="fe496-120">Example 6</span></span>

<span data-ttu-id="fe496-121">Nell'esempio seguente, Cloud Connector esegue i passaggi di distribuzione 1, 2 e 3 per creare switch virtuali, creare una macchina virtuale AD e installare il servizio del dominio nel server degli annunci.</span><span class="sxs-lookup"><span data-stu-id="fe496-121">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server.</span></span> <span data-ttu-id="fe496-122">Il passaggio viene saltato se il passaggio è già stato eseguito:</span><span class="sxs-lookup"><span data-stu-id="fe496-122">It skips the step if the step has already been executed:</span></span>
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="fe496-123">Il parametro SkipExistingObjects deve essere usato insieme al parametro Steps.</span><span class="sxs-lookup"><span data-stu-id="fe496-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe496-124">Il parametro Steps è solo per scopi di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="fe496-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="fe496-125">Non usare questo parametro per distribuire un dispositivo o per aggiornare un dispositivo in servizio.</span><span class="sxs-lookup"><span data-stu-id="fe496-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="fe496-126">Per determinare i passaggi della distribuzione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fe496-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="fe496-127">Installare-CcAppliance-ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="fe496-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="fe496-128">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="fe496-128">Detailed Description</span></span>
<span data-ttu-id="fe496-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fe496-129"></span></span>

<span data-ttu-id="fe496-130">Il cmdlet Install-CcAppliance viene usato per distribuire Cloud Connector in un nuovo dispositivo o per aggiornare un dispositivo esistente alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="fe496-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="fe496-131">Se si dispone di un nuovo dispositivo, leggere prima di tutto preparare l'ambiente per Cloud Connector, eseguire il cmdlet Register-CcAppliance per registrare l'accessorio e quindi eseguire il cmdlet Install-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="fe496-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="fe496-132">Per altre informazioni, vedere [distribuire un singolo sito nel Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e [distribuire più siti in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="fe496-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="fe496-133">Se si ha una distribuzione di Cloud Connector esistente e si vuole eseguire l'aggiornamento, seguire le istruzioni visualizzate in [eseguire l'aggiornamento a una nuova versione di Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="fe496-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="fe496-134">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe496-134">Parameters</span></span>
<span data-ttu-id="fe496-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fe496-135"></span></span>

|<span data-ttu-id="fe496-136">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="fe496-136">**Parameter**</span></span>|<span data-ttu-id="fe496-137">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="fe496-137">**Required**</span></span>|<span data-ttu-id="fe496-138">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fe496-138">**Type**</span></span>|<span data-ttu-id="fe496-139">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fe496-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fe496-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="fe496-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="fe496-141">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="fe496-141">Optional</span></span>  <br/> |<span data-ttu-id="fe496-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fe496-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="fe496-143">Genera file di configurazione per ogni passaggio di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fe496-143">Generate configuration files for each deployment step.</span></span> <span data-ttu-id="fe496-144">Questo parametro è solo per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="fe496-144">This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="fe496-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="fe496-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="fe496-146">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="fe496-146">Optional</span></span>  <br/> |<span data-ttu-id="fe496-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fe496-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="fe496-148">Visualizzare solo i nomi dei passaggi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fe496-148">Display deployment step names only.</span></span> <span data-ttu-id="fe496-149">Questo parametro è solo per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="fe496-149">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="fe496-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="fe496-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="fe496-151">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="fe496-151">Optional</span></span>  <br/> |<span data-ttu-id="fe496-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fe496-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="fe496-153">Questo parametro deve essere usato insieme al parametro Steps.</span><span class="sxs-lookup"><span data-stu-id="fe496-153">This parameter must be used in conjunction with the Steps parameter.</span></span> <span data-ttu-id="fe496-154">Questo parametro è solo per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="fe496-154">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="fe496-155">Passaggi</span><span class="sxs-lookup"><span data-stu-id="fe496-155">Steps</span></span>  <br/> |<span data-ttu-id="fe496-156">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="fe496-156">Optional</span></span>  <br/> |<span data-ttu-id="fe496-157">System. Array</span><span class="sxs-lookup"><span data-stu-id="fe496-157">System.Array</span></span>  <br/> |<span data-ttu-id="fe496-158">Eseguire la procedura di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fe496-158">Run the deployment steps.</span></span> <span data-ttu-id="fe496-159">Questo parametro è solo per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="fe496-159">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="fe496-160">Upgrade</span><span class="sxs-lookup"><span data-stu-id="fe496-160">Upgrade</span></span>  <br/> |<span data-ttu-id="fe496-161">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="fe496-161">Optional</span></span>  <br/> |<span data-ttu-id="fe496-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fe496-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="fe496-163">Aggiornare il connettore cloud esistente alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="fe496-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="fe496-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="fe496-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="fe496-165">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="fe496-165">Optional</span></span>  <br/> |<span data-ttu-id="fe496-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fe496-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="fe496-167">Rimuovere tutte le credenziali del connettore cloud nella cache.</span><span class="sxs-lookup"><span data-stu-id="fe496-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="fe496-168">Richiedi all'utente di specificare le nuove informazioni sulle credenziali per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="fe496-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="fe496-169">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="fe496-169">Input Types</span></span>
<span data-ttu-id="fe496-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fe496-170"></span></span>

<span data-ttu-id="fe496-171">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fe496-171">None.</span></span> <span data-ttu-id="fe496-172">Il cmdlet Install-CcAppliance non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="fe496-172">The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fe496-173">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="fe496-173">Return Types</span></span>
<span data-ttu-id="fe496-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fe496-174"></span></span>

<span data-ttu-id="fe496-175">Nessuno</span><span class="sxs-lookup"><span data-stu-id="fe496-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fe496-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe496-176">See also</span></span>
<span data-ttu-id="fe496-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fe496-177"></span></span>

[<span data-ttu-id="fe496-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fe496-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="fe496-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fe496-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="fe496-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fe496-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="fe496-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fe496-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

