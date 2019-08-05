---
title: Registro-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Il cmdlet Register-CcAppliance registra le informazioni sugli apparecchi in un sito PSTN in una configurazione tenant online. Un elettrodomestico deve essere registrato prima che possa essere distribuito e gestito dal servizio di gestione di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 9e15d7b8227bf9ee657d197041056703505ca7c8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190703"
---
# <a name="register-ccappliance"></a><span data-ttu-id="cf8bd-104">Registro-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="cf8bd-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="cf8bd-105">Il cmdlet Register-CcAppliance registra le informazioni sugli apparecchi in un sito PSTN in una configurazione tenant online.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="cf8bd-106">Un elettrodomestico deve essere registrato prima che possa essere distribuito e gestito dal servizio di gestione di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="cf8bd-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="cf8bd-107">Examples</span></span>
<span data-ttu-id="cf8bd-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cf8bd-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="cf8bd-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="cf8bd-109">Example 1</span></span>

<span data-ttu-id="cf8bd-110">L'esempio seguente registra le informazioni sull'appliance corrente in una configurazione del tenant online:</span><span class="sxs-lookup"><span data-stu-id="cf8bd-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="cf8bd-111">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="cf8bd-111">Example 2</span></span>

<span data-ttu-id="cf8bd-112">L'esempio seguente controlla la configurazione per la registrazione localmente senza connettersi a una configurazione del tenant online:</span><span class="sxs-lookup"><span data-stu-id="cf8bd-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="cf8bd-113">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="cf8bd-113">Example 3</span></span>

<span data-ttu-id="cf8bd-114">L'esempio seguente registra l'appliance corrente con il nome "Appliance1" al sito PSTN "Microsoft1":</span><span class="sxs-lookup"><span data-stu-id="cf8bd-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="cf8bd-115">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="cf8bd-115">Detailed Description</span></span>
<span data-ttu-id="cf8bd-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="cf8bd-116"></span></span>

<span data-ttu-id="cf8bd-117">È necessario specificare il nome dell'account di amministratore del tenant e la password.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="cf8bd-118">Usare l'account creato per la gestione di Cloud Connector online.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="cf8bd-119">In versione 1.4.2 e versioni precedenti seguire le istruzioni fornite per specificare la password del certificato esterno, la password di amministratore in modalità provvisoria, la password di amministratore del dominio e la password di amministratore VM.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="cf8bd-120">In versione 2,0 e successive seguire le istruzioni per specificare la password del certificato esterno, la password di CceService e la password di CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="cf8bd-121">Al termine della registrazione, riavviare il servizio di gestione di Cloud Connector e accedere all'account servizi come CceService.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="cf8bd-122">SiteName combinato con il nome di dominio completo esterno del server perimetrale nel file CloudConnector. ini è considerato un'identità del sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-122">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="cf8bd-123">Se per la registrazione di un sito non è stato usato né il nome di dominio completo esterno per SiteName né l'Edge Server, verrà creato un nuovo sito per l'appliance in una configurazione tenant online.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-123">If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration.</span></span> <span data-ttu-id="cf8bd-124">Se viene trovata un'identità del sito PSTN, un sito PSTN utilizzerà questa identità e l'accessorio verrà registrato nel sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-124">If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="cf8bd-125">Nella situazione seguente il cmdlet non riesce e indica che Microsoft1 è già registrato:</span><span class="sxs-lookup"><span data-stu-id="cf8bd-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="cf8bd-126">Nomesito è Microsoft1 e il nome di dominio completo esterno di Edge Server è edgserver1.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="cf8bd-127">Un sito PSTN il cui siteName è Microsoft1 e il nome di dominio completo esterno di Edge Server è edgserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="cf8bd-128">Un sito PSTN il cui siteName è nuovosito e il nome di dominio completo esterno di Edge Server è edgserver1.contoso.com è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="cf8bd-129">Appliancename combinata con l'FQDN di Mediation Server nel file CloudConnector. ini è considerata un'identità Appliance.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-129">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity.</span></span> <span data-ttu-id="cf8bd-130">Se per la registrazione di un dispositivo non è stato usato né l'FQDN di Mediation Server, verrà creato un nuovo dispositivo nella configurazione del tenant online.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-130">If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration.</span></span> <span data-ttu-id="cf8bd-131">Se l'accessorio è già registrato, il cmdlet avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-131">If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="cf8bd-132">Nella situazione seguente il cmdlet non riesce e indica che l'accessorio è già registrato:</span><span class="sxs-lookup"><span data-stu-id="cf8bd-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="cf8bd-133">Appliancename è Appliance1 e il nome di dominio completo di Mediation Server è ms1.vdomain.com.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="cf8bd-134">Nel sito PSTN corrente, se un dispositivo il cui nome è Appliance1 e l'FQDN di Mediation Server è ms.vdomain.com o un accessorio il cui nome è NewAppliance e FQDN di Mediation Server, ms1.vdomain.com è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="cf8bd-135">Parametri</span><span class="sxs-lookup"><span data-stu-id="cf8bd-135">Parameters</span></span>
<span data-ttu-id="cf8bd-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="cf8bd-136"></span></span>

|<span data-ttu-id="cf8bd-137">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="cf8bd-137">**Parameter**</span></span>|<span data-ttu-id="cf8bd-138">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="cf8bd-138">**Required**</span></span>|<span data-ttu-id="cf8bd-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cf8bd-139">**Type**</span></span>|<span data-ttu-id="cf8bd-140">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cf8bd-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf8bd-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="cf8bd-141">SiteName</span></span>  <br/> |<span data-ttu-id="cf8bd-142">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="cf8bd-142">Optional</span></span>  <br/> |<span data-ttu-id="cf8bd-143">System.String</span><span class="sxs-lookup"><span data-stu-id="cf8bd-143">System.String</span></span>  <br/> |<span data-ttu-id="cf8bd-144">Nome del sito PSTN a cui è registrata l'appliance.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-144">PSTN site name to which the appliance is registered.</span></span> <span data-ttu-id="cf8bd-145">Il valore predefinito è il valore SiteName nel file CloudConnector. ini.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-145">Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="cf8bd-146">Appliancename</span><span class="sxs-lookup"><span data-stu-id="cf8bd-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="cf8bd-147">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="cf8bd-147">Optional</span></span>  <br/> |<span data-ttu-id="cf8bd-148">System.String</span><span class="sxs-lookup"><span data-stu-id="cf8bd-148">System.String</span></span>  <br/> |<span data-ttu-id="cf8bd-149">Nome dell'appliance corrente.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-149">Name of the current appliance.</span></span> <span data-ttu-id="cf8bd-150">Il valore predefinito è il nome del computer del server host.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-150">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="cf8bd-151">Locale</span><span class="sxs-lookup"><span data-stu-id="cf8bd-151">Local</span></span>  <br/> |<span data-ttu-id="cf8bd-152">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="cf8bd-152">Optional</span></span>  <br/> |<span data-ttu-id="cf8bd-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="cf8bd-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="cf8bd-154">Verificare le configurazioni per la registrazione localmente senza connettersi alla configurazione del tenant online.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="cf8bd-155">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="cf8bd-155">Input Types</span></span>
<span data-ttu-id="cf8bd-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cf8bd-156"></span></span>

<span data-ttu-id="cf8bd-157">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-157">None.</span></span> <span data-ttu-id="cf8bd-158">Il cmdlet Register-CcAppliance non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="cf8bd-158">The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="cf8bd-159">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="cf8bd-159">Return Types</span></span>
<span data-ttu-id="cf8bd-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cf8bd-160"></span></span>

<span data-ttu-id="cf8bd-161">Nessuno</span><span class="sxs-lookup"><span data-stu-id="cf8bd-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cf8bd-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf8bd-162">See also</span></span>
<span data-ttu-id="cf8bd-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cf8bd-163"></span></span>

[<span data-ttu-id="cf8bd-164">Annullamento della registrazione-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="cf8bd-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="cf8bd-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="cf8bd-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="cf8bd-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="cf8bd-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="cf8bd-167">Disinstallare-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="cf8bd-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

