---
title: Renew-CcCACertificate
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
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Il cmdlet Renew-CcCACertificate consente di rinnovare il Skype for Business Cloud Connector Edition ca radice che è prossimo alla scadenza o è già scaduto. Questo comando è stato modificato in Update-CcCACertificate in Cloud Connector 2.0 e versioni successive.
ms.openlocfilehash: f48839360af0be72279547e1e1f9cbd695c48b39
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624978"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
Il cmdlet Renew-CcCACertificate consente di rinnovare il Skype for Business Cloud Connector Edition ca radice che è prossimo alla scadenza o è già scaduto. Questo comando è stato modificato in Update-CcCACertificate in Cloud Connector 2.0 e versioni successive.
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene rinnovato il certificato della CA radice: 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il certificato della CA radice del connettore cloud è valido per cinque anni a partire dalla data di installazione del servizio Autorità di certificazione.
  
Se il certificato radice è prossimo alla scadenza o è già scaduto, eseguire il cmdlet Renew-CcCACertificate per rinnovare il certificato. Dopo il rinnovo del certificato radice, il server AD, l'archivio di gestione centrale e il server perimetrale verranno emessi automaticamente nuovi certificati.
  
Se sono presenti più appliance nello stesso sito PSTN, eseguire il cmdlet Renew-CcCACertificate in tutte le appliance dello stesso sito PSTN.
  
Come ultimo passaggio, eseguire Export-CcRootCertificate per esportare il certificato radice in un file locale nella prima appliance, quindi copiare e installare il certificato esportato nei gateway PSTN.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Renew-CcCACertificate non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

