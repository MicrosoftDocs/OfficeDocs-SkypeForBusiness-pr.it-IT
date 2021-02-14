---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Restituisce la versione dell'applicazione Cloud Connector. Get-CCVersion può essere usato solo nel computer host di Cloud Connector.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799846"
---
# <a name="get-ccversion"></a><span data-ttu-id="b2920-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="b2920-104">Get-CcVersion</span></span>
 
<span data-ttu-id="b2920-105">Restituisce la versione dell'applicazione Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b2920-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="b2920-106">Get-CCVersion può essere usato solo nel computer host di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b2920-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="b2920-107">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="b2920-107">Detailed Description</span></span>

<span data-ttu-id="b2920-108">Restituisce la versione dell'applicazione Cloud Connector in base agli script di PowerShell installati, ai file nella directory appliance e alle macchine virtuali distribuite nel server host.</span><span class="sxs-lookup"><span data-stu-id="b2920-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b2920-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2920-109">Parameters</span></span>

|<span data-ttu-id="b2920-110">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="b2920-110">**Parameter**</span></span>|<span data-ttu-id="b2920-111">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="b2920-111">**Required**</span></span>|<span data-ttu-id="b2920-112">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b2920-112">**Type**</span></span>|<span data-ttu-id="b2920-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b2920-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b2920-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="b2920-114">VersionType</span></span>  <br/> |<span data-ttu-id="b2920-115">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="b2920-115">Optional</span></span>  <br/> |<span data-ttu-id="b2920-116">System.String</span><span class="sxs-lookup"><span data-stu-id="b2920-116">System.String</span></span>  <br/> |<span data-ttu-id="b2920-117">Tipo di versione.</span><span class="sxs-lookup"><span data-stu-id="b2920-117">Type of version.</span></span> <span data-ttu-id="b2920-118">Il valore del parametro può essere RunningScripts, RunningBits, BackupBits o All.</span><span class="sxs-lookup"><span data-stu-id="b2920-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="b2920-119">Il valore predefinito è RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="b2920-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="b2920-120">Esempi</span><span class="sxs-lookup"><span data-stu-id="b2920-120">Examples</span></span>
<span data-ttu-id="b2920-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b2920-121"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="b2920-122">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="b2920-122">Example 1</span></span>

<span data-ttu-id="b2920-123">L'esempio seguente mostra la versione Cloud Connector dello script attualmente in esecuzione nella console di PowerShell aperta:</span><span class="sxs-lookup"><span data-stu-id="b2920-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="b2920-124">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="b2920-124">Example 2</span></span>

<span data-ttu-id="b2920-125">L'esempio seguente mostra la versione Cloud Connector dei file binari attualmente in esecuzione distribuiti alle macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="b2920-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="b2920-126">È possibile visualizzare la versione nei nomi delle macchine virtuali in esecuzione nella console di gestione di Hyper-v:</span><span class="sxs-lookup"><span data-stu-id="b2920-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="b2920-127">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="b2920-127">Input Types</span></span>
<span data-ttu-id="b2920-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b2920-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="b2920-129">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="b2920-129">None.</span></span> <span data-ttu-id="b2920-130">Il cmdlet Get-CcVersion non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="b2920-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b2920-131">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="b2920-131">Return Types</span></span>
<span data-ttu-id="b2920-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b2920-132"><a name="Examples"> </a></span></span>

<span data-ttu-id="b2920-133">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="b2920-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b2920-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2920-134">See also</span></span>
<span data-ttu-id="b2920-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b2920-135"><a name="Examples"> </a></span></span>

<span data-ttu-id="b2920-136">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="b2920-136">None.</span></span>
  

