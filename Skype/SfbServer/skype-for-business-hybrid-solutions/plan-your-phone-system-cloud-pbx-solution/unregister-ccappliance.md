---
title: Annullamento della registrazione-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Il cmdlet Unregister-CcAppliance Annulla la registrazione dell'appliance di Skype for Business Cloud Connector corrente da un sito PSTN nella configurazione del tenant online.
ms.openlocfilehash: fafe374371cd01b2ec7c67ade89dd2a905e16d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190586"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="0fa27-103">Annullamento della registrazione-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0fa27-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="0fa27-104">Il cmdlet Unregister-CcAppliance Annulla la registrazione dell'appliance di Skype for Business Cloud Connector corrente da un sito PSTN nella configurazione del tenant online.</span><span class="sxs-lookup"><span data-stu-id="0fa27-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="0fa27-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="0fa27-105">Examples</span></span>
<span data-ttu-id="0fa27-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa27-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="0fa27-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="0fa27-107">Example 1</span></span>

<span data-ttu-id="0fa27-108">L'esempio seguente annulla la registrazione di un appliance corrente dalla configurazione del tenant online:</span><span class="sxs-lookup"><span data-stu-id="0fa27-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="0fa27-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="0fa27-109">Example 2</span></span>

<span data-ttu-id="0fa27-110">Nell'esempio seguente viene controllata la configurazione per l'annullamento della registrazione localmente senza connettersi alla configurazione del tenant online:</span><span class="sxs-lookup"><span data-stu-id="0fa27-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="0fa27-111">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="0fa27-111">Example 3</span></span>

<span data-ttu-id="0fa27-112">L'esempio seguente annulla la registrazione dell'appliance corrente con il nome "Appliance1" nel sito PSTN "Microsoft1":</span><span class="sxs-lookup"><span data-stu-id="0fa27-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="0fa27-113">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="0fa27-113">Detailed Description</span></span>
<span data-ttu-id="0fa27-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa27-114"></span></span>

<span data-ttu-id="0fa27-115">In modo analogo al cmdlet Register-CcAppliance, SiteName combinato con il nome di dominio completo esterno del server perimetrale nel file CloudConnector. ini è considerato un'identità del sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="0fa27-115">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="0fa27-116">Analogamente, Appliancename combinato con il nome di dominio completo di Mediation Server nel file CloudConnector. ini viene considerato un'identità Appliance.</span><span class="sxs-lookup"><span data-stu-id="0fa27-116">Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="0fa27-117">Dopo l'annullamento della registrazione dell'appliance, riavviare il servizio di gestione di Cloud Connector e accedere come account NetworkService.</span><span class="sxs-lookup"><span data-stu-id="0fa27-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0fa27-118">Parametri</span><span class="sxs-lookup"><span data-stu-id="0fa27-118">Parameters</span></span>
<span data-ttu-id="0fa27-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa27-119"></span></span>

|<span data-ttu-id="0fa27-120">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="0fa27-120">**Parameter**</span></span>|<span data-ttu-id="0fa27-121">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="0fa27-121">**Required**</span></span>|<span data-ttu-id="0fa27-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0fa27-122">**Type**</span></span>|<span data-ttu-id="0fa27-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0fa27-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0fa27-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="0fa27-124">SiteName</span></span> <br/> |<span data-ttu-id="0fa27-125">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="0fa27-125">Optional</span></span>  <br/> |<span data-ttu-id="0fa27-126">System.String</span><span class="sxs-lookup"><span data-stu-id="0fa27-126">System.String</span></span>  <br/> |<span data-ttu-id="0fa27-127">Nome del sito PSTN in cui è registrato l'accessorio.</span><span class="sxs-lookup"><span data-stu-id="0fa27-127">PSTN site name where the appliance is registered.</span></span> <span data-ttu-id="0fa27-128">Il valore predefinito è il valore SiteName nel file CloudConnector. ini.</span><span class="sxs-lookup"><span data-stu-id="0fa27-128">Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="0fa27-129">Appliancename</span><span class="sxs-lookup"><span data-stu-id="0fa27-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="0fa27-130">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="0fa27-130">Optional</span></span>  <br/> |<span data-ttu-id="0fa27-131">System.String</span><span class="sxs-lookup"><span data-stu-id="0fa27-131">System.String</span></span>  <br/> |<span data-ttu-id="0fa27-132">Nome dell'appliance corrente.</span><span class="sxs-lookup"><span data-stu-id="0fa27-132">Name of the current appliance.</span></span> <span data-ttu-id="0fa27-133">Il valore predefinito è il nome del computer del server host.</span><span class="sxs-lookup"><span data-stu-id="0fa27-133">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="0fa27-134">Locale</span><span class="sxs-lookup"><span data-stu-id="0fa27-134">Local</span></span>  <br/> |<span data-ttu-id="0fa27-135">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="0fa27-135">Optional</span></span>  <br/> |<span data-ttu-id="0fa27-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0fa27-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0fa27-137">Verificare la configurazione per la registrazione localmente senza connettersi a una configurazione del tenant online.</span><span class="sxs-lookup"><span data-stu-id="0fa27-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0fa27-138">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="0fa27-138">Input Types</span></span>
<span data-ttu-id="0fa27-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa27-139"></span></span>

<span data-ttu-id="0fa27-140">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0fa27-140">None.</span></span> <span data-ttu-id="0fa27-141">Il cmdlet Unregister-CcAppliance non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="0fa27-141">The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0fa27-142">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="0fa27-142">Return Types</span></span>
<span data-ttu-id="0fa27-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa27-143"></span></span>

<span data-ttu-id="0fa27-144">Nessuno</span><span class="sxs-lookup"><span data-stu-id="0fa27-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0fa27-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fa27-145">See also</span></span>
<span data-ttu-id="0fa27-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa27-146"></span></span>

[<span data-ttu-id="0fa27-147">Registro-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0fa27-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="0fa27-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0fa27-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="0fa27-149">Disinstallare-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0fa27-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="0fa27-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0fa27-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

