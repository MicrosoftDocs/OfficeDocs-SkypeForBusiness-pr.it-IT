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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Il cmdlet Unregister-CcAppliance annulla la registrazione dell'appliance Skype for Business Cloud Connector Edition corrente da un sito PSTN nella configurazione tenant online.
ms.openlocfilehash: de872082f6a025a736b871a76d41061c888acb1f401739229ba7ad670a0c19ce
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344545"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
Il cmdlet Unregister-CcAppliance annulla la registrazione dell'appliance Skype for Business Cloud Connector Edition corrente da un sito PSTN nella configurazione tenant online.
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene annullata la registrazione di un'appliance corrente dalla configurazione tenant online:
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente controlla la configurazione per l'annullamento della registrazione in locale senza connettersi alla configurazione tenant online:
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Esempio 3

Nell'esempio seguente viene annullata la registrazione dell'appliance corrente con nome "Appliance1" al sito PSTN "Site1":
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Analogamente al cmdlet Register-CcAppliance, SiteName combinato con l'FQDN esterno del server perimetrale nel file CloudConnector.ini viene considerato un'identità del sito PSTN. Analogamente, ApplianceName combinato con il nome di dominio completo di Mediation Server nel file CloudConnector.ini viene considerato un'identità dell'appliance.
  
Dopo l'annullamento della registrazione dell'appliance, riavviare il servizio di gestione del connettore cloud e accedere come account NetworkService.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |Facoltativo  <br/> |System.String  <br/> |Nome del sito PSTN in cui è registrato il dispositivo. Il valore predefinito è SiteName in CloudConnector.ini file.  <br/> |
|ApplianceName  <br/> |Facoltativo  <br/> |System.String  <br/> |Nome dell'appliance corrente. Il valore predefinito è il nome computer del server host.  <br/> |
|Locale  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Controllare la configurazione per la registrazione in locale senza connettersi a una configurazione tenant online.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Unregister-CcAppliance non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

