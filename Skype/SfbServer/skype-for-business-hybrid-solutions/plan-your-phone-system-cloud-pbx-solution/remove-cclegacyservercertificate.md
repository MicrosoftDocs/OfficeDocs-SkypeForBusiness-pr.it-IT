---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Il cmdlet Remove-CcLegacyServerCertificate rimuove i certificati server legacy in Central Management store, Mediation Server e Edge Server dopo l'esecuzione dei cmdlet Renew-CcCACertificate o Renew CcServerCertificate.
ms.openlocfilehash: f22a57a3a366c621a1c035881c886190055b15e6
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003286"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="22e35-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="22e35-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="22e35-104">Il cmdlet Remove-CcLegacyServerCertificate rimuove i certificati server legacy in Central Management store, Mediation Server e Edge Server dopo l'esecuzione dei cmdlet Renew-CcCACertificate o Renew CcServerCertificate.</span><span class="sxs-lookup"><span data-stu-id="22e35-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="22e35-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="22e35-105">Examples</span></span>
<span data-ttu-id="22e35-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="22e35-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="22e35-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="22e35-107">Example 1</span></span>

<span data-ttu-id="22e35-108">L'esempio seguente consente di rimuovere i certificati legacy rilasciati per Central Management store, Mediation Server e Edge Server dopo aver rinnovato i certificati:</span><span class="sxs-lookup"><span data-stu-id="22e35-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="22e35-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="22e35-109">Example 2</span></span>

<span data-ttu-id="22e35-110">L'esempio seguente rimuove i certificati rilasciati per Mediation Server e Edge Server dopo aver rinnovato i certificati:</span><span class="sxs-lookup"><span data-stu-id="22e35-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="22e35-111">Parametri</span><span class="sxs-lookup"><span data-stu-id="22e35-111">Parameters</span></span>
<span data-ttu-id="22e35-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="22e35-112"></span></span>

|<span data-ttu-id="22e35-113">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="22e35-113">**Parameter**</span></span>|<span data-ttu-id="22e35-114">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="22e35-114">**Required**</span></span>|<span data-ttu-id="22e35-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="22e35-115">**Type**</span></span>|<span data-ttu-id="22e35-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="22e35-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="22e35-117">Ruoli</span><span class="sxs-lookup"><span data-stu-id="22e35-117">Roles</span></span> <br/> |<span data-ttu-id="22e35-118">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="22e35-118">Optional</span></span>  <br/> |<span data-ttu-id="22e35-119">System. Array</span><span class="sxs-lookup"><span data-stu-id="22e35-119">System.Array</span></span>  <br/> | <span data-ttu-id="22e35-120">Matrice di ruoli del server del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="22e35-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="22e35-121">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="22e35-121">Input Types</span></span>
<span data-ttu-id="22e35-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="22e35-122"></span></span>

<span data-ttu-id="22e35-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="22e35-123">None.</span></span> <span data-ttu-id="22e35-124">Il cmdlet Remove-CcLegacyServerCertificate non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="22e35-124">The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="22e35-125">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="22e35-125">Return Types</span></span>
<span data-ttu-id="22e35-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="22e35-126"></span></span>

<span data-ttu-id="22e35-127">Nessuno</span><span class="sxs-lookup"><span data-stu-id="22e35-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="22e35-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22e35-128">See also</span></span>
<span data-ttu-id="22e35-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="22e35-129"></span></span>

[<span data-ttu-id="22e35-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="22e35-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="22e35-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="22e35-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="22e35-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="22e35-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="22e35-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="22e35-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

