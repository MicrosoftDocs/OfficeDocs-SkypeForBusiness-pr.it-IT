---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Esporta la configurazione di Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition.
ms.openlocfilehash: cd0745081e3f069aaf58c9ffdbf24494bfb3ece1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801466"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="9c55d-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c55d-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="9c55d-104">Esporta la configurazione di Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="9c55d-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="9c55d-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="9c55d-105">Examples</span></span>
<span data-ttu-id="9c55d-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c55d-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="9c55d-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="9c55d-107">Example 1</span></span>

<span data-ttu-id="9c55d-108">Nell'esempio seguente il parametro Path viene impostato come percorso completo del file e le configurazioni vengono esportate in tale file.</span><span class="sxs-lookup"><span data-stu-id="9c55d-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="9c55d-109">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="9c55d-109">Detailed Description</span></span>
<span data-ttu-id="9c55d-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c55d-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="9c55d-111">Il cmdlet Export-CcConfiguration consente di salvare la configurazione di Cloud Connector in un file in un percorso selezionato.</span><span class="sxs-lookup"><span data-stu-id="9c55d-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="9c55d-112">Questo comando è stato introdotto in Cloud Connector Edition versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="9c55d-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="9c55d-113">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c55d-113">Parameters</span></span>
<span data-ttu-id="9c55d-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c55d-114"><a name="Examples"> </a></span></span>

|<span data-ttu-id="9c55d-115">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="9c55d-115">**Parameter**</span></span>|<span data-ttu-id="9c55d-116">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="9c55d-116">**Required**</span></span>|<span data-ttu-id="9c55d-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9c55d-117">**Type**</span></span>|<span data-ttu-id="9c55d-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9c55d-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9c55d-119">Percorso</span><span class="sxs-lookup"><span data-stu-id="9c55d-119">Path</span></span>  <br/> |<span data-ttu-id="9c55d-120">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="9c55d-120">Required</span></span>  <br/> |<span data-ttu-id="9c55d-121">System.String</span><span class="sxs-lookup"><span data-stu-id="9c55d-121">System.String</span></span>  <br/> |<span data-ttu-id="9c55d-122">Percorso completo del file in cui verranno archiviate le configurazioni di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9c55d-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9c55d-123">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="9c55d-123">Input Types</span></span>
<span data-ttu-id="9c55d-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c55d-124"><a name="Examples"> </a></span></span>

<span data-ttu-id="9c55d-125">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="9c55d-125">None.</span></span> <span data-ttu-id="9c55d-126">Il cmdlet Export-CcConfiguration non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="9c55d-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9c55d-127">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="9c55d-127">Return Types</span></span>
<span data-ttu-id="9c55d-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c55d-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="9c55d-129">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="9c55d-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9c55d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c55d-130">See also</span></span>
<span data-ttu-id="9c55d-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c55d-131"><a name="Examples"> </a></span></span>

<span data-ttu-id="9c55d-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c55d-132">Import-CcConfiguration</span></span>
  

