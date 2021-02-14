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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Il Reset-CcCACertificate consente di reinstallare il server AD del servizio Autorità di certificazione per creare un nuovo certificato CA radice.
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824252"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
Il Reset-CcCACertificate consente di reinstallare il server AD del servizio Autorità di certificazione per creare un nuovo certificato CA radice.
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>Parametri

None
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene reinstallato il server AD Del servizio Autorità di certificazione per creare un nuovo certificato CA radice:
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Se il certificato della CA radice è compromesso o non è più sicuro, è necessario aggiornare il certificato della CA radice e tutti i certificati emessi dalla CA radice. Il cmdlet Reset-CcCACertificate revoca tutti i certificati, disinstalla e reinstalla l'Autorità di certificazione e quindi pulisce tutti i certificati relativi al servizio Autorità di certificazione precedente. 
  
Per ulteriori informazioni, vedere "I certificati dell'autorità di certificazione o i certificati interni rilasciati a CMS, Mediation Server ed Edge Server sono prossimi alla scadenza o sono compromessi" in Risoluzione dei problemi relativi alla distribuzione di Cloud Connector.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Reset-CcCACertificate non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuna.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) Solo versione 1.4.2
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Solo versione 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) Versione 2.0 e successive
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Versione 2.0 e successive
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

