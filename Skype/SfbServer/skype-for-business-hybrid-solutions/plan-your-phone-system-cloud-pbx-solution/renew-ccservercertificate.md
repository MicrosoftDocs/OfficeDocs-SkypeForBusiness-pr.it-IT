---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: Il Renew-CcServerCertificate consente di rinnovare i certificati per Skype for Business Cloud Connector Edition quando sono prossimi alla scadenza o sono già scaduti. Questo comando è stato modificato in Update-CcServerCertificate in Cloud Connector 2.0 e versioni successive.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824262"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="c92cc-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="c92cc-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="c92cc-105">Il Renew-CcServerCertificate consente di rinnovare i certificati per Skype for Business Cloud Connector Edition quando sono prossimi alla scadenza o sono già scaduti.</span><span class="sxs-lookup"><span data-stu-id="c92cc-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="c92cc-106">Questo comando è stato modificato in Update-CcServerCertificate in Cloud Connector 2.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c92cc-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="c92cc-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="c92cc-107">Examples</span></span>
<span data-ttu-id="c92cc-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c92cc-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c92cc-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="c92cc-109">Example 1</span></span>

<span data-ttu-id="c92cc-110">Nell'esempio seguente vengono rinnovati i certificati per l'archivio di gestione centrale, il Mediation Server e il server perimetrale quando i certificati sono prossimi alla scadenza o sono già scaduti:</span><span class="sxs-lookup"><span data-stu-id="c92cc-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="c92cc-111">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="c92cc-111">Example 2</span></span>

<span data-ttu-id="c92cc-112">Nell'esempio seguente vengono rinnovati i certificati per Mediation Server ed Edge Server quando sono prossimi alla scadenza o sono già scaduti:</span><span class="sxs-lookup"><span data-stu-id="c92cc-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="c92cc-113">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="c92cc-113">Detailed Description</span></span>
<span data-ttu-id="c92cc-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c92cc-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c92cc-115">I certificati interni del connettore cloud emessi per l'archivio di gestione centrale, il Mediation Server e il server perimetrale sono validi per due anni dopo l'emissione da un servizio autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="c92cc-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="c92cc-116">Se i certificati sono prossimi alla scadenza o sono già scaduti, eseguire il cmdlet Renew-CcServerCertificate per rinnovare i certificati.</span><span class="sxs-lookup"><span data-stu-id="c92cc-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="c92cc-117">Parametri</span><span class="sxs-lookup"><span data-stu-id="c92cc-117">Parameters</span></span>
<span data-ttu-id="c92cc-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c92cc-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="c92cc-119">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="c92cc-119">**Parameter**</span></span>|<span data-ttu-id="c92cc-120">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="c92cc-120">**Required**</span></span>|<span data-ttu-id="c92cc-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c92cc-121">**Type**</span></span>|<span data-ttu-id="c92cc-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c92cc-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c92cc-123">Ruoli</span><span class="sxs-lookup"><span data-stu-id="c92cc-123">Roles</span></span>  <br/> |<span data-ttu-id="c92cc-124">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="c92cc-124">Optional</span></span>  <br/> |<span data-ttu-id="c92cc-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="c92cc-125">System.Array</span></span>  <br/> | <span data-ttu-id="c92cc-126">Array di ruoli del server Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c92cc-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c92cc-127">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="c92cc-127">Input Types</span></span>
<span data-ttu-id="c92cc-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c92cc-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c92cc-129">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="c92cc-129">None.</span></span> <span data-ttu-id="c92cc-130">Il cmdlet Renew-CcServerCertificate non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="c92cc-130">The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c92cc-131">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="c92cc-131">Return Types</span></span>
<span data-ttu-id="c92cc-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c92cc-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c92cc-133">None</span><span class="sxs-lookup"><span data-stu-id="c92cc-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c92cc-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c92cc-134">See also</span></span>
<span data-ttu-id="c92cc-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c92cc-135"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="c92cc-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="c92cc-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="c92cc-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="c92cc-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="c92cc-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="c92cc-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

