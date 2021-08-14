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
description: Il cmdlet Publish-CcAppliance ottiene informazioni sulla disponibilità elevata dalla configurazione del tenant online e le pubblica nel Skype for Business Cloud Connector Edition appliance nel server host.
ms.openlocfilehash: 83b0a7e3806a271a358085bb0cca2a2ef6a518e67e124f0be97c1ff4616e3dcc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326182"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
Il cmdlet Publish-CcAppliance ottiene informazioni sulla disponibilità elevata dalla configurazione del tenant online e le pubblica nel Skype for Business Cloud Connector Edition appliance nel server host. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente ottiene informazioni sulla disponibilità elevata dalla configurazione tenant online e le pubblica nell'appliance Cloud Connector nel server host:
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Le informazioni sulla disponibilità elevata contengono i nomi fqdn e gli indirizzi IP di Mediation Server del sito PSTN. I nuovi record A DNS vengono aggiunti all'AD Server per gli indirizzi IP di Mediation Server. I nuovi elementi della topologia vengono aggiornati nell'archivio di gestione centrale per gli FQDN e gli indirizzi IP di Mediation Server. 
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Publish-CcAppliance non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

