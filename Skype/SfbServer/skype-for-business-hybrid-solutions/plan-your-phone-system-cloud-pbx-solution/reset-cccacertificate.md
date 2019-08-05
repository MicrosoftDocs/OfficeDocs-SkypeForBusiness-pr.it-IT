---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Il cmdlet Reset-CcCACertificate reinstalla il server degli annunci del servizio autorità di certificazione per creare un nuovo certificato della CA radice.
ms.openlocfilehash: 3cac8629a52d915df55408a44d8d31701106a5bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190661"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
Il cmdlet Reset-CcCACertificate reinstalla il server degli annunci del servizio autorità di certificazione per creare un nuovo certificato della CA radice.
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente reinstalla il server degli annunci del servizio autorità di certificazione per creare un nuovo certificato della CA radice:
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Se il certificato della CA radice è compromesso o non è più sicuro, è necessario aggiornare il certificato della CA radice e tutti i certificati emessi dalla CA radice. Il cmdlet Reset-CcCACertificate revoca tutti i certificati, disinstalla e reinstalla l'autorità di certificazione e quindi pulisce tutti i certificati relativi al vecchio servizio autorità di certificazione. 
  
Per altre informazioni, vedere "i certificati di autorità di certificazione o i certificati interni rilasciati a CMS, Mediation Server e Edge Server sono scaduti o compromessi" in risoluzione dei problemi relativi alla distribuzione di Cloud Connector.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Reset-CcCACertificate non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) Solo versione 1.4.2
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Solo versione 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) Versione 2,0 e successive
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Versione 2,0 e successive
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

