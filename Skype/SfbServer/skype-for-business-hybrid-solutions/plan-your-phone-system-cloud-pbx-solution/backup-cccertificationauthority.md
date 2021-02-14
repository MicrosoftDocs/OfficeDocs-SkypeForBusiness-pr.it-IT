---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Il cmdlet Backup-CcCertificationAuthority consente di eseguire il backup del servizio Autorità di certificazione Skype for Business Cloud Connector Edition in un file e di salvarlo nella cartella CA nella directory della condivisione del sito.
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803806"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="367f3-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="367f3-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="367f3-104">Il cmdlet Backup-CcCertificationAuthority consente di eseguire il backup del servizio Autorità di certificazione Skype for Business Cloud Connector Edition in un file e di salvarlo nella cartella CA nella directory della condivisione del sito.</span><span class="sxs-lookup"><span data-stu-id="367f3-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="367f3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="367f3-105">Parameters</span></span>

<span data-ttu-id="367f3-106">None</span><span class="sxs-lookup"><span data-stu-id="367f3-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="367f3-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="367f3-107">Examples</span></span>
<span data-ttu-id="367f3-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="367f3-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="367f3-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="367f3-109">Example 1</span></span>

<span data-ttu-id="367f3-110">Nell'esempio seguente viene illustrato come eseguire il backup del servizio Autorità di certificazione in un file e salvarlo nella cartella ca nella directory della condivisione del sito:</span><span class="sxs-lookup"><span data-stu-id="367f3-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="367f3-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="367f3-111">Detailed Description</span></span>
<span data-ttu-id="367f3-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="367f3-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="367f3-113">Il backup dell'Autorità di certificazione può essere utile se si prevede di ridistribuire un'applicazione Cloud Connector con lo stesso certificato in caso di emergenza o se si desidera spostare l'applicazione in un nuovo hardware.</span><span class="sxs-lookup"><span data-stu-id="367f3-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="367f3-114">Il comando salva la copia del servizio Autorità di certificazione Cloud Connector dal server AD in " \< SiteRootDirectory \> \CA\SfB CCE Root.p12".</span><span class="sxs-lookup"><span data-stu-id="367f3-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="367f3-115">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="367f3-115">Input Types</span></span>
<span data-ttu-id="367f3-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="367f3-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="367f3-117">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="367f3-117">None.</span></span> <span data-ttu-id="367f3-118">Il cmdlet Backup-CcCertificationAuthority non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="367f3-118">The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="367f3-119">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="367f3-119">Return Types</span></span>
<span data-ttu-id="367f3-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="367f3-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="367f3-121">None</span><span class="sxs-lookup"><span data-stu-id="367f3-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="367f3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="367f3-122">See also</span></span>
<span data-ttu-id="367f3-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="367f3-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="367f3-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="367f3-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

