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
description: Il cmdlet Uninstall-CcAppliance consente di disinstallare l'Skype for Business Cloud Connector Edition appliance in esecuzione dal server host.
ms.openlocfilehash: f82459e71ee3c7eea88030a2f265f0076a633a280ee3182920e599402f69a96c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344555"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
Il cmdlet Uninstall-CcAppliance consente di disinstallare l'Skype for Business Cloud Connector Edition appliance in esecuzione dal server host. 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente scarica e disinstalla l'appliance Cloud Connector dal server host:
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente scarica e disinstalla forzatamente l'appliance Cloud Connector in esecuzione nel server host anche se il processo di svuotamento non è riuscito:
  
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
|Conferma  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Chiedere la conferma dell'utente per disinstallare le macchine virtuali. Il valore predefinito è TRUE.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Uninstall-CcAppliance non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

