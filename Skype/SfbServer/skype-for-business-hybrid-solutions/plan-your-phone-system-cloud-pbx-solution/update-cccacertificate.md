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
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: Il cmdlet Update-CcCACertificate rinnova il certificato della CA radice di Skype for Business Cloud Connector Edition che è vicino alla scadenza o è già scaduto.
ms.openlocfilehash: 15be5d4518d7e375b4804ed2d9f22bd35a45ca7e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003126"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
Il cmdlet Update-CcCACertificate rinnova il certificato della CA radice di Skype for Business Cloud Connector Edition che è vicino alla scadenza o è già scaduto. 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>Parametri

Nessuno.
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente rinnova il certificato della CA radice: 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il certificato della CA radice del connettore Cloud è valido per cinque anni dalla data in cui è installato il servizio autorità di certificazione.
  
Se il certificato radice è vicino alla scadenza o è già scaduto, eseguire il cmdlet Update-CcCACertificate per rinnovare il certificato. Dopo il rinnovo del certificato radice, verranno emessi automaticamente nuovi certificati nel server AD, Central Management store e Edge Server.
  
Se sono presenti più dispositivi nello stesso sito PSTN, eseguire il cmdlet Update-CcCACertificate in tutti gli apparecchi dello stesso sito PSTN.
  
Come ultimo passaggio, eseguire Export-CcRootCertificate per esportare il certificato radice in un file locale nel primo appliance, quindi copiare e installare il certificato esportato nei gateway PSTN.
  
Questo comando sostituisce il cmdlet Renew-CcCACertificate in Cloud Connector 2,0 e versioni successive.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Update-CcCACertificate non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno. 
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

