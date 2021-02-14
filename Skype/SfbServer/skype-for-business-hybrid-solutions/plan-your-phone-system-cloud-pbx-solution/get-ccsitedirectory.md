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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Il cmdlet Get-CcSiteDirectory mostra la directory corrente in cui sono archiviati i file di configurazione a livello di sito. La cartella contiene il disco rigido virtuale di base e i file di installazione di Skype for Business Cloud Connector Edition. Questa cartella deve essere condivisa con tutte le altre appliance di un sito Cloud Connector.
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799866"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="051c0-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="051c0-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="051c0-106">Il cmdlet Get-CcSiteDirectory mostra la directory corrente in cui sono archiviati i file di configurazione a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="051c0-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="051c0-107">La cartella contiene il disco rigido virtuale di base e i file di installazione di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="051c0-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="051c0-108">Questa cartella deve essere condivisa con tutte le altre appliance di un sito Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="051c0-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="051c0-109">Questo cmdlet si applica a Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="051c0-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="051c0-110">Parametri</span><span class="sxs-lookup"><span data-stu-id="051c0-110">Parameters</span></span>

<span data-ttu-id="051c0-111">None</span><span class="sxs-lookup"><span data-stu-id="051c0-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="051c0-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="051c0-112">Examples</span></span>
<span data-ttu-id="051c0-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="051c0-113"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="051c0-114">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="051c0-114">Example 1</span></span>

<span data-ttu-id="051c0-115">Nell'esempio seguente viene mostrata la cartella corrente in cui sono archiviati i file di configurazione e delle macchine virtuali dei componenti di Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="051c0-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="051c0-116">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="051c0-116">Detailed Description</span></span>
<span data-ttu-id="051c0-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="051c0-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="051c0-118">Per fornire affinità gateway e disponibilità elevata, le appliance Cloud Connector possono essere combinate nei siti.</span><span class="sxs-lookup"><span data-stu-id="051c0-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="051c0-119">Gli utenti vengono assegnati ai siti anziché alle appliance cloud connector.</span><span class="sxs-lookup"><span data-stu-id="051c0-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="051c0-120">Ogni sito dispone di una cartella condivisa in cui sono archiviati i file di installazione del disco rigido virtuale e del connettore cloud di base.</span><span class="sxs-lookup"><span data-stu-id="051c0-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="051c0-121">Gli appliance usano questa cartella durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="051c0-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="051c0-122">La cartella predefinita è C:\Users \% userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="051c0-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="051c0-123">È possibile modificare il percorso utilizzando il cmdlet Set-CcSiteDirectory seguente.</span><span class="sxs-lookup"><span data-stu-id="051c0-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="051c0-124">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="051c0-124">Input Types</span></span>
<span data-ttu-id="051c0-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="051c0-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="051c0-126">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="051c0-126">None.</span></span> <span data-ttu-id="051c0-127">Il cmdlet Get-CcSiteDirectory non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="051c0-127">The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="051c0-128">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="051c0-128">Return Types</span></span>
<span data-ttu-id="051c0-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="051c0-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="051c0-130">Questo comando restituisce un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="051c0-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="051c0-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="051c0-131">See also</span></span>
<span data-ttu-id="051c0-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="051c0-132"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="051c0-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="051c0-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

