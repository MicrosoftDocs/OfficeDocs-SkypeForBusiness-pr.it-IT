---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Il cmdlet Set-CcApplianceDirectory imposta la directory di lavoro nel server host di Skype for Business Cloud Connector Edition. Tutti i file di distribuzione sono archiviati in questa directory.
ms.openlocfilehash: 1dfc85a08709fd550b91dbecdb5d4186f265ca67
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003226"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="6f60d-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="6f60d-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="6f60d-105">Il cmdlet Set-CcApplianceDirectory imposta la directory di lavoro nel server host di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="6f60d-105">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="6f60d-106">Tutti i file di distribuzione sono archiviati in questa directory.</span><span class="sxs-lookup"><span data-stu-id="6f60d-106">All deployment files are stored in this directory.</span></span>
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="6f60d-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="6f60d-107">Examples</span></span>
<span data-ttu-id="6f60d-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6f60d-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="6f60d-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="6f60d-109">Example 1</span></span>

<span data-ttu-id="6f60d-110">L'esempio seguente imposta la directory di lavoro nel server host su c:\cloudconnector\applianceroot:</span><span class="sxs-lookup"><span data-stu-id="6f60d-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="6f60d-111">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f60d-111">Parameters</span></span>
<span data-ttu-id="6f60d-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6f60d-112"></span></span>

|<span data-ttu-id="6f60d-113">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="6f60d-113">**Parameter**</span></span>|<span data-ttu-id="6f60d-114">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="6f60d-114">**Required**</span></span>|<span data-ttu-id="6f60d-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6f60d-115">**Type**</span></span>|<span data-ttu-id="6f60d-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6f60d-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="6f60d-117">Percorso</span><span class="sxs-lookup"><span data-stu-id="6f60d-117">Path</span></span> <br/> | <span data-ttu-id="6f60d-118">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="6f60d-118">Required</span></span> <br/> |<span data-ttu-id="6f60d-119">System.String</span><span class="sxs-lookup"><span data-stu-id="6f60d-119">System.String</span></span>  <br/> | <span data-ttu-id="6f60d-120">Specifica il percorso in cui sono archiviati tutti i file di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6f60d-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="6f60d-121">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="6f60d-121">Input Types</span></span>
<span data-ttu-id="6f60d-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6f60d-122"></span></span>

<span data-ttu-id="6f60d-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6f60d-123">None.</span></span> <span data-ttu-id="6f60d-124">Il cmdlet Set-CcApplianceDirectory non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="6f60d-124">The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6f60d-125">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="6f60d-125">Return Types</span></span>
<span data-ttu-id="6f60d-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6f60d-126"></span></span>

<span data-ttu-id="6f60d-127">Nessuno</span><span class="sxs-lookup"><span data-stu-id="6f60d-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6f60d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f60d-128">See also</span></span>
<span data-ttu-id="6f60d-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6f60d-129"></span></span>

<span data-ttu-id="6f60d-130">Nessuno</span><span class="sxs-lookup"><span data-stu-id="6f60d-130">None</span></span>
  

