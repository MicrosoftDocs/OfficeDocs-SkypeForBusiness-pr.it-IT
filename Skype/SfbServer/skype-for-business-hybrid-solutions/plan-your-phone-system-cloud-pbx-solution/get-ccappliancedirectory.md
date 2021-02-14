---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Il Get-CcApplianceDirectory cmdlet recupera la directory di lavoro nel server host Skype for Business Cloud Connector Edition. Tutti i file di distribuzione sono archiviati in questa directory.
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800846"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="c2c37-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="c2c37-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="c2c37-105">Il Get-CcApplianceDirectory cmdlet recupera la directory di lavoro nel server host Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c2c37-105">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="c2c37-106">Tutti i file di distribuzione sono archiviati in questa directory.</span><span class="sxs-lookup"><span data-stu-id="c2c37-106">All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="c2c37-107">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="c2c37-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="c2c37-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="c2c37-108">Parameters</span></span>

<span data-ttu-id="c2c37-109">None</span><span class="sxs-lookup"><span data-stu-id="c2c37-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="c2c37-110">Esempi</span><span class="sxs-lookup"><span data-stu-id="c2c37-110">Examples</span></span>
<span data-ttu-id="c2c37-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c37-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c2c37-112">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="c2c37-112">Example 1</span></span>

<span data-ttu-id="c2c37-113">L'esempio seguente mostra la cartella corrente in cui sono archiviati i file di configurazione e della macchina virtuale dei componenti cloud connector:</span><span class="sxs-lookup"><span data-stu-id="c2c37-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="c2c37-114">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="c2c37-114">Detailed Description</span></span>
<span data-ttu-id="c2c37-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c37-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c2c37-116">Il cmdlet Get-CcApplianceDirectory mostra dove vengono archiviati tutti i file, i registri e i certificati esterni della macchina virtuale e di configurazione per l'applicazione Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c2c37-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="c2c37-117">Ogni applicazione Cloud Connector dispone di quattro componenti: Mediation Server, Archivio di gestione centrale, Server perimetrale e controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="c2c37-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="c2c37-118">La cartella predefinita è C:\Users \% userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="c2c37-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="c2c37-119">È possibile modificare questa cartella utilizzando il cmdlet Set-CCApplianceDirectory seguente.</span><span class="sxs-lookup"><span data-stu-id="c2c37-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="c2c37-120">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="c2c37-120">Input Types</span></span>
<span data-ttu-id="c2c37-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c37-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c2c37-122">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="c2c37-122">None.</span></span> <span data-ttu-id="c2c37-123">Il cmdlet Get-CCApplianceDirectory non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="c2c37-123">The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c2c37-124">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="c2c37-124">Return Types</span></span>
<span data-ttu-id="c2c37-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c37-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c2c37-126">Il comando restituisce un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="c2c37-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c2c37-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2c37-127">See also</span></span>
<span data-ttu-id="c2c37-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c37-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="c2c37-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="c2c37-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

