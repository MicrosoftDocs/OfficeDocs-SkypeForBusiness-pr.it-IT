---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Il cmdlet Start-CcDownload Scarica in modo sincrono i bit di Skype for Business Cloud Connector Edition e il file MSI.
ms.openlocfilehash: 5c493862151a308208bf83e142421f3257e476e0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003186"
---
# <a name="start-ccdownload"></a><span data-ttu-id="84429-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="84429-103">Start-CcDownload</span></span>
 
<span data-ttu-id="84429-104">Il cmdlet Start-CcDownload Scarica in modo sincrono i bit di Skype for Business Cloud Connector Edition e il file MSI.</span><span class="sxs-lookup"><span data-stu-id="84429-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="84429-105">Con Cloud Connector versione 2,0 e successive è anche possibile specificare il parametro DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="84429-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="84429-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="84429-106">Examples</span></span>
<span data-ttu-id="84429-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="84429-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="84429-108">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="84429-108">Example 1</span></span>

<span data-ttu-id="84429-109">L'esempio seguente Scarica i bit del connettore Cloud e il file MSI in modo sincrono dal sito di download pubblico di Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="84429-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="84429-110">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="84429-110">Example 2</span></span>

<span data-ttu-id="84429-111">L'esempio seguente Scarica i bit del connettore Cloud e il file MSI in modo sincrono da un sito di download privato:</span><span class="sxs-lookup"><span data-stu-id="84429-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="84429-112">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="84429-112">Example 3</span></span>

<span data-ttu-id="84429-113">Il terzo esempio Scarica i bit del connettore Cloud e il file MSI in modo sincrono da un sito di download privato.</span><span class="sxs-lookup"><span data-stu-id="84429-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="84429-114">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="84429-114">Detailed Description</span></span>
<span data-ttu-id="84429-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="84429-115"></span></span>

<span data-ttu-id="84429-116">Se nel sito di download è disponibile una nuova versione, Start-CcDownload scaricherà e installerà il file MSI dal sito di download e quindi scaricherà i bit del connettore Cloud in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="84429-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="84429-117">Se non è disponibile una nuova versione del file MSI, Start-CcDownload scaricherà solo i bit del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="84429-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="84429-118">Se i bit del connettore Cloud sono già scaricati, Start-CcDownload non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="84429-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="84429-119">Parametri</span><span class="sxs-lookup"><span data-stu-id="84429-119">Parameters</span></span>
<span data-ttu-id="84429-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="84429-120"></span></span>

|<span data-ttu-id="84429-121">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="84429-121">**Parameter**</span></span>|<span data-ttu-id="84429-122">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="84429-122">**Required**</span></span>|<span data-ttu-id="84429-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="84429-123">**Type**</span></span>|<span data-ttu-id="84429-124">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="84429-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84429-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="84429-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="84429-126">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="84429-126">Optional</span></span> <br/> |<span data-ttu-id="84429-127">System.String</span><span class="sxs-lookup"><span data-stu-id="84429-127">System.String</span></span>  <br/> | <span data-ttu-id="84429-128">URL completo di una versione specifica di Cloud Connector nel sito di download privato.</span><span class="sxs-lookup"><span data-stu-id="84429-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="84429-129">Usa questo parametro con cautela, assicurati di essere a conoscenza della versione di Cloud Connector che stai scaricando.</span><span class="sxs-lookup"><span data-stu-id="84429-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="84429-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="84429-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="84429-131">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="84429-131">Optional</span></span>  <br/> |<span data-ttu-id="84429-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="84429-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="84429-133">Ignorare il passaggio per scaricare e installare MSI dal sito di download, scaricare solo i bit del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="84429-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="84429-134">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="84429-134">Input Types</span></span>
<span data-ttu-id="84429-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="84429-135"></span></span>

<span data-ttu-id="84429-136">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="84429-136">None.</span></span> <span data-ttu-id="84429-137">Il cmdlet Start-CcDownload non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="84429-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="84429-138">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="84429-138">Return Types</span></span>
<span data-ttu-id="84429-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="84429-139"></span></span>

<span data-ttu-id="84429-140">Nessuno</span><span class="sxs-lookup"><span data-stu-id="84429-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="84429-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84429-141">See also</span></span>
<span data-ttu-id="84429-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="84429-142"></span></span>

<span data-ttu-id="84429-143">Nessuno</span><span class="sxs-lookup"><span data-stu-id="84429-143">None</span></span>
  

