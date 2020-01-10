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
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Il cmdlet Uninstall-CcAppliance Disinstalla l'uso di Skype for Business Cloud Connector Edition dal server host.
ms.openlocfilehash: f37c3092103832c9efd3b24d2efbedf00e8f54ac
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003146"
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
  

