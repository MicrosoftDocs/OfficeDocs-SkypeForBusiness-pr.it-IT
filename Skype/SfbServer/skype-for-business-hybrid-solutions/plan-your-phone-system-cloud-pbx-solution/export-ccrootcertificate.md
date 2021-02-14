---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Il cmdlet Export-CcRootCertificate esporta il certificato CA radice in un file locale nel server host Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800916"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="5865a-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="5865a-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="5865a-104">Il cmdlet Export-CcRootCertificate esporta il certificato CA radice in un file locale nel server host Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="5865a-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="5865a-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="5865a-105">Examples</span></span>
<span data-ttu-id="5865a-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5865a-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="5865a-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="5865a-107">Example 1</span></span>

<span data-ttu-id="5865a-108">Nell'esempio seguente il parametro Path viene impostato come percorso di directory e non come percorso di file.</span><span class="sxs-lookup"><span data-stu-id="5865a-108">The following example sets the Path parameter as a directory path—not a file path.</span></span> <span data-ttu-id="5865a-109">Viene generato il file c:\test\CCERootCertificates.p7b.</span><span class="sxs-lookup"><span data-stu-id="5865a-109">It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="5865a-110">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="5865a-110">Detailed Description</span></span>
<span data-ttu-id="5865a-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5865a-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="5865a-112">Il Export-CcRootCertificate consente di salvare i certificati radice e intermedi in un percorso file.</span><span class="sxs-lookup"><span data-stu-id="5865a-112">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path.</span></span> <span data-ttu-id="5865a-113">Ciò può essere utile in caso di uno scenario di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="5865a-113">This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="5865a-114">Parametri</span><span class="sxs-lookup"><span data-stu-id="5865a-114">Parameters</span></span>
<span data-ttu-id="5865a-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5865a-115"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="5865a-116">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="5865a-116">**Parameter**</span></span>|<span data-ttu-id="5865a-117">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="5865a-117">**Required**</span></span>|<span data-ttu-id="5865a-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5865a-118">**Type**</span></span>|<span data-ttu-id="5865a-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5865a-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5865a-120">Percorso</span><span class="sxs-lookup"><span data-stu-id="5865a-120">Path</span></span>  <br/> |<span data-ttu-id="5865a-121">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="5865a-121">Required</span></span>  <br/> |<span data-ttu-id="5865a-122">System.String</span><span class="sxs-lookup"><span data-stu-id="5865a-122">System.String</span></span>  <br/> |<span data-ttu-id="5865a-123">Percorso del file in cui verrà archiviato il certificato.</span><span class="sxs-lookup"><span data-stu-id="5865a-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5865a-124">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="5865a-124">Input Types</span></span>
<span data-ttu-id="5865a-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5865a-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="5865a-126">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="5865a-126">None.</span></span> <span data-ttu-id="5865a-127">Il cmdlet Export-CcRootCertificate non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="5865a-127">The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="5865a-128">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="5865a-128">Return Types</span></span>
<span data-ttu-id="5865a-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5865a-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5865a-130">None</span><span class="sxs-lookup"><span data-stu-id="5865a-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5865a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5865a-131">See also</span></span>
<span data-ttu-id="5865a-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5865a-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5865a-133">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5865a-133">None</span></span>
  

