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
description: Il cmdlet Unregister-CcAppliance annulla la registrazione dell'applicazione Skype for Business Cloud Connector Edition corrente da un sito PSTN nella configurazione tenant online.
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824130"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
Il cmdlet Unregister-CcAppliance annulla la registrazione dell'applicazione Skype for Business Cloud Connector Edition corrente da un sito PSTN nella configurazione tenant online.
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene annullata la registrazione di un'applicazione corrente dalla configurazione tenant online:
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente viene verificata la presenza di un'annullamento della registrazione in locale senza connettersi alla configurazione tenant online:
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Esempio 3

Nell'esempio seguente viene annullata la registrazione dell'applicazione corrente con nome "Appliance1" nel sito PSTN "Site1":
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Analogamente al cmdlet Register-CcAppliance, SiteName combinato con l'FQDN esterno del server perimetrale nel file CloudConnector.ini viene considerato un'identità del sito PSTN. Analogamente, ApplianceName combinato con l'FQDN di Mediation Server nel file CloudConnector.ini viene considerato un'identità del dispositivo.
  
Dopo l'annullamento della registrazione dell'applicazione, riavviare il servizio di gestione di Cloud Connector ed eseguire l'accesso con l'account NetworkService.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |Facoltativo  <br/> |System.String  <br/> |Nome del sito PSTN in cui è registrato il dispositivo. Il valore predefinito è SiteName in CloudConnector.ini file.  <br/> |
|ApplianceName  <br/> |Facoltativo  <br/> |System.String  <br/> |Nome dell'applicazione corrente. Il valore predefinito è il nome computer del server host.  <br/> |
|Locale  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Controllare la configurazione per la registrazione in locale senza connettersi a una configurazione tenant online.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Unregister-CcAppliance non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

