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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: Il cmdlet Update-CcCACertificate consente di rinnovare il certificato CA radice Skype for Business Cloud Connector Edition che sta per scadere o è già scaduto.
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824120"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="6b2e2-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="6b2e2-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="6b2e2-104">Il cmdlet Update-CcCACertificate consente di rinnovare il certificato CA radice Skype for Business Cloud Connector Edition che sta per scadere o è già scaduto.</span><span class="sxs-lookup"><span data-stu-id="6b2e2-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="6b2e2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6b2e2-105">Parameters</span></span>

<span data-ttu-id="6b2e2-106">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="6b2e2-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="6b2e2-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="6b2e2-107">Examples</span></span>
<span data-ttu-id="6b2e2-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6b2e2-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="6b2e2-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="6b2e2-109">Example 1</span></span>

<span data-ttu-id="6b2e2-110">Nell'esempio seguente viene rinnovato il certificato CA radice:</span><span class="sxs-lookup"><span data-stu-id="6b2e2-110">The following example renews the root CA certificate:</span></span> 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="6b2e2-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="6b2e2-111">Detailed Description</span></span>
<span data-ttu-id="6b2e2-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6b2e2-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="6b2e2-113">Il certificato DELLA CA radice del connettore cloud è valido per cinque anni dalla data di installazione del servizio Autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="6b2e2-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="6b2e2-114">Se il certificato radice è prossimo alla scadenza o è già scaduto, eseguire il cmdlet Update-CcCACertificate per rinnovare il certificato.</span><span class="sxs-lookup"><span data-stu-id="6b2e2-114">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="6b2e2-115">Dopo il rinnovo del certificato radice, i nuovi certificati verranno emessi automaticamente dal server AD, dall'archivio di gestione centrale e dal server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="6b2e2-115">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="6b2e2-116">Se sono presenti più appliance nello stesso sito PSTN, eseguire il cmdlet Update-CcCACertificate in tutte le appliance dello stesso sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="6b2e2-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="6b2e2-117">Come ultimo passaggio, eseguire Export-CcRootCertificate per esportare il certificato radice in un file locale nel primo dispositivo, quindi copiare e installare il certificato esportato nei gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="6b2e2-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="6b2e2-118">Questo comando sostituisce il cmdlet Renew-CcCACertificate in Cloud Connector 2.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="6b2e2-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="6b2e2-119">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="6b2e2-119">Input Types</span></span>
<span data-ttu-id="6b2e2-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6b2e2-120"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="6b2e2-121">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="6b2e2-121">None.</span></span> <span data-ttu-id="6b2e2-122">Il cmdlet Update-CcCACertificate non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="6b2e2-122">The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6b2e2-123">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="6b2e2-123">Return Types</span></span>
<span data-ttu-id="6b2e2-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6b2e2-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="6b2e2-125">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="6b2e2-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6b2e2-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b2e2-126">See also</span></span>
<span data-ttu-id="6b2e2-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6b2e2-127"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="6b2e2-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="6b2e2-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="6b2e2-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="6b2e2-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="6b2e2-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="6b2e2-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

