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
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Il cmdlet Register-CcAppliance registra le informazioni sugli apparecchi in un sito PSTN in una configurazione tenant online. Un elettrodomestico deve essere registrato prima che possa essere distribuito e gestito dal servizio di gestione di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 93f1fe59a199214615c5ecdf8445f6c363ce6bbe
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003306"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
Il cmdlet Register-CcAppliance registra le informazioni sugli apparecchi in un sito PSTN in una configurazione tenant online. Un elettrodomestico deve essere registrato prima che possa essere distribuito e gestito dal servizio di gestione di Skype for Business Cloud Connector Edition.
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente registra le informazioni sull'appliance corrente in una configurazione del tenant online:
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente controlla la configurazione per la registrazione localmente senza connettersi a una configurazione del tenant online:
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>Esempio 3

L'esempio seguente registra l'appliance corrente con il nome "Appliance1" al sito PSTN "Microsoft1":
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

È necessario specificare il nome dell'account di amministratore del tenant e la password. Usare l'account creato per la gestione di Cloud Connector online. 
  
In versione 1.4.2 e versioni precedenti seguire le istruzioni fornite per specificare la password del certificato esterno, la password di amministratore in modalità provvisoria, la password di amministratore del dominio e la password di amministratore VM. 
  
In versione 2,0 e successive seguire le istruzioni per specificare la password del certificato esterno, la password di CceService e la password di CABackupFile.
  
Al termine della registrazione, riavviare il servizio di gestione di Cloud Connector e accedere all'account servizi come CceService.
  
SiteName combinato con il nome di dominio completo esterno del server perimetrale nel file CloudConnector. ini è considerato un'identità del sito PSTN. Se per la registrazione di un sito non è stato usato né il nome di dominio completo esterno per SiteName né l'Edge Server, verrà creato un nuovo sito per l'appliance in una configurazione tenant online. Se viene trovata un'identità del sito PSTN, un sito PSTN utilizzerà questa identità e l'accessorio verrà registrato nel sito PSTN. 
  
Nella situazione seguente il cmdlet non riesce e indica che Microsoft1 è già registrato: 
  
- Nomesito è Microsoft1 e il nome di dominio completo esterno di Edge Server è edgserver1.contoso.com. 
    
- Un sito PSTN il cui siteName è Microsoft1 e il nome di dominio completo esterno di Edge Server è edgserver.contoso.com.
    
- Un sito PSTN il cui siteName è nuovosito e il nome di dominio completo esterno di Edge Server è edgserver1.contoso.com è stato registrato. 
    
Appliancename combinata con l'FQDN di Mediation Server nel file CloudConnector. ini è considerata un'identità Appliance. Se per la registrazione di un dispositivo non è stato usato né l'FQDN di Mediation Server, verrà creato un nuovo dispositivo nella configurazione del tenant online. Se l'accessorio è già registrato, il cmdlet avrà esito negativo.
  
Nella situazione seguente il cmdlet non riesce e indica che l'accessorio è già registrato: 
  
- Appliancename è Appliance1 e il nome di dominio completo di Mediation Server è ms1.vdomain.com.
    
- Nel sito PSTN corrente, se un dispositivo il cui nome è Appliance1 e l'FQDN di Mediation Server è ms.vdomain.com o un accessorio il cui nome è NewAppliance e FQDN di Mediation Server, ms1.vdomain.com è stato registrato.
    
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Facoltativo  <br/> |System.String  <br/> |Nome del sito PSTN a cui è registrata l'appliance. Il valore predefinito è il valore SiteName nel file CloudConnector. ini.  <br/> |
|Appliancename  <br/> |Facoltativo  <br/> |System.String  <br/> |Nome dell'appliance corrente. Il valore predefinito è il nome del computer del server host.  <br/> |
|Locale  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Verificare le configurazioni per la registrazione localmente senza connettersi alla configurazione del tenant online.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Register-CcAppliance non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

