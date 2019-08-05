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
ms.openlocfilehash: 56a13da740b0c23adee7e05ddbcc1bbc82f0f1cc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190649"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="ab4d1-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="ab4d1-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="ab4d1-105">Il cmdlet Set-CcApplianceDirectory imposta la directory di lavoro nel server host di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="ab4d1-105">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="ab4d1-106">Tutti i file di distribuzione sono archiviati in questa directory.</span><span class="sxs-lookup"><span data-stu-id="ab4d1-106">All deployment files are stored in this directory.</span></span>
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="ab4d1-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="ab4d1-107">Examples</span></span>
<span data-ttu-id="ab4d1-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ab4d1-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="ab4d1-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="ab4d1-109">Example 1</span></span>

<span data-ttu-id="ab4d1-110">L'esempio seguente imposta la directory di lavoro nel server host su c:\cloudconnector\applianceroot:</span><span class="sxs-lookup"><span data-stu-id="ab4d1-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="ab4d1-111">Parametri</span><span class="sxs-lookup"><span data-stu-id="ab4d1-111">Parameters</span></span>
<span data-ttu-id="ab4d1-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ab4d1-112"></span></span>

|<span data-ttu-id="ab4d1-113">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="ab4d1-113">**Parameter**</span></span>|<span data-ttu-id="ab4d1-114">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="ab4d1-114">**Required**</span></span>|<span data-ttu-id="ab4d1-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ab4d1-115">**Type**</span></span>|<span data-ttu-id="ab4d1-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ab4d1-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ab4d1-117">Percorso</span><span class="sxs-lookup"><span data-stu-id="ab4d1-117">Path</span></span> <br/> | <span data-ttu-id="ab4d1-118">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ab4d1-118">Required</span></span> <br/> |<span data-ttu-id="ab4d1-119">System.String</span><span class="sxs-lookup"><span data-stu-id="ab4d1-119">System.String</span></span>  <br/> | <span data-ttu-id="ab4d1-120">Specifica il percorso in cui sono archiviati tutti i file di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ab4d1-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ab4d1-121">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="ab4d1-121">Input Types</span></span>
<span data-ttu-id="ab4d1-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ab4d1-122"></span></span>

<span data-ttu-id="ab4d1-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ab4d1-123">None.</span></span> <span data-ttu-id="ab4d1-124">Il cmdlet Set-CcApplianceDirectory non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="ab4d1-124">The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ab4d1-125">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="ab4d1-125">Return Types</span></span>
<span data-ttu-id="ab4d1-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ab4d1-126"></span></span>

<span data-ttu-id="ab4d1-127">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ab4d1-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ab4d1-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab4d1-128">See also</span></span>
<span data-ttu-id="ab4d1-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ab4d1-129"></span></span>

<span data-ttu-id="ab4d1-130">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ab4d1-130">None</span></span>
  

