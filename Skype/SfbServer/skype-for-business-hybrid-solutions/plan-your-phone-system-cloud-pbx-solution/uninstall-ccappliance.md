---
title: Disinstallare-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Il cmdlet Uninstall-CcAppliance Disinstalla l'uso di Skype for Business Cloud Connector Edition dal server host.
ms.openlocfilehash: 337c5c489846facb1da3c177cac7a965d7550ae5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190589"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="d0c6d-103">Disinstallare-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d0c6d-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="d0c6d-104">Il cmdlet Uninstall-CcAppliance Disinstalla l'uso di Skype for Business Cloud Connector Edition dal server host.</span><span class="sxs-lookup"><span data-stu-id="d0c6d-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="d0c6d-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="d0c6d-105">Examples</span></span>
<span data-ttu-id="d0c6d-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d0c6d-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="d0c6d-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="d0c6d-107">Example 1</span></span>

<span data-ttu-id="d0c6d-108">Nell'esempio seguente viene svuotato e disinstallato l'accessorio Cloud Connector dal server host:</span><span class="sxs-lookup"><span data-stu-id="d0c6d-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="d0c6d-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="d0c6d-109">Example 2</span></span>

<span data-ttu-id="d0c6d-110">L'esempio seguente Scarica e Disinstalla forzatamente l'appliance di connessione cloud in esecuzione nel server host anche se il processo di svuotamento non è riuscito:</span><span class="sxs-lookup"><span data-stu-id="d0c6d-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="d0c6d-111">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="d0c6d-111">Example 3</span></span>

<span data-ttu-id="d0c6d-112">Nell'esempio successivo viene disinstallata una versione di backup di Cloud Connector senza la conferma dell'utente:</span><span class="sxs-lookup"><span data-stu-id="d0c6d-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="d0c6d-113">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="d0c6d-113">Detailed Description</span></span>
<span data-ttu-id="d0c6d-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d0c6d-114"></span></span>

<span data-ttu-id="d0c6d-115">Se si disinstalla la versione corrente di Cloud Connector, i servizi di drenaggio vengono eseguiti prima di tutto sul server Mediation e Edge Server per consentire la fine delle chiamate simultanee prima della disinstallazione delle macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="d0c6d-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="d0c6d-116">Se si disinstalla una versione di backup, lo svuotamento non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="d0c6d-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="d0c6d-117">Parametri</span><span class="sxs-lookup"><span data-stu-id="d0c6d-117">Parameters</span></span>
<span data-ttu-id="d0c6d-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d0c6d-118"></span></span>

|<span data-ttu-id="d0c6d-119">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="d0c6d-119">**Parameter**</span></span>|<span data-ttu-id="d0c6d-120">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="d0c6d-120">**Required**</span></span>|<span data-ttu-id="d0c6d-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d0c6d-121">**Type**</span></span>|<span data-ttu-id="d0c6d-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d0c6d-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d0c6d-123">Versione</span><span class="sxs-lookup"><span data-stu-id="d0c6d-123">Version</span></span> <br/> | <span data-ttu-id="d0c6d-124">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="d0c6d-124">Optional</span></span> <br/> |<span data-ttu-id="d0c6d-125">System.String</span><span class="sxs-lookup"><span data-stu-id="d0c6d-125">System.String</span></span>  <br/> | <span data-ttu-id="d0c6d-126">La versione di Cloud Connector che verrà disinstallata dal server host.</span><span class="sxs-lookup"><span data-stu-id="d0c6d-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="d0c6d-127">Se non specificato, disinstallare la versione corrente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d0c6d-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="d0c6d-128">Force</span><span class="sxs-lookup"><span data-stu-id="d0c6d-128">Force</span></span>  <br/> |<span data-ttu-id="d0c6d-129">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="d0c6d-129">Optional</span></span>  <br/> |<span data-ttu-id="d0c6d-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d0c6d-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d0c6d-131">Per disinstallare la versione corrente in esecuzione, provare a svuotare i server in Mediation Server e Edge Server prima di disinstallare le macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="d0c6d-131">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines.</span></span> <span data-ttu-id="d0c6d-132">Se specifichi l'opzione "forza", anche se i servizi di scarico non riescono, le macchine virtuali verranno disinstallate.</span><span class="sxs-lookup"><span data-stu-id="d0c6d-132">If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled.</span></span> <span data-ttu-id="d0c6d-133">Questo parametro viene usato solo per disinstallare la versione corrente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d0c6d-133">This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="d0c6d-134">Confirm</span><span class="sxs-lookup"><span data-stu-id="d0c6d-134">Confirm</span></span>  <br/> |<span data-ttu-id="d0c6d-135">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="d0c6d-135">Optional</span></span>  <br/> |<span data-ttu-id="d0c6d-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d0c6d-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d0c6d-137">Richiedi conferma dell'utente per disinstallare le macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="d0c6d-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="d0c6d-138">Il valore predefinito è TRUE.</span><span class="sxs-lookup"><span data-stu-id="d0c6d-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d0c6d-139">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="d0c6d-139">Input Types</span></span>
<span data-ttu-id="d0c6d-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d0c6d-140"></span></span>

<span data-ttu-id="d0c6d-141">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d0c6d-141">None.</span></span> <span data-ttu-id="d0c6d-142">Il cmdlet Uninstall-CcAppliance non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="d0c6d-142">The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d0c6d-143">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="d0c6d-143">Return Types</span></span>
<span data-ttu-id="d0c6d-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d0c6d-144"></span></span>

<span data-ttu-id="d0c6d-145">Nessuno</span><span class="sxs-lookup"><span data-stu-id="d0c6d-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d0c6d-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0c6d-146">See also</span></span>
<span data-ttu-id="d0c6d-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d0c6d-147"></span></span>

[<span data-ttu-id="d0c6d-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d0c6d-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="d0c6d-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d0c6d-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="d0c6d-150">Registro-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d0c6d-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="d0c6d-151">Annullamento della registrazione-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d0c6d-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

