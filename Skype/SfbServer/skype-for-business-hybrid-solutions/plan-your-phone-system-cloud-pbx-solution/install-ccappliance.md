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
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Il cmdlet Install-CcAppliance installa l'accessorio Cloud Connector Edition di Skype for business, tra cui le macchine virtuali AD, Central Management store, Mediation Server e Edge Server nel server host.
ms.openlocfilehash: cccf500c6506c8ba3459631d5c823940907ad213
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003326"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
Il cmdlet Install-CcAppliance installa l'accessorio Cloud Connector Edition di Skype for business, tra cui le macchine virtuali AD, Central Management store, Mediation Server e Edge Server nel server host. 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente installa un nuovo accessorio Cloud Connector nel server host:
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente aggiorna Cloud Connector alla versione più recente:
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Esempio 3

L'esempio seguente rimuove tutte le credenziali di Cloud Connector memorizzate nella cache nel server host, chiede all'utente di specificare di nuovo tutte le informazioni sulle credenziali e quindi installa Cloud Connector:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Esempio 4

L'esempio seguente mostra tutti i passaggi di distribuzione nella console di PowerShell:
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

Il parametro-ShowStepsOnly è solo per la risoluzione dei problemi.
  
### <a name="example-5"></a>Esempio 5

L'esempio seguente genera i file di configurazione per ogni passaggio di distribuzione nel server host. I file di configurazione vengono salvati \<nella\>cartella\\ ApplianceRoot \Instances\><-default\ExportedConfig nel server host:
  
```powershell
Install-CcAppliance -PrepareOnly
```

Per determinare la radice dell'accessorio, eseguire il cmdlet Get-CcApplianceDirectory. 
  
### <a name="example-6"></a>Esempio 6

Nell'esempio seguente, Cloud Connector esegue i passaggi di distribuzione 1, 2 e 3 per creare switch virtuali, creare una macchina virtuale AD e installare il servizio del dominio nel server degli annunci. Il passaggio viene saltato se il passaggio è già stato eseguito:
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

Il parametro SkipExistingObjects deve essere usato insieme al parametro Steps.
  
> [!NOTE]
> Il parametro Steps è solo per scopi di risoluzione dei problemi. Non usare questo parametro per distribuire un dispositivo o per aggiornare un dispositivo in servizio. 
  
Per determinare i passaggi della distribuzione, eseguire il comando seguente:
  
Installare-CcAppliance-ShowStepsOnly
  
## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Install-CcAppliance viene usato per distribuire Cloud Connector in un nuovo dispositivo o per aggiornare un dispositivo esistente alla versione più recente.
  
Se si dispone di un nuovo dispositivo, leggere prima di tutto preparare l'ambiente per Cloud Connector, eseguire il cmdlet Register-CcAppliance per registrare l'accessorio e quindi eseguire il cmdlet Install-CcAppliance. Per altre informazioni, vedere [distribuire un singolo sito nel Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e [distribuire più siti in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
Se si ha una distribuzione di Cloud Connector esistente e si vuole eseguire l'aggiornamento, seguire le istruzioni visualizzate in [eseguire l'aggiornamento a una nuova versione di Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> | Genera file di configurazione per ogni passaggio di distribuzione. Questo parametro è solo per la risoluzione dei problemi. <br/> |
|ShowStepsOnly  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Visualizzare solo i nomi dei passaggi di distribuzione. Questo parametro è solo per la risoluzione dei problemi.  <br/> |
|SkipExistingObjects  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Questo parametro deve essere usato insieme al parametro Steps. Questo parametro è solo per la risoluzione dei problemi.  <br/> |
|Passaggi  <br/> |Facoltativo  <br/> |System. Array  <br/> |Eseguire la procedura di distribuzione. Questo parametro è solo per la risoluzione dei problemi.  <br/> |
|Upgrade  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Aggiornare il connettore cloud esistente alla versione più recente.  <br/> |
|UpdateAllCredentials  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Rimuovere tutte le credenziali del connettore cloud nella cache. Richiedi all'utente di specificare le nuove informazioni sulle credenziali per l'installazione.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Install-CcAppliance non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

