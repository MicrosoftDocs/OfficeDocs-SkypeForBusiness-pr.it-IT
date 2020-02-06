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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Il cmdlet Renew-CcCACertificate rinnova il certificato della CA radice di Skype for Business Cloud Connector Edition che è vicino alla scadenza o è già scaduto. Questo comando è stato modificato in Update-CcCACertificate in Cloud Connector 2,0 e versioni successive.
ms.openlocfilehash: e92709cd1da0ffccd2b356000dbd2345ba56a1d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824272"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="3f348-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="3f348-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="3f348-105">Il cmdlet Renew-CcCACertificate rinnova il certificato della CA radice di Skype for Business Cloud Connector Edition che è vicino alla scadenza o è già scaduto.</span><span class="sxs-lookup"><span data-stu-id="3f348-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="3f348-106">Questo comando è stato modificato in Update-CcCACertificate in Cloud Connector 2,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="3f348-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="3f348-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f348-107">Parameters</span></span>

<span data-ttu-id="3f348-108">Nessuno</span><span class="sxs-lookup"><span data-stu-id="3f348-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="3f348-109">Esempi</span><span class="sxs-lookup"><span data-stu-id="3f348-109">Examples</span></span>
<span data-ttu-id="3f348-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3f348-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="3f348-111">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="3f348-111">Example 1</span></span>

<span data-ttu-id="3f348-112">L'esempio seguente rinnova il certificato della CA radice:</span><span class="sxs-lookup"><span data-stu-id="3f348-112">The following example renews the root CA certificate:</span></span> 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="3f348-113">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="3f348-113">Detailed Description</span></span>
<span data-ttu-id="3f348-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3f348-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="3f348-115">Il certificato della CA radice del connettore Cloud è valido per cinque anni dalla data in cui è installato il servizio autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="3f348-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="3f348-116">Se il certificato radice è vicino alla scadenza o è già scaduto, eseguire il cmdlet Renew-CcCACertificate per rinnovare il certificato.</span><span class="sxs-lookup"><span data-stu-id="3f348-116">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="3f348-117">Dopo il rinnovo del certificato radice, verranno emessi automaticamente nuovi certificati nel server AD, Central Management store e Edge Server.</span><span class="sxs-lookup"><span data-stu-id="3f348-117">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="3f348-118">Se sono presenti più dispositivi nello stesso sito PSTN, eseguire il cmdlet Renew-CcCACertificate in tutti gli apparecchi dello stesso sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="3f348-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="3f348-119">Come ultimo passaggio, eseguire Export-CcRootCertificate per esportare il certificato radice in un file locale nel primo appliance, quindi copiare e installare il certificato esportato nei gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="3f348-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="3f348-120">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="3f348-120">Input Types</span></span>
<span data-ttu-id="3f348-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3f348-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="3f348-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3f348-122">None.</span></span> <span data-ttu-id="3f348-123">Il cmdlet Renew-CcCACertificate non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="3f348-123">The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3f348-124">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="3f348-124">Return Types</span></span>
<span data-ttu-id="3f348-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3f348-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="3f348-126">Nessuno</span><span class="sxs-lookup"><span data-stu-id="3f348-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3f348-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f348-127">See also</span></span>
<span data-ttu-id="3f348-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3f348-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="3f348-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="3f348-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="3f348-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="3f348-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="3f348-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="3f348-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

