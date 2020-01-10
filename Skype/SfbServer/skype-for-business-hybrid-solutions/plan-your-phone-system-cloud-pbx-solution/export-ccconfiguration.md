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
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Esporta la configurazione di Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition.
ms.openlocfilehash: cb3ea5a48c4e8911dc94526f85a517082d057b6e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003436"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="71492-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="71492-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="71492-104">Esporta la configurazione di Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="71492-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="71492-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="71492-105">Examples</span></span>
<span data-ttu-id="71492-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="71492-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="71492-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="71492-107">Example 1</span></span>

<span data-ttu-id="71492-108">L'esempio seguente imposta il parametro Path come percorso di file completo ed Esporta le configurazioni in tale file.</span><span class="sxs-lookup"><span data-stu-id="71492-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="71492-109">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="71492-109">Detailed Description</span></span>
<span data-ttu-id="71492-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="71492-110"></span></span>

<span data-ttu-id="71492-111">Il cmdlet Export-CcConfiguration consente di salvare la configurazione del connettore Cloud in un file in un percorso selezionato.</span><span class="sxs-lookup"><span data-stu-id="71492-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="71492-112">Questo comando è stato introdotto in Cloud Connector Edition versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="71492-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="71492-113">Parametri</span><span class="sxs-lookup"><span data-stu-id="71492-113">Parameters</span></span>
<span data-ttu-id="71492-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="71492-114"></span></span>

|<span data-ttu-id="71492-115">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="71492-115">**Parameter**</span></span>|<span data-ttu-id="71492-116">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="71492-116">**Required**</span></span>|<span data-ttu-id="71492-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="71492-117">**Type**</span></span>|<span data-ttu-id="71492-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="71492-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="71492-119">Percorso</span><span class="sxs-lookup"><span data-stu-id="71492-119">Path</span></span>  <br/> |<span data-ttu-id="71492-120">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="71492-120">Required</span></span>  <br/> |<span data-ttu-id="71492-121">System.String</span><span class="sxs-lookup"><span data-stu-id="71492-121">System.String</span></span>  <br/> |<span data-ttu-id="71492-122">Percorso file completo in cui verranno archiviate le configurazioni del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="71492-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="71492-123">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="71492-123">Input Types</span></span>
<span data-ttu-id="71492-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="71492-124"></span></span>

<span data-ttu-id="71492-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="71492-125">None.</span></span> <span data-ttu-id="71492-126">Il cmdlet Export-CcConfiguration non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="71492-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="71492-127">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="71492-127">Return Types</span></span>
<span data-ttu-id="71492-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="71492-128"></span></span>

<span data-ttu-id="71492-129">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="71492-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="71492-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71492-130">See also</span></span>
<span data-ttu-id="71492-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="71492-131"></span></span>

<span data-ttu-id="71492-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="71492-132">Import-CcConfiguration</span></span>
  

