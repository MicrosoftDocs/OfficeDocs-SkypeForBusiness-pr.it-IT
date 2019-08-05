---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: Il cmdlet Update-CcCACertificate rinnova il certificato della CA radice di Skype for Business Cloud Connector Edition che è vicino alla scadenza o è già scaduto.
ms.openlocfilehash: e32b910d07aa4f2370af72d0a04bb939b80b3034
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190580"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="11cac-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="11cac-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="11cac-104">Il cmdlet Update-CcCACertificate rinnova il certificato della CA radice di Skype for Business Cloud Connector Edition che è vicino alla scadenza o è già scaduto.</span><span class="sxs-lookup"><span data-stu-id="11cac-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="11cac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="11cac-105">Parameters</span></span>

<span data-ttu-id="11cac-106">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="11cac-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="11cac-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="11cac-107">Examples</span></span>
<span data-ttu-id="11cac-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="11cac-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="11cac-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="11cac-109">Example 1</span></span>

<span data-ttu-id="11cac-110">L'esempio seguente rinnova il certificato della CA radice:</span><span class="sxs-lookup"><span data-stu-id="11cac-110">The following example renews the root CA certificate:</span></span> 
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="11cac-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="11cac-111">Detailed Description</span></span>
<span data-ttu-id="11cac-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="11cac-112"></span></span>

<span data-ttu-id="11cac-113">Il certificato della CA radice del connettore Cloud è valido per cinque anni dalla data in cui è installato il servizio autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="11cac-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="11cac-114">Se il certificato radice è vicino alla scadenza o è già scaduto, eseguire il cmdlet Update-CcCACertificate per rinnovare il certificato.</span><span class="sxs-lookup"><span data-stu-id="11cac-114">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="11cac-115">Dopo il rinnovo del certificato radice, verranno emessi automaticamente nuovi certificati nel server AD, Central Management store e Edge Server.</span><span class="sxs-lookup"><span data-stu-id="11cac-115">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="11cac-116">Se sono presenti più dispositivi nello stesso sito PSTN, eseguire il cmdlet Update-CcCACertificate in tutti gli apparecchi dello stesso sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="11cac-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="11cac-117">Come ultimo passaggio, eseguire Export-CcRootCertificate per esportare il certificato radice in un file locale nel primo appliance, quindi copiare e installare il certificato esportato nei gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="11cac-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="11cac-118">Questo comando sostituisce il cmdlet Renew-CcCACertificate in Cloud Connector 2,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="11cac-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="11cac-119">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="11cac-119">Input Types</span></span>
<span data-ttu-id="11cac-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="11cac-120"></span></span>

<span data-ttu-id="11cac-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="11cac-121">None.</span></span> <span data-ttu-id="11cac-122">Il cmdlet Update-CcCACertificate non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="11cac-122">The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="11cac-123">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="11cac-123">Return Types</span></span>
<span data-ttu-id="11cac-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="11cac-124"></span></span>

<span data-ttu-id="11cac-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="11cac-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="11cac-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11cac-126">See also</span></span>
<span data-ttu-id="11cac-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="11cac-127"></span></span>

[<span data-ttu-id="11cac-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="11cac-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="11cac-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="11cac-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="11cac-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="11cac-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

