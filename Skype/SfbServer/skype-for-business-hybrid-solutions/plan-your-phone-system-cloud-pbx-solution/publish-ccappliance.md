---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Il cmdlet Publish-CcAppliance ottiene le informazioni di disponibilità elevate dalla configurazione del tenant online e le pubblica nell'appliance Skype for Business Cloud Connector Edition nel server host.
ms.openlocfilehash: 2fd17e2afdceabc8fbfb44a808b7e6c9ce6bd894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190706"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="8ac52-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8ac52-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="8ac52-104">Il cmdlet Publish-CcAppliance ottiene le informazioni di disponibilità elevate dalla configurazione del tenant online e le pubblica nell'appliance Skype for Business Cloud Connector Edition nel server host.</span><span class="sxs-lookup"><span data-stu-id="8ac52-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="8ac52-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ac52-105">Parameters</span></span>

<span data-ttu-id="8ac52-106">Nessuno</span><span class="sxs-lookup"><span data-stu-id="8ac52-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="8ac52-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="8ac52-107">Examples</span></span>
<span data-ttu-id="8ac52-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8ac52-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="8ac52-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="8ac52-109">Example 1</span></span>

<span data-ttu-id="8ac52-110">L'esempio seguente consente di ottenere informazioni di disponibilità elevate dalla configurazione del tenant online e di pubblicarlo nell'appliance Cloud Connector nel server host:</span><span class="sxs-lookup"><span data-stu-id="8ac52-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="8ac52-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="8ac52-111">Detailed Description</span></span>
<span data-ttu-id="8ac52-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8ac52-112"></span></span>

<span data-ttu-id="8ac52-113">Le informazioni di disponibilità elevata contengono gli FQDN di Mediation Server e gli indirizzi IP del sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="8ac52-113">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site.</span></span> <span data-ttu-id="8ac52-114">I nuovi record DNS vengono aggiunti agli indirizzi IP di AD server per Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="8ac52-114">New DNS A records are added to the AD Server for Mediation Server IP addresses.</span></span> <span data-ttu-id="8ac52-115">I nuovi elementi della topologia vengono aggiornati all'Central Management store per gli FQDN di Mediation Server e gli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="8ac52-115">New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="8ac52-116">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="8ac52-116">Input Types</span></span>
<span data-ttu-id="8ac52-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8ac52-117"></span></span>

<span data-ttu-id="8ac52-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8ac52-118">None.</span></span> <span data-ttu-id="8ac52-119">Il cmdlet Publish-CcAppliance non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="8ac52-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8ac52-120">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="8ac52-120">Return Types</span></span>
<span data-ttu-id="8ac52-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8ac52-121"></span></span>

<span data-ttu-id="8ac52-122">Nessuno</span><span class="sxs-lookup"><span data-stu-id="8ac52-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8ac52-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ac52-123">See also</span></span>
<span data-ttu-id="8ac52-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8ac52-124"></span></span>

[<span data-ttu-id="8ac52-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8ac52-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="8ac52-126">Disinstallare-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8ac52-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="8ac52-127">Registro-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8ac52-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="8ac52-128">Annullamento della registrazione-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8ac52-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

