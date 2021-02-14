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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Il cmdlet Install-CcAppliance installa l'appliance Skype for Business Cloud Connector Edition, incluse le macchine virtuali AD, Archivio di gestione centrale, Mediation Server e Edge Server, nel server host.
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799876"
---
# <a name="install-ccappliance"></a><span data-ttu-id="4e6a6-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="4e6a6-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="4e6a6-104">Il cmdlet Install-CcAppliance installa l'appliance Skype for Business Cloud Connector Edition, incluse le macchine virtuali AD, Archivio di gestione centrale, Mediation Server e Edge Server, nel server host.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="4e6a6-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="4e6a6-105">Examples</span></span>
<span data-ttu-id="4e6a6-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4e6a6-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="4e6a6-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="4e6a6-107">Example 1</span></span>

<span data-ttu-id="4e6a6-108">Nell'esempio seguente viene installato un nuovo dispositivo Cloud Connector nel server host:</span><span class="sxs-lookup"><span data-stu-id="4e6a6-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="4e6a6-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="4e6a6-109">Example 2</span></span>

<span data-ttu-id="4e6a6-110">Nell'esempio seguente cloud connector viene aggiornato alla versione più recente:</span><span class="sxs-lookup"><span data-stu-id="4e6a6-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="4e6a6-111">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="4e6a6-111">Example 3</span></span>

<span data-ttu-id="4e6a6-112">Nell'esempio seguente vengono rimosse tutte le credenziali del connettore cloud memorizzate nella cache del server host, viene richiesto all'utente di specificare nuovamente tutte le informazioni sulle credenziali e quindi viene installato Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="4e6a6-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="4e6a6-113">Esempio 4</span><span class="sxs-lookup"><span data-stu-id="4e6a6-113">Example 4</span></span>

<span data-ttu-id="4e6a6-114">Nell'esempio seguente vengono visualizzati tutti i passaggi di distribuzione nella console di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4e6a6-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="4e6a6-115">Il parametro -ShowStepsOnly è solo per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="4e6a6-116">Esempio 5</span><span class="sxs-lookup"><span data-stu-id="4e6a6-116">Example 5</span></span>

<span data-ttu-id="4e6a6-117">Nell'esempio seguente vengono generati file di configurazione per ogni passaggio di distribuzione nel server host.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="4e6a6-118">I file di configurazione vengono salvati nella cartella \< ApplianceRoot \> \Instances \\<Version \> -default\ExportedConfig nel server host:</span><span class="sxs-lookup"><span data-stu-id="4e6a6-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```powershell
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="4e6a6-119">Per determinare la radice dell'applicazione, eseguire Get-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="4e6a6-120">Esempio 6</span><span class="sxs-lookup"><span data-stu-id="4e6a6-120">Example 6</span></span>

<span data-ttu-id="4e6a6-121">Nell'esempio seguente Cloud Connector esegue i passaggi di distribuzione 1, 2 e 3 per creare commutatori virtuali, creare una macchina virtuale AD e installare il servizio di dominio nel server AD.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-121">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server.</span></span> <span data-ttu-id="4e6a6-122">Ignora il passaggio se il passaggio è già stato eseguito:</span><span class="sxs-lookup"><span data-stu-id="4e6a6-122">It skips the step if the step has already been executed:</span></span>
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="4e6a6-123">Il parametro SkipExistingObjects deve essere utilizzato insieme al parametro Steps.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4e6a6-124">Il parametro Steps ha solo scopo di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="4e6a6-125">Non utilizzare questo parametro per distribuire un'applicazione o per aggiornare un'applicazione in servizio.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="4e6a6-126">Per determinare i passaggi della distribuzione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4e6a6-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="4e6a6-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="4e6a6-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="4e6a6-128">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="4e6a6-128">Detailed Description</span></span>
<span data-ttu-id="4e6a6-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4e6a6-129"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="4e6a6-130">Il cmdlet Install-CcAppliance viene utilizzato per distribuire Cloud Connector a un nuovo dispositivo o per aggiornare un'applicazione esistente alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="4e6a6-131">Se si dispone di un nuovo dispositivo, leggere prima Preparare l'ambiente per Cloud Connector, eseguire il cmdlet Register-CcAppliance per registrare l'appliance e quindi eseguire il cmdlet Install-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="4e6a6-132">Per ulteriori informazioni, vedere [Distribuire un singolo sito in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e Distribuire più siti in Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="4e6a6-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="4e6a6-133">Se si dispone di una distribuzione esistente di Cloud Connector e si desidera eseguire l'aggiornamento, seguire le istruzioni in Eseguire l'aggiornamento [a una nuova versione di Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="4e6a6-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="4e6a6-134">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e6a6-134">Parameters</span></span>
<span data-ttu-id="4e6a6-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4e6a6-135"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="4e6a6-136">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="4e6a6-136">**Parameter**</span></span>|<span data-ttu-id="4e6a6-137">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="4e6a6-137">**Required**</span></span>|<span data-ttu-id="4e6a6-138">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4e6a6-138">**Type**</span></span>|<span data-ttu-id="4e6a6-139">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4e6a6-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4e6a6-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="4e6a6-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="4e6a6-141">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="4e6a6-141">Optional</span></span>  <br/> |<span data-ttu-id="4e6a6-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="4e6a6-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="4e6a6-143">Generare i file di configurazione per ogni passaggio di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-143">Generate configuration files for each deployment step.</span></span> <span data-ttu-id="4e6a6-144">Questo parametro è solo per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-144">This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="4e6a6-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="4e6a6-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="4e6a6-146">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="4e6a6-146">Optional</span></span>  <br/> |<span data-ttu-id="4e6a6-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="4e6a6-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="4e6a6-148">Visualizza solo i nomi dei passaggi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-148">Display deployment step names only.</span></span> <span data-ttu-id="4e6a6-149">Questo parametro è solo per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-149">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="4e6a6-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="4e6a6-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="4e6a6-151">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="4e6a6-151">Optional</span></span>  <br/> |<span data-ttu-id="4e6a6-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="4e6a6-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="4e6a6-153">Questo parametro deve essere utilizzato insieme al parametro Steps.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-153">This parameter must be used in conjunction with the Steps parameter.</span></span> <span data-ttu-id="4e6a6-154">Questo parametro è solo per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-154">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="4e6a6-155">Passaggi</span><span class="sxs-lookup"><span data-stu-id="4e6a6-155">Steps</span></span>  <br/> |<span data-ttu-id="4e6a6-156">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="4e6a6-156">Optional</span></span>  <br/> |<span data-ttu-id="4e6a6-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="4e6a6-157">System.Array</span></span>  <br/> |<span data-ttu-id="4e6a6-158">Eseguire i passaggi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-158">Run the deployment steps.</span></span> <span data-ttu-id="4e6a6-159">Questo parametro è solo per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-159">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="4e6a6-160">Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="4e6a6-160">Upgrade</span></span>  <br/> |<span data-ttu-id="4e6a6-161">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="4e6a6-161">Optional</span></span>  <br/> |<span data-ttu-id="4e6a6-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="4e6a6-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="4e6a6-163">Aggiornare il connettore cloud esistente alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="4e6a6-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="4e6a6-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="4e6a6-165">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="4e6a6-165">Optional</span></span>  <br/> |<span data-ttu-id="4e6a6-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="4e6a6-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="4e6a6-167">Rimuovere tutte le credenziali del connettore cloud nella cache.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="4e6a6-168">Chiedere all'utente di specificare nuove informazioni sulle credenziali per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="4e6a6-169">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="4e6a6-169">Input Types</span></span>
<span data-ttu-id="4e6a6-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4e6a6-170"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="4e6a6-171">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-171">None.</span></span> <span data-ttu-id="4e6a6-172">Il cmdlet Install-CcAppliance non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="4e6a6-172">The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4e6a6-173">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="4e6a6-173">Return Types</span></span>
<span data-ttu-id="4e6a6-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4e6a6-174"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="4e6a6-175">None</span><span class="sxs-lookup"><span data-stu-id="4e6a6-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4e6a6-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e6a6-176">See also</span></span>
<span data-ttu-id="4e6a6-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4e6a6-177"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="4e6a6-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="4e6a6-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="4e6a6-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="4e6a6-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="4e6a6-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="4e6a6-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="4e6a6-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="4e6a6-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

