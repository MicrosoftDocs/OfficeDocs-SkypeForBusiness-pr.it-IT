---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Il cmdlet Get-CcSiteDirectory Mostra la directory corrente in cui sono archiviati i file di configurazione a livello di sito. La cartella contiene i file di installazione VHD di base e Skype for Business Cloud Connector Edition. Questa cartella deve essere condivisa con tutti gli altri dispositivi di un sito del connettore Cloud.
ms.openlocfilehash: e0b8a793f0210535a726b0bed19f240bf8b30dd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190775"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="99702-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="99702-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="99702-106">Il cmdlet Get-CcSiteDirectory Mostra la directory corrente in cui sono archiviati i file di configurazione a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="99702-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="99702-107">La cartella contiene i file di installazione VHD di base e Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="99702-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="99702-108">Questa cartella deve essere condivisa con tutti gli altri dispositivi di un sito del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="99702-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="99702-109">Questo cmdlet si applica a Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="99702-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="99702-110">Parametri</span><span class="sxs-lookup"><span data-stu-id="99702-110">Parameters</span></span>

<span data-ttu-id="99702-111">Nessuno</span><span class="sxs-lookup"><span data-stu-id="99702-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="99702-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="99702-112">Examples</span></span>
<span data-ttu-id="99702-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="99702-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="99702-114">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="99702-114">Example 1</span></span>

<span data-ttu-id="99702-115">L'esempio seguente mostra la cartella corrente in cui sono archiviati i file di configurazione e le macchine virtuali dei componenti del connettore Cloud:</span><span class="sxs-lookup"><span data-stu-id="99702-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="99702-116">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="99702-116">Detailed Description</span></span>
<span data-ttu-id="99702-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="99702-117"></span></span>

<span data-ttu-id="99702-118">Per consentire l'affinità dei gateway e l'elevata disponibilità, i dispositivi cloud Connector possono essere combinati nei siti.</span><span class="sxs-lookup"><span data-stu-id="99702-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="99702-119">Gli utenti vengono assegnati a siti anziché a dispositivi cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="99702-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="99702-120">Ogni sito include una cartella condivisa in cui sono archiviati i file di installazione del VHD di base e del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="99702-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="99702-121">Gli elettrodomestici usano questa cartella durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="99702-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="99702-122">La cartella predefinita è C:\Users\%UserProfile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="99702-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="99702-123">Puoi modificare il percorso usando il cmdlet Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="99702-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="99702-124">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="99702-124">Input Types</span></span>
<span data-ttu-id="99702-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="99702-125"></span></span>

<span data-ttu-id="99702-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="99702-126">None.</span></span> <span data-ttu-id="99702-127">Il cmdlet Get-CcSiteDirectory non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="99702-127">The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="99702-128">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="99702-128">Return Types</span></span>
<span data-ttu-id="99702-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="99702-129"></span></span>

<span data-ttu-id="99702-130">Questo comando restituisce un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="99702-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99702-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99702-131">See also</span></span>
<span data-ttu-id="99702-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="99702-132"></span></span>

[<span data-ttu-id="99702-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="99702-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

