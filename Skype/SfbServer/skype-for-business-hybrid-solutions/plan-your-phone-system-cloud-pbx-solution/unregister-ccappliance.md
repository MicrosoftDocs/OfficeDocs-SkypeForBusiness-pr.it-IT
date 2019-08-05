---
title: Annullamento della registrazione-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Il cmdlet Unregister-CcAppliance Annulla la registrazione dell'appliance di Skype for Business Cloud Connector corrente da un sito PSTN nella configurazione del tenant online.
ms.openlocfilehash: fafe374371cd01b2ec7c67ade89dd2a905e16d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190586"
---
# <a name="unregister-ccappliance"></a>Annullamento della registrazione-CcAppliance
 
Il cmdlet Unregister-CcAppliance Annulla la registrazione dell'appliance di Skype for Business Cloud Connector corrente da un sito PSTN nella configurazione del tenant online.
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente annulla la registrazione di un appliance corrente dalla configurazione del tenant online:
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente viene controllata la configurazione per l'annullamento della registrazione localmente senza connettersi alla configurazione del tenant online:
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Esempio 3

L'esempio seguente annulla la registrazione dell'appliance corrente con il nome "Appliance1" nel sito PSTN "Microsoft1":
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

In modo analogo al cmdlet Register-CcAppliance, SiteName combinato con il nome di dominio completo esterno del server perimetrale nel file CloudConnector. ini è considerato un'identità del sito PSTN. Analogamente, Appliancename combinato con il nome di dominio completo di Mediation Server nel file CloudConnector. ini viene considerato un'identità Appliance.
  
Dopo l'annullamento della registrazione dell'appliance, riavviare il servizio di gestione di Cloud Connector e accedere come account NetworkService.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |Facoltativo  <br/> |System.String  <br/> |Nome del sito PSTN in cui è registrato l'accessorio. Il valore predefinito è il valore SiteName nel file CloudConnector. ini.  <br/> |
|Appliancename  <br/> |Facoltativo  <br/> |System.String  <br/> |Nome dell'appliance corrente. Il valore predefinito è il nome del computer del server host.  <br/> |
|Locale  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Verificare la configurazione per la registrazione localmente senza connettersi a una configurazione del tenant online.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Unregister-CcAppliance non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Registro-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Disinstallare-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

