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
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
Il cmdlet Publish-CcAppliance ottiene le informazioni di disponibilità elevate dalla configurazione del tenant online e le pubblica nell'appliance Skype for Business Cloud Connector Edition nel server host. 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente consente di ottenere informazioni di disponibilità elevate dalla configurazione del tenant online e di pubblicarlo nell'appliance Cloud Connector nel server host:
  
```
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
  
[Disinstallare-CcAppliance](uninstall-ccappliance.md)
  
[Registro-CcAppliance](register-ccappliance.md)
  
[Annullamento della registrazione-CcAppliance](unregister-ccappliance.md)
  

