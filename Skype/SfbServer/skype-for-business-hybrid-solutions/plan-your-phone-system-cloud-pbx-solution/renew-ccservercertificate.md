---
title: Renew-CcServerCertificate
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
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: Il Renew-CcServerCertificate consente di rinnovare i certificati per Skype for Business Cloud Connector Edition quando sono prossimi alla scadenza o sono già scaduti. Questo comando è stato modificato in Update-CcServerCertificate in Cloud Connector 2.0 e versioni successive.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824262"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
Il Renew-CcServerCertificate consente di rinnovare i certificati per Skype for Business Cloud Connector Edition quando sono prossimi alla scadenza o sono già scaduti. Questo comando è stato modificato in Update-CcServerCertificate in Cloud Connector 2.0 e versioni successive. 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente vengono rinnovati i certificati per l'archivio di gestione centrale, il Mediation Server e il server perimetrale quando i certificati sono prossimi alla scadenza o sono già scaduti:
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente vengono rinnovati i certificati per Mediation Server ed Edge Server quando sono prossimi alla scadenza o sono già scaduti:
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

I certificati interni del connettore cloud emessi per l'archivio di gestione centrale, il Mediation Server e il server perimetrale sono validi per due anni dopo l'emissione da un servizio autorità di certificazione. Se i certificati sono prossimi alla scadenza o sono già scaduti, eseguire il cmdlet Renew-CcServerCertificate per rinnovare i certificati. 
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Ruoli  <br/> |Facoltativo  <br/> |System.Array  <br/> | Array di ruoli del server Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Renew-CcServerCertificate non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

