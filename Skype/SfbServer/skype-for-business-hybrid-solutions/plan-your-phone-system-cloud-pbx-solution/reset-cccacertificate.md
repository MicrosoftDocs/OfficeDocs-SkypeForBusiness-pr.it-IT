---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Il cmdlet Reset-CcCACertificate reinstalla il server degli annunci del servizio autorità di certificazione per creare un nuovo certificato della CA radice.
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824252"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="90c41-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="90c41-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="90c41-104">Il cmdlet Reset-CcCACertificate reinstalla il server degli annunci del servizio autorità di certificazione per creare un nuovo certificato della CA radice.</span><span class="sxs-lookup"><span data-stu-id="90c41-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="90c41-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="90c41-105">Parameters</span></span>

<span data-ttu-id="90c41-106">Nessuno</span><span class="sxs-lookup"><span data-stu-id="90c41-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="90c41-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="90c41-107">Examples</span></span>
<span data-ttu-id="90c41-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="90c41-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="90c41-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="90c41-109">Example 1</span></span>

<span data-ttu-id="90c41-110">L'esempio seguente reinstalla il server degli annunci del servizio autorità di certificazione per creare un nuovo certificato della CA radice:</span><span class="sxs-lookup"><span data-stu-id="90c41-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="90c41-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="90c41-111">Detailed Description</span></span>
<span data-ttu-id="90c41-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="90c41-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="90c41-113">Se il certificato della CA radice è compromesso o non è più sicuro, è necessario aggiornare il certificato della CA radice e tutti i certificati emessi dalla CA radice.</span><span class="sxs-lookup"><span data-stu-id="90c41-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="90c41-114">Il cmdlet Reset-CcCACertificate revoca tutti i certificati, disinstalla e reinstalla l'autorità di certificazione e quindi pulisce tutti i certificati relativi al vecchio servizio autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="90c41-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="90c41-115">Per altre informazioni, vedere "i certificati di autorità di certificazione o i certificati interni rilasciati a CMS, Mediation Server e Edge Server sono scaduti o compromessi" in risoluzione dei problemi relativi alla distribuzione di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="90c41-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="90c41-116">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="90c41-116">Input Types</span></span>
<span data-ttu-id="90c41-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="90c41-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="90c41-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="90c41-118">None.</span></span> <span data-ttu-id="90c41-119">Il cmdlet Reset-CcCACertificate non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="90c41-119">The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="90c41-120">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="90c41-120">Return Types</span></span>
<span data-ttu-id="90c41-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="90c41-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="90c41-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="90c41-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="90c41-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90c41-123">See also</span></span>
<span data-ttu-id="90c41-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="90c41-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="90c41-125">[Renew-CcCACertificate](renew-cccacertificate.md) Solo versione 1.4.2</span><span class="sxs-lookup"><span data-stu-id="90c41-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="90c41-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Solo versione 1.4.2</span><span class="sxs-lookup"><span data-stu-id="90c41-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="90c41-127">[Update-CcCACertificate](update-cccacertificate.md) Versione 2,0 e successive</span><span class="sxs-lookup"><span data-stu-id="90c41-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="90c41-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Versione 2,0 e successive</span><span class="sxs-lookup"><span data-stu-id="90c41-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="90c41-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="90c41-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

