---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: Il cmdlet Update-CcCACertificate consente di rinnovare il certificato CA radice Skype for Business Cloud Connector Edition che sta per scadere o è già scaduto.
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824120"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
Il cmdlet Update-CcCACertificate consente di rinnovare il certificato CA radice Skype for Business Cloud Connector Edition che sta per scadere o è già scaduto. 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>Parametri

Nessuna.
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene rinnovato il certificato CA radice: 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il certificato DELLA CA radice del connettore cloud è valido per cinque anni dalla data di installazione del servizio Autorità di certificazione.
  
Se il certificato radice è prossimo alla scadenza o è già scaduto, eseguire il cmdlet Update-CcCACertificate per rinnovare il certificato. Dopo il rinnovo del certificato radice, i nuovi certificati verranno emessi automaticamente dal server AD, dall'archivio di gestione centrale e dal server perimetrale.
  
Se sono presenti più appliance nello stesso sito PSTN, eseguire il cmdlet Update-CcCACertificate in tutte le appliance dello stesso sito PSTN.
  
Come ultimo passaggio, eseguire Export-CcRootCertificate per esportare il certificato radice in un file locale nel primo dispositivo, quindi copiare e installare il certificato esportato nei gateway PSTN.
  
Questo comando sostituisce il cmdlet Renew-CcCACertificate in Cloud Connector 2.0 e versioni successive.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Update-CcCACertificate non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuna. 
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

