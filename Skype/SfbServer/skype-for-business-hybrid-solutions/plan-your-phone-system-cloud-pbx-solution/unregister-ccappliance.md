---
title: Unregister-CcAppliance
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
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Il cmdlet Unregister-CcAppliance annulla la registrazione dell'applicazione Skype for Business Cloud Connector Edition corrente da un sito PSTN nella configurazione tenant online.
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824130"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="e7fe8-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e7fe8-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="e7fe8-104">Il cmdlet Unregister-CcAppliance annulla la registrazione dell'applicazione Skype for Business Cloud Connector Edition corrente da un sito PSTN nella configurazione tenant online.</span><span class="sxs-lookup"><span data-stu-id="e7fe8-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="e7fe8-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="e7fe8-105">Examples</span></span>
<span data-ttu-id="e7fe8-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e7fe8-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="e7fe8-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="e7fe8-107">Example 1</span></span>

<span data-ttu-id="e7fe8-108">Nell'esempio seguente viene annullata la registrazione di un'applicazione corrente dalla configurazione tenant online:</span><span class="sxs-lookup"><span data-stu-id="e7fe8-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="e7fe8-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="e7fe8-109">Example 2</span></span>

<span data-ttu-id="e7fe8-110">Nell'esempio seguente viene verificata la presenza di un'annullamento della registrazione in locale senza connettersi alla configurazione tenant online:</span><span class="sxs-lookup"><span data-stu-id="e7fe8-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="e7fe8-111">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="e7fe8-111">Example 3</span></span>

<span data-ttu-id="e7fe8-112">Nell'esempio seguente viene annullata la registrazione dell'applicazione corrente con nome "Appliance1" nel sito PSTN "Site1":</span><span class="sxs-lookup"><span data-stu-id="e7fe8-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="e7fe8-113">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="e7fe8-113">Detailed Description</span></span>
<span data-ttu-id="e7fe8-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e7fe8-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="e7fe8-115">Analogamente al cmdlet Register-CcAppliance, SiteName combinato con l'FQDN esterno del server perimetrale nel file CloudConnector.ini viene considerato un'identità del sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="e7fe8-115">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="e7fe8-116">Analogamente, ApplianceName combinato con l'FQDN di Mediation Server nel file CloudConnector.ini viene considerato un'identità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e7fe8-116">Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="e7fe8-117">Dopo l'annullamento della registrazione dell'applicazione, riavviare il servizio di gestione di Cloud Connector ed eseguire l'accesso con l'account NetworkService.</span><span class="sxs-lookup"><span data-stu-id="e7fe8-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="e7fe8-118">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7fe8-118">Parameters</span></span>
<span data-ttu-id="e7fe8-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e7fe8-119"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="e7fe8-120">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="e7fe8-120">**Parameter**</span></span>|<span data-ttu-id="e7fe8-121">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="e7fe8-121">**Required**</span></span>|<span data-ttu-id="e7fe8-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e7fe8-122">**Type**</span></span>|<span data-ttu-id="e7fe8-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e7fe8-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e7fe8-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="e7fe8-124">SiteName</span></span> <br/> |<span data-ttu-id="e7fe8-125">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="e7fe8-125">Optional</span></span>  <br/> |<span data-ttu-id="e7fe8-126">System.String</span><span class="sxs-lookup"><span data-stu-id="e7fe8-126">System.String</span></span>  <br/> |<span data-ttu-id="e7fe8-127">Nome del sito PSTN in cui è registrato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e7fe8-127">PSTN site name where the appliance is registered.</span></span> <span data-ttu-id="e7fe8-128">Il valore predefinito è SiteName in CloudConnector.ini file.</span><span class="sxs-lookup"><span data-stu-id="e7fe8-128">Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="e7fe8-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="e7fe8-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="e7fe8-130">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="e7fe8-130">Optional</span></span>  <br/> |<span data-ttu-id="e7fe8-131">System.String</span><span class="sxs-lookup"><span data-stu-id="e7fe8-131">System.String</span></span>  <br/> |<span data-ttu-id="e7fe8-132">Nome dell'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="e7fe8-132">Name of the current appliance.</span></span> <span data-ttu-id="e7fe8-133">Il valore predefinito è il nome computer del server host.</span><span class="sxs-lookup"><span data-stu-id="e7fe8-133">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="e7fe8-134">Locale</span><span class="sxs-lookup"><span data-stu-id="e7fe8-134">Local</span></span>  <br/> |<span data-ttu-id="e7fe8-135">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="e7fe8-135">Optional</span></span>  <br/> |<span data-ttu-id="e7fe8-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="e7fe8-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="e7fe8-137">Controllare la configurazione per la registrazione in locale senza connettersi a una configurazione tenant online.</span><span class="sxs-lookup"><span data-stu-id="e7fe8-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="e7fe8-138">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="e7fe8-138">Input Types</span></span>
<span data-ttu-id="e7fe8-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e7fe8-139"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="e7fe8-140">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="e7fe8-140">None.</span></span> <span data-ttu-id="e7fe8-141">Il cmdlet Unregister-CcAppliance non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="e7fe8-141">The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e7fe8-142">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="e7fe8-142">Return Types</span></span>
<span data-ttu-id="e7fe8-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e7fe8-143"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e7fe8-144">None</span><span class="sxs-lookup"><span data-stu-id="e7fe8-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7fe8-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7fe8-145">See also</span></span>
<span data-ttu-id="e7fe8-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e7fe8-146"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="e7fe8-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e7fe8-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="e7fe8-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e7fe8-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="e7fe8-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e7fe8-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="e7fe8-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e7fe8-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

