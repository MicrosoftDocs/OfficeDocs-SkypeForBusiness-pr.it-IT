---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: Il cmdlet Update-CcServerCertificate rinnova i certificati per Skype for Business Cloud Connector Edition quando è vicino alla scadenza o è già scaduto.
ms.openlocfilehash: 34da35e607f8941da9c962386509f8a0b87ec122
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190574"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="46773-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="46773-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="46773-104">Il cmdlet Update-CcServerCertificate rinnova i certificati per Skype for Business Cloud Connector Edition quando è vicino alla scadenza o è già scaduto.</span><span class="sxs-lookup"><span data-stu-id="46773-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="46773-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="46773-105">Examples</span></span>
<span data-ttu-id="46773-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="46773-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="46773-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="46773-107">Example 1</span></span>

<span data-ttu-id="46773-108">L'esempio seguente rinnova i certificati per l'archivio di gestione centrale, il Mediation Server e il server perimetrale quando i certificati sono a scadenza quasi scaduta o già scaduti:</span><span class="sxs-lookup"><span data-stu-id="46773-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="46773-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="46773-109">Example 2</span></span>

<span data-ttu-id="46773-110">Nell'esempio successivo vengono rinnovati i certificati per Mediation Server e Edge Server quando la scadenza è prossima o è già scaduta:</span><span class="sxs-lookup"><span data-stu-id="46773-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="46773-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="46773-111">Detailed Description</span></span>
<span data-ttu-id="46773-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="46773-112"></span></span>

<span data-ttu-id="46773-113">I certificati interni del connettore Cloud rilasciati a Central Management store, Mediation Server e Edge Server sono validi per due anni dopo il rilascio da parte di un servizio autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="46773-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="46773-114">Se i certificati sono a scadenza quasi scaduta o già scaduti, eseguire il cmdlet Update-CcServerCertificate per rinnovare i certificati.</span><span class="sxs-lookup"><span data-stu-id="46773-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="46773-115">Questo comando sostituisce il cmdlet Renew-CcServerCertificate in Cloud Connector 2,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="46773-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="46773-116">Parametri</span><span class="sxs-lookup"><span data-stu-id="46773-116">Parameters</span></span>
<span data-ttu-id="46773-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="46773-117"></span></span>

|<span data-ttu-id="46773-118">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="46773-118">**Parameter**</span></span>|<span data-ttu-id="46773-119">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="46773-119">**Required**</span></span>|<span data-ttu-id="46773-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="46773-120">**Type**</span></span>|<span data-ttu-id="46773-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="46773-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="46773-122">Ruoli</span><span class="sxs-lookup"><span data-stu-id="46773-122">Roles</span></span>  <br/> |<span data-ttu-id="46773-123">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="46773-123">Optional</span></span>  <br/> |<span data-ttu-id="46773-124">System. Array</span><span class="sxs-lookup"><span data-stu-id="46773-124">System.Array</span></span>  <br/> | <span data-ttu-id="46773-125">Matrice di ruoli del server del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="46773-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="46773-126">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="46773-126">Input Types</span></span>
<span data-ttu-id="46773-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="46773-127"></span></span>

<span data-ttu-id="46773-128">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="46773-128">None.</span></span> <span data-ttu-id="46773-129">Il cmdlet Update-CcServerCertificate non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="46773-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="46773-130">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="46773-130">Return Types</span></span>
<span data-ttu-id="46773-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="46773-131"></span></span>

<span data-ttu-id="46773-132">Nessuno</span><span class="sxs-lookup"><span data-stu-id="46773-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="46773-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46773-133">See also</span></span>
<span data-ttu-id="46773-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="46773-134"></span></span>

[<span data-ttu-id="46773-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="46773-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="46773-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="46773-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="46773-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="46773-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

