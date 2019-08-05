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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Il cmdlet Export-CcConfigurationSampleFile esporta un file di configurazione di esempio in Skype for Business Cloud Connector Edition (INI) nella directory appliance di un appliance di connessione cloud. È possibile modificare e rinominare il file da usare per la distribuzione.
ms.openlocfilehash: 440253bc6b9c4e980a6f7ac4aae0c82ebad05660
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190802"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="b08fe-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="b08fe-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="b08fe-105">Il cmdlet Export-CcConfigurationSampleFile esporta un file di configurazione di esempio in Skype for Business Cloud Connector Edition (INI) nella directory appliance di un appliance di connessione cloud.</span><span class="sxs-lookup"><span data-stu-id="b08fe-105">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance.</span></span> <span data-ttu-id="b08fe-106">È possibile modificare e rinominare il file da usare per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b08fe-106">You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="b08fe-107">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="b08fe-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="b08fe-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="b08fe-108">Parameters</span></span>

<span data-ttu-id="b08fe-109">Nessuno</span><span class="sxs-lookup"><span data-stu-id="b08fe-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="b08fe-110">Esempi</span><span class="sxs-lookup"><span data-stu-id="b08fe-110">Examples</span></span>
<span data-ttu-id="b08fe-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b08fe-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="b08fe-112">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="b08fe-112">Example 1</span></span>

<span data-ttu-id="b08fe-113">L'esempio seguente Scarica un file di configurazione di esempio dal sito Microsoft e lo scrive nella directory appliance dell'accessorio Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="b08fe-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="b08fe-114">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="b08fe-114">Detailed Description</span></span>
<span data-ttu-id="b08fe-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b08fe-115"></span></span>

<span data-ttu-id="b08fe-116">La versione corrente di Cloud Connector richiede di specificare diversi parametri nel file ini; ad esempio, parametri come gli indirizzi IP delle macchine virtuali per i componenti del connettore Cloud, i nomi dei componenti, i parametri del gateway e così via.</span><span class="sxs-lookup"><span data-stu-id="b08fe-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="b08fe-117">Questo cmdlet, quando viene eseguito nel computer host di Cloud Connector, Scarica un file ini sample con esempi di configurazione dal sito Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b08fe-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="b08fe-118">Il cmdlet scrive il file nella directory appliance dell'accessorio Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b08fe-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="b08fe-119">La directory Appliance viene specificata usando il cmdlet Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="b08fe-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b08fe-120">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="b08fe-120">Input Types</span></span>
<span data-ttu-id="b08fe-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b08fe-121"></span></span>

<span data-ttu-id="b08fe-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b08fe-122">None.</span></span> <span data-ttu-id="b08fe-123">Il cmdlet Export-CcConfigurationSampleFile non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="b08fe-123">The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="b08fe-124">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="b08fe-124">Return Types</span></span>
<span data-ttu-id="b08fe-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b08fe-125"></span></span>

<span data-ttu-id="b08fe-126">Nessuno</span><span class="sxs-lookup"><span data-stu-id="b08fe-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b08fe-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b08fe-127">See also</span></span>
<span data-ttu-id="b08fe-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b08fe-128"></span></span>

[<span data-ttu-id="b08fe-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="b08fe-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

