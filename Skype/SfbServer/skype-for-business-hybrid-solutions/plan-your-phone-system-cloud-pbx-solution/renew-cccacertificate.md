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
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Il cmdlet Renew-CcCACertificate consente di rinnovare il certificato CA radice Skype for Business Cloud Connector Edition che sta per scadere o è già scaduto. Questo comando è stato modificato in Update-CcCACertificate in Cloud Connector 2.0 e versioni successive.
ms.openlocfilehash: e92709cd1da0ffccd2b356000dbd2345ba56a1d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824272"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
Il cmdlet Renew-CcCACertificate consente di rinnovare il certificato CA radice Skype for Business Cloud Connector Edition che sta per scadere o è già scaduto. Questo comando è stato modificato in Update-CcCACertificate in Cloud Connector 2.0 e versioni successive.
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>Parametri

None
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene rinnovato il certificato CA radice: 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il certificato DELLA CA radice del connettore cloud è valido per cinque anni dalla data di installazione del servizio Autorità di certificazione.
  
Se il certificato radice è prossimo alla scadenza o è già scaduto, eseguire il cmdlet Renew-CcCACertificate per rinnovare il certificato. Dopo il rinnovo del certificato radice, i nuovi certificati verranno emessi automaticamente dal server AD, dall'archivio di gestione centrale e dal server perimetrale.
  
Se sono presenti più appliance nello stesso sito PSTN, eseguire il cmdlet Renew-CcCACertificate in tutte le appliance dello stesso sito PSTN.
  
Come ultimo passaggio, eseguire Export-CcRootCertificate per esportare il certificato radice in un file locale nel primo dispositivo, quindi copiare e installare il certificato esportato nei gateway PSTN.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Renew-CcCACertificate non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

