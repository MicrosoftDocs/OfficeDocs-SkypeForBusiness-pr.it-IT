---
title: Install-CcAppliance
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
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Il cmdlet Install-CcAppliance consente di installare l'appliance Skype for Business Cloud Connector Edition, incluse le macchine virtuali AD, Central Management Store, Mediation Server e Edge Server, nel server host.
ms.openlocfilehash: b88b869e3c30783a69bc16ab690a258506ebcc90e849eb474a17859140485e8d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343180"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
Il cmdlet Install-CcAppliance consente di installare l'appliance Skype for Business Cloud Connector Edition, incluse le macchine virtuali AD, Central Management Store, Mediation Server e Edge Server, nel server host. 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene installata una nuova appliance Cloud Connector nel server host:
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente aggiorna Cloud Connector alla versione più recente:
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Esempio 3

Nell'esempio seguente vengono rimosse tutte le credenziali del connettore cloud memorizzate nella cache nel server host, viene richiesto all'utente di specificare di nuovo tutte le informazioni sulle credenziali e quindi viene installato Cloud Connector:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Esempio 4

Nell'esempio seguente vengono visualizzati tutti i passaggi di distribuzione nella console di PowerShell:
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

Il parametro -ShowStepsOnly è solo per la risoluzione dei problemi.
  
### <a name="example-5"></a>Esempio 5

Nell'esempio seguente vengono generati file di configurazione per ogni passaggio di distribuzione nel server host. I file di configurazione vengono salvati nella \<ApplianceRoot\> cartella \Instances \\<Version \> -default\ExportedConfig nel server host:
  
```powershell
Install-CcAppliance -PrepareOnly
```

Per determinare la radice dell'appliance, eseguire il cmdlet Get-CcApplianceDirectory appliance. 
  
### <a name="example-6"></a>Esempio 6

Nell'esempio seguente Cloud Connector esegue i passaggi di distribuzione 1, 2 e 3 per creare commutatori virtuali, creare una macchina virtuale AD e installare il servizio di dominio nel server AD. Ignora il passaggio se il passaggio è già stato eseguito:
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

Il parametro SkipExistingObjects deve essere utilizzato insieme al parametro Steps.
  
> [!NOTE]
> Il parametro Steps è solo a scopo di risoluzione dei problemi. Non utilizzare questo parametro per distribuire un'appliance o per aggiornare un'appliance in servizio. 
  
Per determinare i passaggi della distribuzione, eseguire il comando seguente:
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Install-CcAppliance viene utilizzato per distribuire Cloud Connector in una nuova appliance o per aggiornare un'appliance esistente alla versione più recente.
  
Se si dispone di un nuovo dispositivo, leggere Preparare l'ambiente per Cloud Connector, eseguire il cmdlet Register-CcAppliance per registrare l'appliance e quindi eseguire il cmdlet Install-CcAppliance. Per ulteriori informazioni, vedere [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e Deploy multiple sites in Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md) 
  
Se si dispone di una distribuzione esistente di Cloud Connector e si desidera eseguire l'aggiornamento, seguire le istruzioni in Eseguire l'aggiornamento [a una nuova versione di Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> | Generare file di configurazione per ogni passaggio di distribuzione. Questo parametro è solo per la risoluzione dei problemi. <br/> |
|ShowStepsOnly  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Visualizzare solo i nomi dei passaggi di distribuzione. Questo parametro è solo per la risoluzione dei problemi.  <br/> |
|SkipExistingObjects  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Questo parametro deve essere utilizzato insieme al parametro Steps. Questo parametro è solo per la risoluzione dei problemi.  <br/> |
|Procedura  <br/> |Facoltativo  <br/> |System.Array  <br/> |Eseguire i passaggi di distribuzione. Questo parametro è solo per la risoluzione dei problemi.  <br/> |
|Aggiornamento  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Aggiornare il connettore cloud esistente alla versione più recente.  <br/> |
|UpdateAllCredentials  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Rimuovere tutte le credenziali del connettore cloud nella cache. Richiedere all'utente di specificare nuove informazioni sulle credenziali per l'installazione.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Install-CcAppliance non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

