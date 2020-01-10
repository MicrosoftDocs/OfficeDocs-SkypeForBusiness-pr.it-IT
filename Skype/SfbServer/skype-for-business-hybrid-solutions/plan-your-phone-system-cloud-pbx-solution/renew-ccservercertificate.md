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
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: Il cmdlet Renew-CcServerCertificate rinnova i certificati per Skype for Business Cloud Connector Edition quando è vicino alla scadenza o è già scaduto. Questo comando è stato modificato in Update-CcServerCertificate in Cloud Connector 2,0 e versioni successive.
ms.openlocfilehash: 47f2bbefa6510ae49e2e4a3ddc321e288dee266e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003266"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="97185-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="97185-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="97185-105">Il cmdlet Renew-CcServerCertificate rinnova i certificati per Skype for Business Cloud Connector Edition quando è vicino alla scadenza o è già scaduto.</span><span class="sxs-lookup"><span data-stu-id="97185-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="97185-106">Questo comando è stato modificato in Update-CcServerCertificate in Cloud Connector 2,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="97185-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="97185-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="97185-107">Examples</span></span>
<span data-ttu-id="97185-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="97185-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="97185-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="97185-109">Example 1</span></span>

<span data-ttu-id="97185-110">L'esempio seguente rinnova i certificati per l'archivio di gestione centrale, il Mediation Server e il server perimetrale quando i certificati sono a scadenza quasi scaduta o già scaduti:</span><span class="sxs-lookup"><span data-stu-id="97185-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="97185-111">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="97185-111">Example 2</span></span>

<span data-ttu-id="97185-112">Nell'esempio successivo vengono rinnovati i certificati per Mediation Server e Edge Server quando la scadenza è prossima o è già scaduta:</span><span class="sxs-lookup"><span data-stu-id="97185-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="97185-113">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="97185-113">Detailed Description</span></span>
<span data-ttu-id="97185-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="97185-114"></span></span>

<span data-ttu-id="97185-115">I certificati interni del connettore Cloud rilasciati a Central Management store, Mediation Server e Edge Server sono validi per due anni dopo il rilascio da parte di un servizio autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="97185-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="97185-116">Se i certificati sono a scadenza quasi scaduta o già scaduti, eseguire il cmdlet Renew-CcServerCertificate per rinnovare i certificati.</span><span class="sxs-lookup"><span data-stu-id="97185-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="97185-117">Parametri</span><span class="sxs-lookup"><span data-stu-id="97185-117">Parameters</span></span>
<span data-ttu-id="97185-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="97185-118"></span></span>

|<span data-ttu-id="97185-119">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="97185-119">**Parameter**</span></span>|<span data-ttu-id="97185-120">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="97185-120">**Required**</span></span>|<span data-ttu-id="97185-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="97185-121">**Type**</span></span>|<span data-ttu-id="97185-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="97185-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="97185-123">Ruoli</span><span class="sxs-lookup"><span data-stu-id="97185-123">Roles</span></span>  <br/> |<span data-ttu-id="97185-124">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="97185-124">Optional</span></span>  <br/> |<span data-ttu-id="97185-125">System. Array</span><span class="sxs-lookup"><span data-stu-id="97185-125">System.Array</span></span>  <br/> | <span data-ttu-id="97185-126">Matrice di ruoli del server del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="97185-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="97185-127">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="97185-127">Input Types</span></span>
<span data-ttu-id="97185-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="97185-128"></span></span>

<span data-ttu-id="97185-129">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="97185-129">None.</span></span> <span data-ttu-id="97185-130">Il cmdlet Renew-CcServerCertificate non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="97185-130">The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="97185-131">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="97185-131">Return Types</span></span>
<span data-ttu-id="97185-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="97185-132"></span></span>

<span data-ttu-id="97185-133">Nessuno</span><span class="sxs-lookup"><span data-stu-id="97185-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="97185-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97185-134">See also</span></span>
<span data-ttu-id="97185-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="97185-135"></span></span>

[<span data-ttu-id="97185-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="97185-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="97185-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="97185-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="97185-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="97185-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

