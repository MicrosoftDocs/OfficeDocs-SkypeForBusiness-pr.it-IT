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
description: Il cmdlet Update-CcCACertificate consente di rinnovare Skype for Business Cloud Connector Edition certificato CA radice che è prossimo alla scadenza o è già scaduto.
ms.openlocfilehash: 640ca982cd005e9805d7214212d847edcc6856456b6995fe1ae689778da58f61
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344535"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
Il cmdlet Update-CcCACertificate consente di rinnovare Skype for Business Cloud Connector Edition certificato CA radice che è prossimo alla scadenza o è già scaduto. 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>Parametri

Nessuna.
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene rinnovato il certificato della CA radice: 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il certificato della CA radice del connettore cloud è valido per cinque anni a partire dalla data di installazione del servizio Autorità di certificazione.
  
Se il certificato radice è prossimo alla scadenza o è già scaduto, eseguire il cmdlet Update-CcCACertificate per rinnovare il certificato. Dopo il rinnovo del certificato radice, il server AD, l'archivio di gestione centrale e il server perimetrale verranno emessi automaticamente nuovi certificati.
  
Se sono presenti più appliance nello stesso sito PSTN, eseguire il cmdlet Update-CcCACertificate in tutte le appliance dello stesso sito PSTN.
  
Come ultimo passaggio, eseguire Export-CcRootCertificate per esportare il certificato radice in un file locale nella prima appliance, quindi copiare e installare il certificato esportato nei gateway PSTN.
  
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
  

