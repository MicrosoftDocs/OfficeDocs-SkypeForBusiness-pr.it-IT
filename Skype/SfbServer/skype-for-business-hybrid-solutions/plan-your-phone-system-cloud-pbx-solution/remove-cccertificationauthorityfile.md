---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: Il cmdlet Remove-CcCertificationAuthorityFile rimuove il file di backup del servizio autorità di certificazione nella cartella CA nella directory della condivisione del sito per Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824292"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="a1fae-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="a1fae-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="a1fae-104">Il cmdlet Remove-CcCertificationAuthorityFile rimuove il file di backup del servizio dell'autorità di certificazione " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" nella cartella CA nella directory della condivisione del sito per Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="a1fae-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="a1fae-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1fae-105">Parameters</span></span>

<span data-ttu-id="a1fae-106">None</span><span class="sxs-lookup"><span data-stu-id="a1fae-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="a1fae-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="a1fae-107">Examples</span></span>
<span data-ttu-id="a1fae-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a1fae-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="a1fae-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="a1fae-109">Example 1</span></span>

<span data-ttu-id="a1fae-110">Nell'esempio seguente viene rimosso il file di backup del servizio autorità di certificazione " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" nella cartella CA nella directory della condivisione del sito:</span><span class="sxs-lookup"><span data-stu-id="a1fae-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="a1fae-111">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="a1fae-111">Input Types</span></span>
<span data-ttu-id="a1fae-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a1fae-112"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="a1fae-113">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="a1fae-113">None.</span></span> <span data-ttu-id="a1fae-114">Il cmdlet Remove-CcCertificationAuthorityFile non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="a1fae-114">The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a1fae-115">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="a1fae-115">Return Types</span></span>
<span data-ttu-id="a1fae-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a1fae-116"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a1fae-117">None</span><span class="sxs-lookup"><span data-stu-id="a1fae-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a1fae-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1fae-118">See also</span></span>
<span data-ttu-id="a1fae-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a1fae-119"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="a1fae-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="a1fae-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  

