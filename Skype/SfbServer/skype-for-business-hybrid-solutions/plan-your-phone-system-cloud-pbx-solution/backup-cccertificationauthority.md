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
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Il cmdlet Backup-CcCertificationAuthority esegue il backup del servizio dell'autorità di certificazione di Skype for Business Cloud Connector Edition in un file e lo salva nella cartella CA nella directory della condivisione del sito.
ms.openlocfilehash: 463aab2516deec5b47e549aec67bcba6a0a80bc0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194545"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="165ff-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="165ff-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="165ff-104">Il cmdlet Backup-CcCertificationAuthority esegue il backup del servizio dell'autorità di certificazione di Skype for Business Cloud Connector Edition in un file e lo salva nella cartella CA nella directory della condivisione del sito.</span><span class="sxs-lookup"><span data-stu-id="165ff-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="165ff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="165ff-105">Parameters</span></span>

<span data-ttu-id="165ff-106">Nessuno</span><span class="sxs-lookup"><span data-stu-id="165ff-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="165ff-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="165ff-107">Examples</span></span>
<span data-ttu-id="165ff-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="165ff-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="165ff-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="165ff-109">Example 1</span></span>

<span data-ttu-id="165ff-110">L'esempio seguente consente di eseguire il backup del servizio autorità di certificazione in un file e di salvarlo nella cartella CA nella directory della condivisione del sito:</span><span class="sxs-lookup"><span data-stu-id="165ff-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="165ff-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="165ff-111">Detailed Description</span></span>
<span data-ttu-id="165ff-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="165ff-112"></span></span>

<span data-ttu-id="165ff-113">Il backup dell'autorità di certificazione può essere utile se si prevede di ridistribuire un dispositivo Cloud Connector con lo stesso certificato in caso di emergenza o se si vuole trasferire l'accessorio in un nuovo hardware.</span><span class="sxs-lookup"><span data-stu-id="165ff-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="165ff-114">Il comando Salva la copia del servizio autorità di certificazione Cloud Connector dal server di annunci in "\<SITEROOTDIRECTORY\>\CA\SfB CCE root. p12".</span><span class="sxs-lookup"><span data-stu-id="165ff-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="165ff-115">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="165ff-115">Input Types</span></span>
<span data-ttu-id="165ff-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="165ff-116"></span></span>

<span data-ttu-id="165ff-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="165ff-117">None.</span></span> <span data-ttu-id="165ff-118">Il cmdlet Backup-CcCertificationAuthority non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="165ff-118">The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="165ff-119">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="165ff-119">Return Types</span></span>
<span data-ttu-id="165ff-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="165ff-120"></span></span>

<span data-ttu-id="165ff-121">Nessuno</span><span class="sxs-lookup"><span data-stu-id="165ff-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="165ff-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="165ff-122">See also</span></span>
<span data-ttu-id="165ff-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="165ff-123"></span></span>

[<span data-ttu-id="165ff-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="165ff-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

