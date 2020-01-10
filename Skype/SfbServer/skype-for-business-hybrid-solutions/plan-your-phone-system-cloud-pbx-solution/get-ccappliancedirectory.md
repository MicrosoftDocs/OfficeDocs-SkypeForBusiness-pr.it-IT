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
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Il cmdlet Get-CcApplianceDirectory recupera la directory di lavoro nel server host di Skype for Business Cloud Connector Edition. Tutti i file di distribuzione sono archiviati in questa directory.
ms.openlocfilehash: 77064676062411c3417e554e422b0ffaae461191
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003406"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="7b656-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="7b656-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="7b656-105">Il cmdlet Get-CcApplianceDirectory recupera la directory di lavoro nel server host di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="7b656-105">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="7b656-106">Tutti i file di distribuzione sono archiviati in questa directory.</span><span class="sxs-lookup"><span data-stu-id="7b656-106">All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="7b656-107">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="7b656-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="7b656-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b656-108">Parameters</span></span>

<span data-ttu-id="7b656-109">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7b656-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="7b656-110">Esempi</span><span class="sxs-lookup"><span data-stu-id="7b656-110">Examples</span></span>
<span data-ttu-id="7b656-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7b656-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="7b656-112">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="7b656-112">Example 1</span></span>

<span data-ttu-id="7b656-113">L'esempio seguente mostra la cartella corrente in cui sono archiviati i file della configurazione e della macchina virtuale dei componenti del connettore Cloud:</span><span class="sxs-lookup"><span data-stu-id="7b656-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="7b656-114">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="7b656-114">Detailed Description</span></span>
<span data-ttu-id="7b656-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7b656-115"></span></span>

<span data-ttu-id="7b656-116">Il cmdlet Get-CcApplianceDirectory Mostra la posizione in cui vengono archiviati tutti i file di configurazione e la macchina virtuale, i registri e i certificati esterni per l'accessorio Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7b656-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="7b656-117">Ogni accessorio Cloud Connector include quattro componenti: Mediation Server, Central Management store, Edge Server e un controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="7b656-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="7b656-118">La cartella predefinita è C:\Users\%UserProfile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="7b656-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="7b656-119">Puoi modificare questa cartella usando il cmdlet Set-CCApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="7b656-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="7b656-120">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="7b656-120">Input Types</span></span>
<span data-ttu-id="7b656-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7b656-121"></span></span>

<span data-ttu-id="7b656-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7b656-122">None.</span></span> <span data-ttu-id="7b656-123">Il cmdlet Get-CCApplianceDirectory non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="7b656-123">The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7b656-124">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="7b656-124">Return Types</span></span>
<span data-ttu-id="7b656-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7b656-125"></span></span>

<span data-ttu-id="7b656-126">Il comando restituisce un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="7b656-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7b656-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b656-127">See also</span></span>
<span data-ttu-id="7b656-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7b656-128"></span></span>

[<span data-ttu-id="7b656-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="7b656-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

