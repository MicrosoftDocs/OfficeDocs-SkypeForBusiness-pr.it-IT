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
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Il cmdlet Renew-CcCACertificate rinnova il certificato della CA radice di Skype for Business Cloud Connector Edition che è vicino alla scadenza o è già scaduto. Questo comando è stato modificato in Update-CcCACertificate in Cloud Connector 2,0 e versioni successive.
ms.openlocfilehash: f1e376b5b944468ec5bf508c6221a099a83d4804
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190679"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
Il cmdlet Renew-CcCACertificate rinnova il certificato della CA radice di Skype for Business Cloud Connector Edition che è vicino alla scadenza o è già scaduto. Questo comando è stato modificato in Update-CcCACertificate in Cloud Connector 2,0 e versioni successive.
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente rinnova il certificato della CA radice: 
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il certificato della CA radice del connettore Cloud è valido per cinque anni dalla data in cui è installato il servizio autorità di certificazione.
  
Se il certificato radice è vicino alla scadenza o è già scaduto, eseguire il cmdlet Renew-CcCACertificate per rinnovare il certificato. Dopo il rinnovo del certificato radice, verranno emessi automaticamente nuovi certificati nel server AD, Central Management store e Edge Server.
  
Se sono presenti più dispositivi nello stesso sito PSTN, eseguire il cmdlet Renew-CcCACertificate in tutti gli apparecchi dello stesso sito PSTN.
  
Come ultimo passaggio, eseguire Export-CcRootCertificate per esportare il certificato radice in un file locale nel primo appliance, quindi copiare e installare il certificato esportato nei gateway PSTN.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Renew-CcCACertificate non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

