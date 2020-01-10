---
title: Unregister-CcAppliance
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
ms.openlocfilehash: 2bd8f3a3ef4ac2b29ab9e7d766836d7a3555c0f4
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003136"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
Il cmdlet Unregister-CcAppliance Annulla la registrazione dell'appliance di Skype for Business Cloud Connector corrente da un sito PSTN nella configurazione del tenant online.
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente annulla la registrazione di un appliance corrente dalla configurazione del tenant online:
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente viene controllata la configurazione per l'annullamento della registrazione localmente senza connettersi alla configurazione del tenant online:
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Esempio 3

L'esempio seguente annulla la registrazione dell'appliance corrente con il nome "Appliance1" nel sito PSTN "Microsoft1":
  
```powershell
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

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

