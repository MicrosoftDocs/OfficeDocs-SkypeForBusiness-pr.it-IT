---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Il cmdlet Set-CcSiteDirectory imposta la directory in cui verranno archiviati i file di configurazione a livello di sito per Skype for Business Cloud Connector Edition. La cartella conterrà i file di configurazione del disco rigido virtuale e del connettore Cloud di base.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824190"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="30b89-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="30b89-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="30b89-105">Il cmdlet Set-CcSiteDirectory imposta la directory in cui verranno archiviati i file di configurazione a livello di sito per Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="30b89-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="30b89-106">La cartella conterrà i file di configurazione del disco rigido virtuale e del connettore Cloud di base.</span><span class="sxs-lookup"><span data-stu-id="30b89-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="30b89-107">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="30b89-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="30b89-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="30b89-108">Examples</span></span>
<span data-ttu-id="30b89-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="30b89-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="30b89-110">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="30b89-110">Example 1</span></span>

<span data-ttu-id="30b89-111">L'esempio seguente imposta la directory radice del sito \\su SiteShare\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="30b89-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="30b89-112">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="30b89-112">Detailed Description</span></span>
<span data-ttu-id="30b89-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="30b89-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="30b89-114">Per consentire l'affinità dei gateway e l'elevata disponibilità, i dispositivi cloud Connector possono essere combinati nei siti.</span><span class="sxs-lookup"><span data-stu-id="30b89-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="30b89-115">Gli utenti vengono assegnati a siti anziché a dispositivi cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="30b89-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="30b89-116">Ogni sito include una cartella condivisa in cui sono archiviati i file di installazione del VHD di base e del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="30b89-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="30b89-117">Gli elettrodomestici usano questa cartella durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="30b89-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="30b89-118">Questa cartella deve essere condivisa con tutti gli altri dispositivi in un sito del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="30b89-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="30b89-119">La cartella predefinita è C:\Users\%UserProfile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="30b89-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="30b89-120">Il percorso può essere visualizzato usando il cmdlet Get-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="30b89-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="30b89-121">Parametri</span><span class="sxs-lookup"><span data-stu-id="30b89-121">Parameters</span></span>
<span data-ttu-id="30b89-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="30b89-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="30b89-123">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="30b89-123">**Parameter**</span></span>|<span data-ttu-id="30b89-124">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="30b89-124">**Required**</span></span>|<span data-ttu-id="30b89-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="30b89-125">**Type**</span></span>|<span data-ttu-id="30b89-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="30b89-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="30b89-127">Percorso</span><span class="sxs-lookup"><span data-stu-id="30b89-127">Path</span></span> <br/> | <span data-ttu-id="30b89-128">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="30b89-128">Required</span></span> <br/> | <span data-ttu-id="30b89-129">System.String</span><span class="sxs-lookup"><span data-stu-id="30b89-129">System.String</span></span> <br/> |<span data-ttu-id="30b89-130">Fornisce il percorso della cartella in cui verranno archiviati i file del sito del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="30b89-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="30b89-131">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="30b89-131">Input Types</span></span>
<span data-ttu-id="30b89-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="30b89-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="30b89-133">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="30b89-133">None.</span></span> <span data-ttu-id="30b89-134">Il cmdlet Set-CcSiteDirectory non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="30b89-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="30b89-135">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="30b89-135">Return Types</span></span>
<span data-ttu-id="30b89-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="30b89-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="30b89-137">Nessuno</span><span class="sxs-lookup"><span data-stu-id="30b89-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="30b89-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30b89-138">See also</span></span>
<span data-ttu-id="30b89-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="30b89-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="30b89-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="30b89-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

