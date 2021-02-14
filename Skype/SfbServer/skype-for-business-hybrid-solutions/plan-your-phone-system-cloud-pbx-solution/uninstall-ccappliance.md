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
description: Il Uninstall-CcAppliance cmdlet disinstalla l'applicazione Skype for Business Cloud Connector Edition in esecuzione dal server host.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824140"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="81409-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="81409-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="81409-104">Il Uninstall-CcAppliance cmdlet disinstalla l'applicazione Skype for Business Cloud Connector Edition in esecuzione dal server host.</span><span class="sxs-lookup"><span data-stu-id="81409-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="81409-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="81409-105">Examples</span></span>
<span data-ttu-id="81409-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="81409-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="81409-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="81409-107">Example 1</span></span>

<span data-ttu-id="81409-108">Nell'esempio seguente l'applicazione Cloud Connector viene scaricata e disinstallata dal server host:</span><span class="sxs-lookup"><span data-stu-id="81409-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="81409-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="81409-109">Example 2</span></span>

<span data-ttu-id="81409-110">Nell'esempio seguente viene svuotato e disinstallato forzatamente l'applicazione Cloud Connector in esecuzione nel server host anche se il processo di svuotamento non è riuscito:</span><span class="sxs-lookup"><span data-stu-id="81409-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="81409-111">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="81409-111">Example 3</span></span>

<span data-ttu-id="81409-112">Nell'esempio seguente viene disinstallata una versione di backup di Cloud Connector senza la conferma dell'utente:</span><span class="sxs-lookup"><span data-stu-id="81409-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="81409-113">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="81409-113">Detailed Description</span></span>
<span data-ttu-id="81409-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="81409-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="81409-115">Se si disinstalla la versione corrente in esecuzione di Cloud Connector, i servizi di svuotamento vengono prima eseguiti nel Mediation Server e nel server perimetrale per consentire il completamento delle chiamate simultanee prima di disinstallare le macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="81409-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="81409-116">Se si disinstalla una versione di backup, lo svuotamento non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="81409-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="81409-117">Parametri</span><span class="sxs-lookup"><span data-stu-id="81409-117">Parameters</span></span>
<span data-ttu-id="81409-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="81409-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="81409-119">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="81409-119">**Parameter**</span></span>|<span data-ttu-id="81409-120">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="81409-120">**Required**</span></span>|<span data-ttu-id="81409-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="81409-121">**Type**</span></span>|<span data-ttu-id="81409-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="81409-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="81409-123">Versione</span><span class="sxs-lookup"><span data-stu-id="81409-123">Version</span></span> <br/> | <span data-ttu-id="81409-124">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="81409-124">Optional</span></span> <br/> |<span data-ttu-id="81409-125">System.String</span><span class="sxs-lookup"><span data-stu-id="81409-125">System.String</span></span>  <br/> | <span data-ttu-id="81409-126">Versione di Cloud Connector che verrà disinstallata dal server host.</span><span class="sxs-lookup"><span data-stu-id="81409-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="81409-127">Se non specificato, disinstallare la versione in esecuzione corrente.</span><span class="sxs-lookup"><span data-stu-id="81409-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="81409-128">Force</span><span class="sxs-lookup"><span data-stu-id="81409-128">Force</span></span>  <br/> |<span data-ttu-id="81409-129">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="81409-129">Optional</span></span>  <br/> |<span data-ttu-id="81409-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="81409-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="81409-131">Se si disinstalla la versione in esecuzione corrente, tentare di svuotare i server nel Mediation Server e nel server perimetrale prima di disinstallare le macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="81409-131">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines.</span></span> <span data-ttu-id="81409-132">Se si specifica l'opzione "Force", anche in caso di errore dei servizi di svuotamento, le macchine virtuali verranno disinstallate.</span><span class="sxs-lookup"><span data-stu-id="81409-132">If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled.</span></span> <span data-ttu-id="81409-133">Questo parametro viene utilizzato solo per disinstallare la versione in esecuzione corrente.</span><span class="sxs-lookup"><span data-stu-id="81409-133">This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="81409-134">Conferma</span><span class="sxs-lookup"><span data-stu-id="81409-134">Confirm</span></span>  <br/> |<span data-ttu-id="81409-135">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="81409-135">Optional</span></span>  <br/> |<span data-ttu-id="81409-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="81409-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="81409-137">Chiedere all'utente di confermare la disinstallazione delle macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="81409-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="81409-138">Il valore predefinito è VERO.</span><span class="sxs-lookup"><span data-stu-id="81409-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="81409-139">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="81409-139">Input Types</span></span>
<span data-ttu-id="81409-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81409-140"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="81409-141">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="81409-141">None.</span></span> <span data-ttu-id="81409-142">Il cmdlet Uninstall-CcAppliance non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="81409-142">The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="81409-143">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="81409-143">Return Types</span></span>
<span data-ttu-id="81409-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81409-144"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="81409-145">None</span><span class="sxs-lookup"><span data-stu-id="81409-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="81409-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81409-146">See also</span></span>
<span data-ttu-id="81409-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="81409-147"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="81409-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="81409-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="81409-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="81409-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="81409-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="81409-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="81409-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="81409-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

