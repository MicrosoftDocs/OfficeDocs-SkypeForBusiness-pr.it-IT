---
title: Export-CcConfigurationSampleFile
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
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Il cmdlet Export-CcConfigurationSampleFile esporta un file di configurazione di esempio di Skype for Business Cloud Connector Edition (ini) nella directory appliance di un'applicazione Cloud Connector. È possibile modificare e rinominare il file da utilizzare per la distribuzione.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801006"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="3af45-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="3af45-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="3af45-105">Il cmdlet Export-CcConfigurationSampleFile esporta un file di configurazione di esempio di Skype for Business Cloud Connector Edition (ini) nella directory appliance di un'applicazione Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="3af45-105">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance.</span></span> <span data-ttu-id="3af45-106">È possibile modificare e rinominare il file da utilizzare per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3af45-106">You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="3af45-107">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="3af45-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="3af45-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="3af45-108">Parameters</span></span>

<span data-ttu-id="3af45-109">None</span><span class="sxs-lookup"><span data-stu-id="3af45-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="3af45-110">Esempi</span><span class="sxs-lookup"><span data-stu-id="3af45-110">Examples</span></span>
<span data-ttu-id="3af45-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3af45-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="3af45-112">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="3af45-112">Example 1</span></span>

<span data-ttu-id="3af45-113">Nell'esempio seguente viene scaricato un file di configurazione di esempio dal sito Microsoft e scritto nella directory appliance dell'appliance Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="3af45-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="3af45-114">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="3af45-114">Detailed Description</span></span>
<span data-ttu-id="3af45-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3af45-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="3af45-116">La versione corrente di Cloud Connector richiede di fornire diversi parametri nel file ini; ad esempio, parametri come gli indirizzi IP delle macchine virtuali per i componenti del connettore cloud, i nomi dei componenti, i parametri del gateway e così via.</span><span class="sxs-lookup"><span data-stu-id="3af45-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="3af45-117">Questo cmdlet, quando viene eseguito nel computer host di Cloud Connector, scarica un file ini di esempio con esempi di configurazione dal sito Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3af45-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="3af45-118">Il cmdlet scrive il file nella directory appliance dell'applicazione Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="3af45-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="3af45-119">La directory dell'appliance viene specificata utilizzando il cmdlet Set-CcApplianceDirectory locale.</span><span class="sxs-lookup"><span data-stu-id="3af45-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="3af45-120">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="3af45-120">Input Types</span></span>
<span data-ttu-id="3af45-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3af45-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="3af45-122">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="3af45-122">None.</span></span> <span data-ttu-id="3af45-123">Il cmdlet Export-CcConfigurationSampleFile non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="3af45-123">The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="3af45-124">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="3af45-124">Return Types</span></span>
<span data-ttu-id="3af45-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3af45-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="3af45-126">None</span><span class="sxs-lookup"><span data-stu-id="3af45-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3af45-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3af45-127">See also</span></span>
<span data-ttu-id="3af45-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3af45-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="3af45-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="3af45-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

