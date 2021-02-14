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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Il cmdlet Publish-CcAppliance ottiene informazioni sulla disponibilità elevata dalla configurazione del tenant online e le pubblica nell'appliance Skype for Business Cloud Connector Edition nel server host.
ms.openlocfilehash: 159247614733261cac4b3381e35d8dd297cf9a23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824312"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
Il cmdlet Publish-CcAppliance ottiene informazioni sulla disponibilità elevata dalla configurazione del tenant online e le pubblica nell'appliance Skype for Business Cloud Connector Edition nel server host. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Parametri

None
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente vengono recuperate informazioni sulla disponibilità elevata dalla configurazione del tenant online e vengono pubblicate nell'appliance Cloud Connector nel server host:
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Le informazioni sulla disponibilità elevata contengono gli FQDN e gli indirizzi IP di Mediation Server del sito PSTN. I nuovi record A DNS vengono aggiunti all'AD Server per gli indirizzi IP di Mediation Server. I nuovi elementi della topologia vengono aggiornati nell'archivio di gestione centrale per gli FQDN e gli indirizzi IP di Mediation Server. 
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Publish-CcAppliance non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

