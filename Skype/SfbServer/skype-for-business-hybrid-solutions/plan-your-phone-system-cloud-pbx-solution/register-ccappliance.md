---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Il Register-CcAppliance consente di registrare le informazioni sull'applicazione in un sito PSTN in una configurazione tenant online. Un'applicazione deve essere registrata prima di poter essere distribuita e gestita dal servizio di gestione Skype for Business Cloud Connector Edition.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824302"
---
# <a name="register-ccappliance"></a><span data-ttu-id="65436-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="65436-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="65436-105">Il Register-CcAppliance consente di registrare le informazioni sull'applicazione in un sito PSTN in una configurazione tenant online.</span><span class="sxs-lookup"><span data-stu-id="65436-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="65436-106">Un'applicazione deve essere registrata prima di poter essere distribuita e gestita dal servizio di gestione Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="65436-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="65436-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="65436-107">Examples</span></span>
<span data-ttu-id="65436-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="65436-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="65436-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="65436-109">Example 1</span></span>

<span data-ttu-id="65436-110">Nell'esempio seguente vengono registrate le informazioni sull'applicazione corrente in una configurazione tenant online:</span><span class="sxs-lookup"><span data-stu-id="65436-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="65436-111">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="65436-111">Example 2</span></span>

<span data-ttu-id="65436-112">Nell'esempio seguente viene verificata la configurazione per la registrazione in locale senza connettersi a una configurazione tenant online:</span><span class="sxs-lookup"><span data-stu-id="65436-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="65436-113">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="65436-113">Example 3</span></span>

<span data-ttu-id="65436-114">Nell'esempio seguente viene registrato l'applicazione corrente con il nome "Appliance1" nel sito PSTN "Site1":</span><span class="sxs-lookup"><span data-stu-id="65436-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="65436-115">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="65436-115">Detailed Description</span></span>
<span data-ttu-id="65436-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="65436-116"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="65436-117">È necessario specificare il nome e la password dell'account di amministratore tenant.</span><span class="sxs-lookup"><span data-stu-id="65436-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="65436-118">Utilizzare l'account creato per la gestione online di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="65436-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="65436-119">Nella versione 1.4.2 e versioni precedenti, seguire le istruzioni per fornire la password del certificato esterno, la password di amministratore in modalità provvisoria, la password di amministratore del dominio e la password di amministratore della macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="65436-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="65436-120">Nella versione 2.0 e successive, seguire le istruzioni per fornire la password del certificato esterno, la password CceService e la password CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="65436-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="65436-121">Al termine della registrazione, riavviare il servizio di gestione cloud Connector e accedere ai servizi come account CceService.</span><span class="sxs-lookup"><span data-stu-id="65436-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="65436-122">SiteName in combinazione con l'FQDN esterno del server perimetrale nel file CloudConnector.ini viene considerato un'identità del sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="65436-122">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="65436-123">Se per registrare un sito non sono stati utilizzati né siteName né FQDN esterno del server perimetrale, verrà creato un nuovo sito per questo appliance in una configurazione tenant online.</span><span class="sxs-lookup"><span data-stu-id="65436-123">If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration.</span></span> <span data-ttu-id="65436-124">Se viene trovata un'identità del sito PSTN, tale identità verrà utilizzata da un sito PSTN e l'applicazione verrà registrata in questo sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="65436-124">If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="65436-125">Nella situazione seguente, il cmdlet avrà esito negativo e indicherà che Site1 è già registrato:</span><span class="sxs-lookup"><span data-stu-id="65436-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="65436-126">SiteName è Site1 e l'FQDN esterno del server perimetrale è edgserver1.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="65436-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="65436-127">Un sito PSTN il cui SiteName è Site1 e il nome di dominio completo esterno del server perimetrale è edgserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="65436-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="65436-128">Un sito PSTN il cui SiteName è NewSite e l'FQDN esterno del server perimetrale edgserver1.contoso.com è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="65436-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="65436-129">ApplianceName in combinazione con l'FQDN di Mediation Server CloudConnector.ini file viene considerato un'identità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="65436-129">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity.</span></span> <span data-ttu-id="65436-130">Se per registrare un'applicazione non è stato utilizzato né il nome di dominio completo di ApplianceName né il Mediation Server, verrà creato un nuovo appliance nella configurazione tenant online.</span><span class="sxs-lookup"><span data-stu-id="65436-130">If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration.</span></span> <span data-ttu-id="65436-131">Se l'applicazione è già registrata, il cmdlet avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="65436-131">If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="65436-132">Nella situazione seguente, il cmdlet avrà esito negativo e indicherà che l'applicazione è già registrata:</span><span class="sxs-lookup"><span data-stu-id="65436-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="65436-133">ApplianceName è Appliance1 e l'FQDN del Mediation Server ms1.vdomain.com.</span><span class="sxs-lookup"><span data-stu-id="65436-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="65436-134">Nel sito PSTN corrente, se è stato registrato un dispositivo il cui nome di dominio completo Appliance1 e Mediation Server è ms.vdomain.com o un'applicazione il cui nome è NewAppliance e mediation server FQDN ms1.vdomain.com è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="65436-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="65436-135">Parametri</span><span class="sxs-lookup"><span data-stu-id="65436-135">Parameters</span></span>
<span data-ttu-id="65436-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="65436-136"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="65436-137">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="65436-137">**Parameter**</span></span>|<span data-ttu-id="65436-138">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="65436-138">**Required**</span></span>|<span data-ttu-id="65436-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="65436-139">**Type**</span></span>|<span data-ttu-id="65436-140">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="65436-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65436-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="65436-141">SiteName</span></span>  <br/> |<span data-ttu-id="65436-142">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="65436-142">Optional</span></span>  <br/> |<span data-ttu-id="65436-143">System.String</span><span class="sxs-lookup"><span data-stu-id="65436-143">System.String</span></span>  <br/> |<span data-ttu-id="65436-144">Nome del sito PSTN in cui è registrato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="65436-144">PSTN site name to which the appliance is registered.</span></span> <span data-ttu-id="65436-145">Il valore predefinito è SiteName nel file CloudConnector.ini locale.</span><span class="sxs-lookup"><span data-stu-id="65436-145">Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="65436-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="65436-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="65436-147">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="65436-147">Optional</span></span>  <br/> |<span data-ttu-id="65436-148">System.String</span><span class="sxs-lookup"><span data-stu-id="65436-148">System.String</span></span>  <br/> |<span data-ttu-id="65436-149">Nome dell'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="65436-149">Name of the current appliance.</span></span> <span data-ttu-id="65436-150">Il valore predefinito è il nome computer del server host.</span><span class="sxs-lookup"><span data-stu-id="65436-150">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="65436-151">Locale</span><span class="sxs-lookup"><span data-stu-id="65436-151">Local</span></span>  <br/> |<span data-ttu-id="65436-152">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="65436-152">Optional</span></span>  <br/> |<span data-ttu-id="65436-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="65436-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="65436-154">Controllare le configurazioni per la registrazione in locale senza connettersi alla configurazione del tenant online.</span><span class="sxs-lookup"><span data-stu-id="65436-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="65436-155">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="65436-155">Input Types</span></span>
<span data-ttu-id="65436-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="65436-156"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="65436-157">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="65436-157">None.</span></span> <span data-ttu-id="65436-158">Il cmdlet Register-CcAppliance non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="65436-158">The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="65436-159">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="65436-159">Return Types</span></span>
<span data-ttu-id="65436-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="65436-160"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="65436-161">None</span><span class="sxs-lookup"><span data-stu-id="65436-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="65436-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65436-162">See also</span></span>
<span data-ttu-id="65436-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="65436-163"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="65436-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="65436-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="65436-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="65436-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="65436-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="65436-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="65436-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="65436-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

