---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Il cmdlet Uninstall-CcAppliance Disinstalla l'uso di Skype for Business Cloud Connector Edition dal server host.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824140"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="0591f-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0591f-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="0591f-104">Il cmdlet Uninstall-CcAppliance Disinstalla l'uso di Skype for Business Cloud Connector Edition dal server host.</span><span class="sxs-lookup"><span data-stu-id="0591f-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="0591f-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="0591f-105">Examples</span></span>
<span data-ttu-id="0591f-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0591f-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="0591f-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="0591f-107">Example 1</span></span>

<span data-ttu-id="0591f-108">Nell'esempio seguente viene svuotato e disinstallato l'accessorio Cloud Connector dal server host:</span><span class="sxs-lookup"><span data-stu-id="0591f-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="0591f-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="0591f-109">Example 2</span></span>

<span data-ttu-id="0591f-110">L'esempio seguente Scarica e Disinstalla forzatamente l'appliance di connessione cloud in esecuzione nel server host anche se il processo di svuotamento non è riuscito:</span><span class="sxs-lookup"><span data-stu-id="0591f-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="0591f-111">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="0591f-111">Example 3</span></span>

<span data-ttu-id="0591f-112">Nell'esempio successivo viene disinstallata una versione di backup di Cloud Connector senza la conferma dell'utente:</span><span class="sxs-lookup"><span data-stu-id="0591f-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="0591f-113">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="0591f-113">Detailed Description</span></span>
<span data-ttu-id="0591f-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0591f-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="0591f-115">Se si disinstalla la versione corrente di Cloud Connector, i servizi di drenaggio vengono eseguiti prima di tutto sul server Mediation e Edge Server per consentire la fine delle chiamate simultanee prima della disinstallazione delle macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="0591f-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="0591f-116">Se si disinstalla una versione di backup, lo svuotamento non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0591f-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0591f-117">Parametri</span><span class="sxs-lookup"><span data-stu-id="0591f-117">Parameters</span></span>
<span data-ttu-id="0591f-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0591f-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="0591f-119">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="0591f-119">**Parameter**</span></span>|<span data-ttu-id="0591f-120">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="0591f-120">**Required**</span></span>|<span data-ttu-id="0591f-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0591f-121">**Type**</span></span>|<span data-ttu-id="0591f-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0591f-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0591f-123">Versione</span><span class="sxs-lookup"><span data-stu-id="0591f-123">Version</span></span> <br/> | <span data-ttu-id="0591f-124">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="0591f-124">Optional</span></span> <br/> |<span data-ttu-id="0591f-125">System.String</span><span class="sxs-lookup"><span data-stu-id="0591f-125">System.String</span></span>  <br/> | <span data-ttu-id="0591f-126">La versione di Cloud Connector che verrà disinstallata dal server host.</span><span class="sxs-lookup"><span data-stu-id="0591f-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="0591f-127">Se non specificato, disinstallare la versione corrente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0591f-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="0591f-128">Force</span><span class="sxs-lookup"><span data-stu-id="0591f-128">Force</span></span>  <br/> |<span data-ttu-id="0591f-129">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="0591f-129">Optional</span></span>  <br/> |<span data-ttu-id="0591f-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0591f-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0591f-131">Per disinstallare la versione corrente in esecuzione, provare a svuotare i server in Mediation Server e Edge Server prima di disinstallare le macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="0591f-131">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines.</span></span> <span data-ttu-id="0591f-132">Se specifichi l'opzione "forza", anche se i servizi di scarico non riescono, le macchine virtuali verranno disinstallate.</span><span class="sxs-lookup"><span data-stu-id="0591f-132">If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled.</span></span> <span data-ttu-id="0591f-133">Questo parametro viene usato solo per disinstallare la versione corrente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0591f-133">This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="0591f-134">Confirm</span><span class="sxs-lookup"><span data-stu-id="0591f-134">Confirm</span></span>  <br/> |<span data-ttu-id="0591f-135">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="0591f-135">Optional</span></span>  <br/> |<span data-ttu-id="0591f-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0591f-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0591f-137">Richiedi conferma dell'utente per disinstallare le macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="0591f-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="0591f-138">Il valore predefinito è TRUE.</span><span class="sxs-lookup"><span data-stu-id="0591f-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0591f-139">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="0591f-139">Input Types</span></span>
<span data-ttu-id="0591f-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0591f-140"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="0591f-141">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0591f-141">None.</span></span> <span data-ttu-id="0591f-142">Il cmdlet Uninstall-CcAppliance non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="0591f-142">The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0591f-143">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="0591f-143">Return Types</span></span>
<span data-ttu-id="0591f-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0591f-144"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0591f-145">Nessuno</span><span class="sxs-lookup"><span data-stu-id="0591f-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0591f-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0591f-146">See also</span></span>
<span data-ttu-id="0591f-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0591f-147"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="0591f-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0591f-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="0591f-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0591f-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="0591f-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0591f-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="0591f-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0591f-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

