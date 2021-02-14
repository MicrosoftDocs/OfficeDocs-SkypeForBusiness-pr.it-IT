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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: Il Update-CcServerCertificate consente di rinnovare i certificati per Skype for Business Cloud Connector Edition quando sono prossimi alla scadenza o sono già scaduti.
ms.openlocfilehash: da52efcd3fdf6a0793e085098bf6f72725115e9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824110"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="28e4b-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="28e4b-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="28e4b-104">Il Update-CcServerCertificate consente di rinnovare i certificati per Skype for Business Cloud Connector Edition quando sono prossimi alla scadenza o sono già scaduti.</span><span class="sxs-lookup"><span data-stu-id="28e4b-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="28e4b-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="28e4b-105">Examples</span></span>
<span data-ttu-id="28e4b-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="28e4b-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="28e4b-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="28e4b-107">Example 1</span></span>

<span data-ttu-id="28e4b-108">Nell'esempio seguente vengono rinnovati i certificati per l'archivio di gestione centrale, il Mediation Server e il server perimetrale quando i certificati sono prossimi alla scadenza o sono già scaduti:</span><span class="sxs-lookup"><span data-stu-id="28e4b-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="28e4b-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="28e4b-109">Example 2</span></span>

<span data-ttu-id="28e4b-110">Nell'esempio seguente vengono rinnovati i certificati per Mediation Server ed Edge Server quando sono prossimi alla scadenza o sono già scaduti:</span><span class="sxs-lookup"><span data-stu-id="28e4b-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="28e4b-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="28e4b-111">Detailed Description</span></span>
<span data-ttu-id="28e4b-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="28e4b-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="28e4b-113">I certificati interni del connettore cloud emessi per l'archivio di gestione centrale, il Mediation Server e il server perimetrale sono validi per due anni dopo l'emissione da un servizio autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="28e4b-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="28e4b-114">Se i certificati sono prossimi alla scadenza o sono già scaduti, eseguire il cmdlet Update-CcServerCertificate per rinnovare i certificati.</span><span class="sxs-lookup"><span data-stu-id="28e4b-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="28e4b-115">Questo comando sostituisce il cmdlet Renew-CcServerCertificate in Cloud Connector 2.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="28e4b-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="28e4b-116">Parametri</span><span class="sxs-lookup"><span data-stu-id="28e4b-116">Parameters</span></span>
<span data-ttu-id="28e4b-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="28e4b-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="28e4b-118">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="28e4b-118">**Parameter**</span></span>|<span data-ttu-id="28e4b-119">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="28e4b-119">**Required**</span></span>|<span data-ttu-id="28e4b-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="28e4b-120">**Type**</span></span>|<span data-ttu-id="28e4b-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="28e4b-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28e4b-122">Ruoli</span><span class="sxs-lookup"><span data-stu-id="28e4b-122">Roles</span></span>  <br/> |<span data-ttu-id="28e4b-123">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="28e4b-123">Optional</span></span>  <br/> |<span data-ttu-id="28e4b-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="28e4b-124">System.Array</span></span>  <br/> | <span data-ttu-id="28e4b-125">Array di ruoli del server Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="28e4b-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="28e4b-126">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="28e4b-126">Input Types</span></span>
<span data-ttu-id="28e4b-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="28e4b-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="28e4b-128">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="28e4b-128">None.</span></span> <span data-ttu-id="28e4b-129">Il cmdlet Update-CcServerCertificate non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="28e4b-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="28e4b-130">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="28e4b-130">Return Types</span></span>
<span data-ttu-id="28e4b-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="28e4b-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="28e4b-132">None</span><span class="sxs-lookup"><span data-stu-id="28e4b-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="28e4b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28e4b-133">See also</span></span>
<span data-ttu-id="28e4b-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="28e4b-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="28e4b-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="28e4b-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="28e4b-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="28e4b-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="28e4b-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="28e4b-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

