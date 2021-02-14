---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Il Register-CcAppliance consente di registrare le informazioni sull'applicazione in un sito PSTN in una configurazione tenant online. Un'applicazione deve essere registrata prima di poter essere distribuita e gestita dal servizio di gestione Skype for Business Cloud Connector Edition.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824302"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
Il Register-CcAppliance consente di registrare le informazioni sull'applicazione in un sito PSTN in una configurazione tenant online. Un'applicazione deve essere registrata prima di poter essere distribuita e gestita dal servizio di gestione Skype for Business Cloud Connector Edition.
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente vengono registrate le informazioni sull'applicazione corrente in una configurazione tenant online:
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente viene verificata la configurazione per la registrazione in locale senza connettersi a una configurazione tenant online:
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>Esempio 3

Nell'esempio seguente viene registrato l'applicazione corrente con il nome "Appliance1" nel sito PSTN "Site1":
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

È necessario specificare il nome e la password dell'account di amministratore tenant. Utilizzare l'account creato per la gestione online di Cloud Connector. 
  
Nella versione 1.4.2 e versioni precedenti, seguire le istruzioni per fornire la password del certificato esterno, la password di amministratore in modalità provvisoria, la password di amministratore del dominio e la password di amministratore della macchina virtuale. 
  
Nella versione 2.0 e successive, seguire le istruzioni per fornire la password del certificato esterno, la password CceService e la password CABackupFile.
  
Al termine della registrazione, riavviare il servizio di gestione cloud Connector e accedere ai servizi come account CceService.
  
SiteName in combinazione con l'FQDN esterno del server perimetrale nel file CloudConnector.ini viene considerato un'identità del sito PSTN. Se per registrare un sito non sono stati utilizzati né siteName né FQDN esterno del server perimetrale, verrà creato un nuovo sito per questo appliance in una configurazione tenant online. Se viene trovata un'identità del sito PSTN, tale identità verrà utilizzata da un sito PSTN e l'applicazione verrà registrata in questo sito PSTN. 
  
Nella situazione seguente, il cmdlet avrà esito negativo e indicherà che Site1 è già registrato: 
  
- SiteName è Site1 e l'FQDN esterno del server perimetrale è edgserver1.contoso.com. 
    
- Un sito PSTN il cui SiteName è Site1 e il nome di dominio completo esterno del server perimetrale è edgserver.contoso.com.
    
- Un sito PSTN il cui SiteName è NewSite e l'FQDN esterno del server perimetrale edgserver1.contoso.com è stato registrato. 
    
ApplianceName in combinazione con l'FQDN di Mediation Server CloudConnector.ini file viene considerato un'identità del dispositivo. Se per registrare un'applicazione non è stato utilizzato né il nome di dominio completo di ApplianceName né il Mediation Server, verrà creato un nuovo appliance nella configurazione tenant online. Se l'applicazione è già registrata, il cmdlet avrà esito negativo.
  
Nella situazione seguente, il cmdlet avrà esito negativo e indicherà che l'applicazione è già registrata: 
  
- ApplianceName è Appliance1 e l'FQDN del Mediation Server ms1.vdomain.com.
    
- Nel sito PSTN corrente, se è stato registrato un dispositivo il cui nome di dominio completo Appliance1 e Mediation Server è ms.vdomain.com o un'applicazione il cui nome è NewAppliance e mediation server FQDN ms1.vdomain.com è stato registrato.
    
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Facoltativo  <br/> |System.String  <br/> |Nome del sito PSTN in cui è registrato il dispositivo. Il valore predefinito è SiteName nel file CloudConnector.ini locale.  <br/> |
|ApplianceName  <br/> |Facoltativo  <br/> |System.String  <br/> |Nome dell'applicazione corrente. Il valore predefinito è il nome computer del server host.  <br/> |
|Locale  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Controllare le configurazioni per la registrazione in locale senza connettersi alla configurazione del tenant online.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Register-CcAppliance non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

