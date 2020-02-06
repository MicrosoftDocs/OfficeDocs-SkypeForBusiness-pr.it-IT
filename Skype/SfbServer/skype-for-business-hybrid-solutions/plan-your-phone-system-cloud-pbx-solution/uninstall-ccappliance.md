---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Il cmdlet Uninstall-CcAppliance Disinstalla l'uso di Skype for Business Cloud Connector Edition dal server host.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824140"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
Il cmdlet Uninstall-CcAppliance Disinstalla l'uso di Skype for Business Cloud Connector Edition dal server host. 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene svuotato e disinstallato l'accessorio Cloud Connector dal server host:
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente Scarica e Disinstalla forzatamente l'appliance di connessione cloud in esecuzione nel server host anche se il processo di svuotamento non è riuscito:
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Esempio 3

Nell'esempio successivo viene disinstallata una versione di backup di Cloud Connector senza la conferma dell'utente:
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Se si disinstalla la versione corrente di Cloud Connector, i servizi di drenaggio vengono eseguiti prima di tutto sul server Mediation e Edge Server per consentire la fine delle chiamate simultanee prima della disinstallazione delle macchine virtuali. Se si disinstalla una versione di backup, lo svuotamento non viene eseguito.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Versione <br/> | Facoltativo <br/> |System.String  <br/> | La versione di Cloud Connector che verrà disinstallata dal server host. Se non specificato, disinstallare la versione corrente in esecuzione. <br/> |
|Force  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Per disinstallare la versione corrente in esecuzione, provare a svuotare i server in Mediation Server e Edge Server prima di disinstallare le macchine virtuali. Se specifichi l'opzione "forza", anche se i servizi di scarico non riescono, le macchine virtuali verranno disinstallate. Questo parametro viene usato solo per disinstallare la versione corrente in esecuzione.  <br/> |
|Confirm  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Richiedi conferma dell'utente per disinstallare le macchine virtuali. Il valore predefinito è TRUE.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Uninstall-CcAppliance non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

