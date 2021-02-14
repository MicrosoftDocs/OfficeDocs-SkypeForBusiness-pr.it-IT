---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Il Switch-CcVersion disconnette l'applicazione in esecuzione e passa a un'appliance appena distribuita o di backup.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824150"
---
# <a name="switch-ccversion"></a><span data-ttu-id="83979-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="83979-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="83979-104">Il Switch-CcVersion disconnette l'applicazione in esecuzione e passa a un'appliance appena distribuita o di backup.</span><span class="sxs-lookup"><span data-stu-id="83979-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="83979-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="83979-105">Examples</span></span>
<span data-ttu-id="83979-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="83979-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="83979-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="83979-107">Example 1</span></span>

<span data-ttu-id="83979-108">Nell'esempio seguente vengono scaricati i servizi dell'applicazione in esecuzione corrente e quindi si passa a un'appliance appena distribuita o di backup:</span><span class="sxs-lookup"><span data-stu-id="83979-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="83979-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="83979-109">Example 2</span></span>

<span data-ttu-id="83979-110">Nell'esempio seguente vengono scaricati i servizi dell'applicazione in esecuzione corrente e i servizi vengono arrestati forzatamente in caso di errore di svuotamento dei servizi.</span><span class="sxs-lookup"><span data-stu-id="83979-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="83979-111">Il comando passa quindi a un'appliance appena distribuita o di backup:</span><span class="sxs-lookup"><span data-stu-id="83979-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="83979-112">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="83979-112">Detailed Description</span></span>
<span data-ttu-id="83979-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="83979-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="83979-114">Il Switch-CcVersion cmdlet svuota i servizi del connettore cloud nel Mediation Server e nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="83979-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="83979-115">Tutte le chiamate in esecuzione verranno completate, ma l'applicazione rifiuterà tutte le nuove chiamate.</span><span class="sxs-lookup"><span data-stu-id="83979-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="83979-116">Dopo lo svuotamento, il cmdlet disconnette l'applicazione in esecuzione dalle reti aziendali e Internet, disattiva tutte le macchine virtuali appartenenti all'appliance e quindi connette l'appliance di backup alle reti aziendali e Internet.</span><span class="sxs-lookup"><span data-stu-id="83979-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="83979-117">Parametri</span><span class="sxs-lookup"><span data-stu-id="83979-117">Parameters</span></span>
<span data-ttu-id="83979-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="83979-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="83979-119">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="83979-119">**Parameter**</span></span>|<span data-ttu-id="83979-120">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="83979-120">**Required**</span></span>|<span data-ttu-id="83979-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="83979-121">**Type**</span></span>|<span data-ttu-id="83979-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="83979-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="83979-123">Force</span><span class="sxs-lookup"><span data-stu-id="83979-123">Force</span></span> <br/> | <span data-ttu-id="83979-124">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="83979-124">Optional</span></span> <br/> |<span data-ttu-id="83979-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="83979-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="83979-126">Arresta forzatamente i servizi in caso di errore di svuotamento dei servizi.</span><span class="sxs-lookup"><span data-stu-id="83979-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="83979-127">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="83979-127">Input Types</span></span>
<span data-ttu-id="83979-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="83979-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="83979-129">None</span><span class="sxs-lookup"><span data-stu-id="83979-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="83979-130">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="83979-130">Return Types</span></span>
<span data-ttu-id="83979-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="83979-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="83979-132">None</span><span class="sxs-lookup"><span data-stu-id="83979-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="83979-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83979-133">See also</span></span>
<span data-ttu-id="83979-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="83979-134"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="83979-135">Nessuno</span><span class="sxs-lookup"><span data-stu-id="83979-135">None</span></span>
  

