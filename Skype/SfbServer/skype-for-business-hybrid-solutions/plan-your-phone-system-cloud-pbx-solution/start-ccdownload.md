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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Il Start-CcDownload cmdlet scarica i bit di Skype for Business Cloud Connector Edition e il file msi in modo sincrono.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824180"
---
# <a name="start-ccdownload"></a><span data-ttu-id="a0c98-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="a0c98-103">Start-CcDownload</span></span>
 
<span data-ttu-id="a0c98-104">Il Start-CcDownload cmdlet scarica i bit di Skype for Business Cloud Connector Edition e il file msi in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="a0c98-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="a0c98-105">Con Cloud Connector versione 2.0 e successive, è anche possibile specificare il parametro DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="a0c98-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="a0c98-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="a0c98-106">Examples</span></span>
<span data-ttu-id="a0c98-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a0c98-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="a0c98-108">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="a0c98-108">Example 1</span></span>

<span data-ttu-id="a0c98-109">Nell'esempio seguente i bit del connettore cloud e il file msi vengono scaricati in modo sincrono dal sito di download pubblico di Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="a0c98-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="a0c98-110">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="a0c98-110">Example 2</span></span>

<span data-ttu-id="a0c98-111">Nell'esempio seguente i bit del connettore cloud e il file msi vengono scaricati in modo sincrono da un sito di download privato:</span><span class="sxs-lookup"><span data-stu-id="a0c98-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="a0c98-112">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="a0c98-112">Example 3</span></span>

<span data-ttu-id="a0c98-113">Nel terzo esempio i bit del connettore cloud e il file msi vengono scaricati in modo sincrono da un sito di download privato.</span><span class="sxs-lookup"><span data-stu-id="a0c98-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="a0c98-114">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="a0c98-114">Detailed Description</span></span>
<span data-ttu-id="a0c98-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a0c98-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="a0c98-116">Se nel sito di download è disponibile una nuova versione, Start-CcDownload scarica e installa il file msi dal sito di download e quindi scarica i bit del connettore cloud in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="a0c98-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="a0c98-117">Se non esiste una nuova versione del file msi, Start-CcDownload solo i bit di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a0c98-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="a0c98-118">Se i bit del connettore cloud sono già scaricati, Start-CcDownload non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="a0c98-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a0c98-119">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0c98-119">Parameters</span></span>
<span data-ttu-id="a0c98-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a0c98-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="a0c98-121">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="a0c98-121">**Parameter**</span></span>|<span data-ttu-id="a0c98-122">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="a0c98-122">**Required**</span></span>|<span data-ttu-id="a0c98-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a0c98-123">**Type**</span></span>|<span data-ttu-id="a0c98-124">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a0c98-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a0c98-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="a0c98-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="a0c98-126">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="a0c98-126">Optional</span></span> <br/> |<span data-ttu-id="a0c98-127">System.String</span><span class="sxs-lookup"><span data-stu-id="a0c98-127">System.String</span></span>  <br/> | <span data-ttu-id="a0c98-128">URL completo di una versione specifica di Cloud Connector nel sito di download privato.</span><span class="sxs-lookup"><span data-stu-id="a0c98-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="a0c98-129">Utilizzare questo parametro con cautela: assicurarsi di essere a conoscenza della versione di Cloud Connector che si sta scaricando.</span><span class="sxs-lookup"><span data-stu-id="a0c98-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="a0c98-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="a0c98-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="a0c98-131">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="a0c98-131">Optional</span></span>  <br/> |<span data-ttu-id="a0c98-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a0c98-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a0c98-133">Ignorare il passaggio per scaricare e installare MSI dal sito di download, scaricare solo i bit del connettore cloud.</span><span class="sxs-lookup"><span data-stu-id="a0c98-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a0c98-134">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="a0c98-134">Input Types</span></span>
<span data-ttu-id="a0c98-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a0c98-135"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="a0c98-136">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="a0c98-136">None.</span></span> <span data-ttu-id="a0c98-137">Il cmdlet Start-CcDownload non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="a0c98-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a0c98-138">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="a0c98-138">Return Types</span></span>
<span data-ttu-id="a0c98-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a0c98-139"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a0c98-140">None</span><span class="sxs-lookup"><span data-stu-id="a0c98-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a0c98-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0c98-141">See also</span></span>
<span data-ttu-id="a0c98-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a0c98-142"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a0c98-143">Nessuno</span><span class="sxs-lookup"><span data-stu-id="a0c98-143">None</span></span>
  

