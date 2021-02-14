---
title: Get-CcApplianceLogDirectory
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
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Il cmdlet Get-CcApplianceLogDirectory mostra la directory corrente in cui sono archiviati i registri per un'applicazione Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800826"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="af99d-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="af99d-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="af99d-104">Il cmdlet Get-CcApplianceLogDirectory mostra la directory corrente in cui sono archiviati i registri per un'applicazione Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="af99d-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="af99d-105">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="af99d-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="af99d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="af99d-106">Parameters</span></span>

<span data-ttu-id="af99d-107">None</span><span class="sxs-lookup"><span data-stu-id="af99d-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="af99d-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="af99d-108">Examples</span></span>
<span data-ttu-id="af99d-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="af99d-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="af99d-110">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="af99d-110">Example 1</span></span>

<span data-ttu-id="af99d-111">Nell'esempio seguente viene mostrata la cartella corrente in cui sono archiviati i registri per l'applicazione corrente di Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="af99d-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="af99d-112">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="af99d-112">Detailed Description</span></span>
<span data-ttu-id="af99d-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="af99d-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="af99d-114">Il cmdlet Get-CcApplianceLogDirectory mostra la directory corrente in cui sono archiviati i registri per un'applicazione Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="af99d-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="af99d-115">La cartella predefinita è C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="af99d-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="af99d-116">È possibile modificare la directory utilizzando il cmdlet Set-CcApplianceDirectory locale.</span><span class="sxs-lookup"><span data-stu-id="af99d-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="af99d-117">Nota: non esiste alcun cmdlet che modifica solo il percorso della cartella dei registri senza modificare la directory dell'appliance.</span><span class="sxs-lookup"><span data-stu-id="af99d-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="af99d-118">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="af99d-118">Input Types</span></span>
<span data-ttu-id="af99d-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="af99d-119"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="af99d-120">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="af99d-120">None.</span></span> <span data-ttu-id="af99d-121">Il cmdlet Get-CcApplianceLogDirectory non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="af99d-121">The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="af99d-122">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="af99d-122">Return Types</span></span>
<span data-ttu-id="af99d-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="af99d-123"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="af99d-124">Questo comando restituisce un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="af99d-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="af99d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af99d-125">See also</span></span>
<span data-ttu-id="af99d-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="af99d-126"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="af99d-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="af99d-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

