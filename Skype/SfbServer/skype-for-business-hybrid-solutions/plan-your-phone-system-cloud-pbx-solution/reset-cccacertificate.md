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
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Il cmdlet Reset-CcCACertificate reinstalla il server degli annunci del servizio autorità di certificazione per creare un nuovo certificato della CA radice.
ms.openlocfilehash: 50c3b1afc29503b2b292ce578ea01b03aeeba368
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003256"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="3cc99-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="3cc99-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="3cc99-104">Il cmdlet Reset-CcCACertificate reinstalla il server degli annunci del servizio autorità di certificazione per creare un nuovo certificato della CA radice.</span><span class="sxs-lookup"><span data-stu-id="3cc99-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="3cc99-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3cc99-105">Parameters</span></span>

<span data-ttu-id="3cc99-106">Nessuno</span><span class="sxs-lookup"><span data-stu-id="3cc99-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="3cc99-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="3cc99-107">Examples</span></span>
<span data-ttu-id="3cc99-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3cc99-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="3cc99-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="3cc99-109">Example 1</span></span>

<span data-ttu-id="3cc99-110">L'esempio seguente reinstalla il server degli annunci del servizio autorità di certificazione per creare un nuovo certificato della CA radice:</span><span class="sxs-lookup"><span data-stu-id="3cc99-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="3cc99-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="3cc99-111">Detailed Description</span></span>
<span data-ttu-id="3cc99-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3cc99-112"></span></span>

<span data-ttu-id="3cc99-113">Se il certificato della CA radice è compromesso o non è più sicuro, è necessario aggiornare il certificato della CA radice e tutti i certificati emessi dalla CA radice.</span><span class="sxs-lookup"><span data-stu-id="3cc99-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="3cc99-114">Il cmdlet Reset-CcCACertificate revoca tutti i certificati, disinstalla e reinstalla l'autorità di certificazione e quindi pulisce tutti i certificati relativi al vecchio servizio autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="3cc99-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="3cc99-115">Per altre informazioni, vedere "i certificati di autorità di certificazione o i certificati interni rilasciati a CMS, Mediation Server e Edge Server sono scaduti o compromessi" in risoluzione dei problemi relativi alla distribuzione di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="3cc99-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="3cc99-116">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="3cc99-116">Input Types</span></span>
<span data-ttu-id="3cc99-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3cc99-117"></span></span>

<span data-ttu-id="3cc99-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3cc99-118">None.</span></span> <span data-ttu-id="3cc99-119">Il cmdlet Reset-CcCACertificate non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="3cc99-119">The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3cc99-120">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="3cc99-120">Return Types</span></span>
<span data-ttu-id="3cc99-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3cc99-121"></span></span>

<span data-ttu-id="3cc99-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3cc99-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3cc99-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cc99-123">See also</span></span>
<span data-ttu-id="3cc99-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3cc99-124"></span></span>

<span data-ttu-id="3cc99-125">[Renew-CcCACertificate](renew-cccacertificate.md) Solo versione 1.4.2</span><span class="sxs-lookup"><span data-stu-id="3cc99-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="3cc99-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Solo versione 1.4.2</span><span class="sxs-lookup"><span data-stu-id="3cc99-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="3cc99-127">[Update-CcCACertificate](update-cccacertificate.md) Versione 2,0 e successive</span><span class="sxs-lookup"><span data-stu-id="3cc99-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="3cc99-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Versione 2,0 e successive</span><span class="sxs-lookup"><span data-stu-id="3cc99-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="3cc99-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="3cc99-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

