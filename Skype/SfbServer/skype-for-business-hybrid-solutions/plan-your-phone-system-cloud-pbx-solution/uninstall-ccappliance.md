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
description: Il Uninstall-CcAppliance cmdlet disinstalla l'applicazione Skype for Business Cloud Connector Edition in esecuzione dal server host.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824140"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
Il Uninstall-CcAppliance cmdlet disinstalla l'applicazione Skype for Business Cloud Connector Edition in esecuzione dal server host. 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente l'applicazione Cloud Connector viene scaricata e disinstallata dal server host:
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente viene svuotato e disinstallato forzatamente l'applicazione Cloud Connector in esecuzione nel server host anche se il processo di svuotamento non è riuscito:
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Esempio 3

Nell'esempio seguente viene disinstallata una versione di backup di Cloud Connector senza la conferma dell'utente:
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Se si disinstalla la versione corrente in esecuzione di Cloud Connector, i servizi di svuotamento vengono prima eseguiti nel Mediation Server e nel server perimetrale per consentire il completamento delle chiamate simultanee prima di disinstallare le macchine virtuali. Se si disinstalla una versione di backup, lo svuotamento non viene eseguito.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Versione <br/> | Facoltativo <br/> |System.String  <br/> | Versione di Cloud Connector che verrà disinstallata dal server host. Se non specificato, disinstallare la versione in esecuzione corrente. <br/> |
|Force  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Se si disinstalla la versione in esecuzione corrente, tentare di svuotare i server nel Mediation Server e nel server perimetrale prima di disinstallare le macchine virtuali. Se si specifica l'opzione "Force", anche in caso di errore dei servizi di svuotamento, le macchine virtuali verranno disinstallate. Questo parametro viene utilizzato solo per disinstallare la versione in esecuzione corrente.  <br/> |
|Conferma  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Chiedere all'utente di confermare la disinstallazione delle macchine virtuali. Il valore predefinito è VERO.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Uninstall-CcAppliance non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

