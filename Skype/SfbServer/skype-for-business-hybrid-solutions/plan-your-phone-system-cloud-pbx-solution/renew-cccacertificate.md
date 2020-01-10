---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Il cmdlet Renew-CcCACertificate rinnova il certificato della CA radice di Skype for Business Cloud Connector Edition che è vicino alla scadenza o è già scaduto. Questo comando è stato modificato in Update-CcCACertificate in Cloud Connector 2,0 e versioni successive.
ms.openlocfilehash: 493b733eab9cbd8331a93d72dc4a865f3574fbe8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003276"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="77037-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="77037-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="77037-105">Il cmdlet Renew-CcCACertificate rinnova il certificato della CA radice di Skype for Business Cloud Connector Edition che è vicino alla scadenza o è già scaduto.</span><span class="sxs-lookup"><span data-stu-id="77037-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="77037-106">Questo comando è stato modificato in Update-CcCACertificate in Cloud Connector 2,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="77037-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="77037-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="77037-107">Parameters</span></span>

<span data-ttu-id="77037-108">Nessuno</span><span class="sxs-lookup"><span data-stu-id="77037-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="77037-109">Esempi</span><span class="sxs-lookup"><span data-stu-id="77037-109">Examples</span></span>
<span data-ttu-id="77037-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="77037-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="77037-111">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="77037-111">Example 1</span></span>

<span data-ttu-id="77037-112">L'esempio seguente rinnova il certificato della CA radice:</span><span class="sxs-lookup"><span data-stu-id="77037-112">The following example renews the root CA certificate:</span></span> 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="77037-113">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="77037-113">Detailed Description</span></span>
<span data-ttu-id="77037-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="77037-114"></span></span>

<span data-ttu-id="77037-115">Il certificato della CA radice del connettore Cloud è valido per cinque anni dalla data in cui è installato il servizio autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="77037-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="77037-116">Se il certificato radice è vicino alla scadenza o è già scaduto, eseguire il cmdlet Renew-CcCACertificate per rinnovare il certificato.</span><span class="sxs-lookup"><span data-stu-id="77037-116">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="77037-117">Dopo il rinnovo del certificato radice, verranno emessi automaticamente nuovi certificati nel server AD, Central Management store e Edge Server.</span><span class="sxs-lookup"><span data-stu-id="77037-117">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="77037-118">Se sono presenti più dispositivi nello stesso sito PSTN, eseguire il cmdlet Renew-CcCACertificate in tutti gli apparecchi dello stesso sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="77037-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="77037-119">Come ultimo passaggio, eseguire Export-CcRootCertificate per esportare il certificato radice in un file locale nel primo appliance, quindi copiare e installare il certificato esportato nei gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="77037-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="77037-120">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="77037-120">Input Types</span></span>
<span data-ttu-id="77037-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="77037-121"></span></span>

<span data-ttu-id="77037-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="77037-122">None.</span></span> <span data-ttu-id="77037-123">Il cmdlet Renew-CcCACertificate non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="77037-123">The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="77037-124">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="77037-124">Return Types</span></span>
<span data-ttu-id="77037-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="77037-125"></span></span>

<span data-ttu-id="77037-126">Nessuno</span><span class="sxs-lookup"><span data-stu-id="77037-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="77037-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77037-127">See also</span></span>
<span data-ttu-id="77037-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="77037-128"></span></span>

[<span data-ttu-id="77037-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="77037-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="77037-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="77037-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="77037-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="77037-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

