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
ms.openlocfilehash: da9135f669cb5b8cbe127295b20d82fd1632a3d3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003086"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
Il cmdlet Publish-CcAppliance ottiene le informazioni di disponibilità elevate dalla configurazione del tenant online e le pubblica nell'appliance Skype for Business Cloud Connector Edition nel server host. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente consente di ottenere informazioni di disponibilità elevate dalla configurazione del tenant online e di pubblicarlo nell'appliance Cloud Connector nel server host:
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Le informazioni di disponibilità elevata contengono gli FQDN di Mediation Server e gli indirizzi IP del sito PSTN. I nuovi record DNS vengono aggiunti agli indirizzi IP di AD server per Mediation Server. I nuovi elementi della topologia vengono aggiornati all'Central Management store per gli FQDN di Mediation Server e gli indirizzi IP. 
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Publish-CcAppliance non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

