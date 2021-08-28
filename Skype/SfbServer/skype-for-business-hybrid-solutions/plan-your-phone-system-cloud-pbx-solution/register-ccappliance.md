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
ms.localizationpriority: medium
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Il cmdlet Register-CcAppliance registra le informazioni dell'appliance in un sito PSTN in una configurazione tenant online. Un'appliance deve essere registrata prima di poter essere distribuita e gestita dal Skype for Business Cloud Connector Edition di gestione dei dispositivi.
ms.openlocfilehash: 159e74f91ca26cd0f8bdd214c9cd6ac45b5c1196
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589960"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
Il cmdlet Register-CcAppliance registra le informazioni dell'appliance in un sito PSTN in una configurazione tenant online. Un'appliance deve essere registrata prima di poter essere distribuita e gestita dal Skype for Business Cloud Connector Edition di gestione dei dispositivi.
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente registra le informazioni correnti dell'appliance in una configurazione tenant online:
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente controlla la configurazione per la registrazione in locale senza connettersi a una configurazione tenant online:
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>Esempio 3

Nell'esempio seguente l'appliance corrente viene registrato con il nome "Appliance1" nel sito PSTN "Site1":
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

È necessario specificare il nome e la password dell'account amministratore tenant. Utilizzare l'account creato per la gestione online del connettore cloud. 
  
Nella versione 1.4.2 e versioni precedenti, seguire le istruzioni per fornire la password del certificato esterno, la password di amministratore in modalità provvisoria, la password di amministratore di dominio e la password di amministratore della macchina virtuale. 
  
Nella versione 2.0 e successive, seguire le istruzioni per fornire la password del certificato esterno, la password CceService e la password CABackupFile.
  
Al termine della registrazione, riavviare il servizio di gestione del connettore cloud e accedere ai servizi come account CceService.
  
SiteName combinato con il nome di dominio completo esterno del server perimetrale nel file CloudConnector.ini viene considerato un'identità del sito PSTN. Se per registrare un sito non è stato utilizzato né il nome di dominio completo (FQDN) esterno né il nome di dominio completo del server perimetrale, verrà creato un nuovo sito per questa appliance in una configurazione tenant online. Se viene trovata un'identità del sito PSTN, verrà utilizzata da un sito PSTN e l'appliance verrà registrata nel sito PSTN. 
  
Nella situazione seguente, il cmdlet avrà esito negativo e indicherà che Site1 è già registrato: 
  
- SiteName è Site1 e il nome di dominio completo esterno del server perimetrale è edgserver1.contoso.com. 
    
- Un sito PSTN il cui SiteName è Site1 e fqdn esterno del server perimetrale è edgserver.contoso.com.
    
- Un sito PSTN il cui SiteName è NewSite e il nome di dominio completo esterno del server perimetrale edgserver1.contoso.com è stato registrato. 
    
ApplianceName in combinazione con il nome di dominio completo CloudConnector.ini Mediation Server nel file viene considerato un'identità dell'appliance. Se per registrare un'appliance non è stato utilizzato né il nome di dominio completo di ApplianceName né il nome di dominio completo del Mediation Server, verrà creato un nuovo dispositivo nella configurazione tenant online. Se l'appliance è già registrata, il cmdlet avrà esito negativo.
  
Nella situazione seguente, il cmdlet avrà esito negativo e indicherà che l'appliance è già registrata: 
  
- ApplianceName è Appliance1 e mediation server FQDN è ms1.vdomain.com.
    
- Nel sito PSTN corrente, se è stato registrato un'appliance con nome Appliance1 e FQDN Mediation Server ms.vdomain.com o un'appliance con nome NewAppliance e FQDN mediation server ms1.vdomain.com stato registrato.
    
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Facoltativo  <br/> |System.String  <br/> |Nome del sito PSTN in cui è registrato il dispositivo. Il valore predefinito è SiteName nel file CloudConnector.ini.  <br/> |
|ApplianceName  <br/> |Facoltativo  <br/> |System.String  <br/> |Nome dell'appliance corrente. Il valore predefinito è il nome computer del server host.  <br/> |
|Locale  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Controllare le configurazioni per la registrazione in locale senza connettersi alla configurazione tenant online.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Register-CcAppliance non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

