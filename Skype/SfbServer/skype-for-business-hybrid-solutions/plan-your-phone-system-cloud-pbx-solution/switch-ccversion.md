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
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Il cmdlet Switch-CcVersion disconnette l'appliance in uso e passa a un'appliance appena distribuita o di backup.
ms.openlocfilehash: 157d1b677cc6c63d7707c9e1633cd8b6e3ad5927
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003156"
---
# <a name="switch-ccversion"></a><span data-ttu-id="eed77-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="eed77-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="eed77-104">Il cmdlet Switch-CcVersion disconnette l'appliance in uso e passa a un'appliance appena distribuita o di backup.</span><span class="sxs-lookup"><span data-stu-id="eed77-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="eed77-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="eed77-105">Examples</span></span>
<span data-ttu-id="eed77-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="eed77-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="eed77-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="eed77-107">Example 1</span></span>

<span data-ttu-id="eed77-108">L'esempio seguente svuota i servizi dell'appliance corrente in uso e quindi passa a un'appliance appena distribuita o di backup:</span><span class="sxs-lookup"><span data-stu-id="eed77-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="eed77-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="eed77-109">Example 2</span></span>

<span data-ttu-id="eed77-110">L'esempio seguente svuota i servizi dell'appliance corrente e arresta i servizi con forza se lo svuotamento dei servizi non riesce.</span><span class="sxs-lookup"><span data-stu-id="eed77-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="eed77-111">Il comando passa quindi a un dispositivo appena distribuito o di backup:</span><span class="sxs-lookup"><span data-stu-id="eed77-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="eed77-112">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="eed77-112">Detailed Description</span></span>
<span data-ttu-id="eed77-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="eed77-113"></span></span>

<span data-ttu-id="eed77-114">Il cmdlet Switch-CcVersion svuota i servizi Cloud Connector in Mediation Server e Edge Server.</span><span class="sxs-lookup"><span data-stu-id="eed77-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="eed77-115">Tutte le chiamate in uso verranno completate, ma l'accessorio rifiuterà tutte le nuove chiamate.</span><span class="sxs-lookup"><span data-stu-id="eed77-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="eed77-116">Dopo lo svuotamento, il cmdlet disconnette l'appliance corrente dalle reti aziendali e Internet, disattiva tutte le macchine virtuali appartenenti all'appliance e quindi connette l'appliance di backup alle reti aziendali e Internet.</span><span class="sxs-lookup"><span data-stu-id="eed77-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="eed77-117">Parametri</span><span class="sxs-lookup"><span data-stu-id="eed77-117">Parameters</span></span>
<span data-ttu-id="eed77-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="eed77-118"></span></span>

|<span data-ttu-id="eed77-119">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="eed77-119">**Parameter**</span></span>|<span data-ttu-id="eed77-120">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="eed77-120">**Required**</span></span>|<span data-ttu-id="eed77-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="eed77-121">**Type**</span></span>|<span data-ttu-id="eed77-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="eed77-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="eed77-123">Force</span><span class="sxs-lookup"><span data-stu-id="eed77-123">Force</span></span> <br/> | <span data-ttu-id="eed77-124">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="eed77-124">Optional</span></span> <br/> |<span data-ttu-id="eed77-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="eed77-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="eed77-126">Arresta i servizi con forza se lo svuotamento dei servizi non riesce.</span><span class="sxs-lookup"><span data-stu-id="eed77-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="eed77-127">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="eed77-127">Input Types</span></span>
<span data-ttu-id="eed77-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="eed77-128"></span></span>

<span data-ttu-id="eed77-129">Nessuno</span><span class="sxs-lookup"><span data-stu-id="eed77-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="eed77-130">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="eed77-130">Return Types</span></span>
<span data-ttu-id="eed77-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="eed77-131"></span></span>

<span data-ttu-id="eed77-132">Nessuno</span><span class="sxs-lookup"><span data-stu-id="eed77-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eed77-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eed77-133">See also</span></span>
<span data-ttu-id="eed77-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="eed77-134"></span></span>

<span data-ttu-id="eed77-135">Nessuno</span><span class="sxs-lookup"><span data-stu-id="eed77-135">None</span></span>
  

