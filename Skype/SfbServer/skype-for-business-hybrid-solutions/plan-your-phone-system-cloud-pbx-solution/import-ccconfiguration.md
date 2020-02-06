---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa la configurazione di Skype for Business Cloud Connector Edition da un file locale al server host Cloud Connector.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799856"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="90a2d-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="90a2d-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="90a2d-104">Importa la configurazione di Skype for Business Cloud Connector Edition da un file locale al server host Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="90a2d-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="90a2d-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="90a2d-105">Examples</span></span>
<span data-ttu-id="90a2d-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="90a2d-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="90a2d-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="90a2d-107">Example 1</span></span>

<span data-ttu-id="90a2d-108">L'esempio seguente copia il CloudConnector. ini dalla directory appliance dell'istanza del connettore Cloud alla directory%SystemDrive%\ProgramData\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="90a2d-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="90a2d-109">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="90a2d-109">Detailed Description</span></span>
<span data-ttu-id="90a2d-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="90a2d-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="90a2d-111">Questo cmdlet copia il CloudConnector. ini dalla directory appliance dell'appliance del connettore Cloud alla directory%SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="90a2d-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="90a2d-112">La directory Appliance viene specificata usando il cmdlet Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="90a2d-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="90a2d-113">Il cmdlet sovrascriverà qualsiasi file esistente in%SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="90a2d-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="90a2d-114">Questo comando si applica a Cloud Connector Edition versione 2.0.1 e successive.</span><span class="sxs-lookup"><span data-stu-id="90a2d-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="90a2d-115">Parametri</span><span class="sxs-lookup"><span data-stu-id="90a2d-115">Parameters</span></span>
<span data-ttu-id="90a2d-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="90a2d-116"><a name="Examples"> </a></span></span>

|<span data-ttu-id="90a2d-117">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="90a2d-117">**Parameter**</span></span>|<span data-ttu-id="90a2d-118">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="90a2d-118">**Required**</span></span>|<span data-ttu-id="90a2d-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="90a2d-119">**Type**</span></span>|<span data-ttu-id="90a2d-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="90a2d-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="90a2d-121">Force</span><span class="sxs-lookup"><span data-stu-id="90a2d-121">Force</span></span>  <br/> |<span data-ttu-id="90a2d-122">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="90a2d-122">Optional</span></span>  <br/> |<span data-ttu-id="90a2d-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="90a2d-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="90a2d-124">Sovrascrivere il file esistente in%SystemDrive%\ProgramData\CloudConnector senza notifica.</span><span class="sxs-lookup"><span data-stu-id="90a2d-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="90a2d-125">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="90a2d-125">Input Types</span></span>
<span data-ttu-id="90a2d-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="90a2d-126"><a name="Examples"> </a></span></span>

<span data-ttu-id="90a2d-127">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="90a2d-127">None.</span></span> <span data-ttu-id="90a2d-128">Il cmdlet Import-CcConfiguration non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="90a2d-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="90a2d-129">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="90a2d-129">Return Types</span></span>
<span data-ttu-id="90a2d-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="90a2d-130"><a name="Examples"> </a></span></span>

<span data-ttu-id="90a2d-131">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="90a2d-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="90a2d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90a2d-132">See also</span></span>
<span data-ttu-id="90a2d-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="90a2d-133"><a name="Examples"> </a></span></span>

<span data-ttu-id="90a2d-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="90a2d-134">Export-CcConfiguration</span></span>
  

