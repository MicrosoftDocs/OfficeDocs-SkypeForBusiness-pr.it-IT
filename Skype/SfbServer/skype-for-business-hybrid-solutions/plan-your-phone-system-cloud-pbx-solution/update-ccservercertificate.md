---
title: Update-CcServerCertificate
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
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: Il Update-CcServerCertificate consente di rinnovare i certificati per Skype for Business Cloud Connector Edition quando sono prossimi alla scadenza o sono già scaduti.
ms.openlocfilehash: da52efcd3fdf6a0793e085098bf6f72725115e9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824110"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
Il Update-CcServerCertificate consente di rinnovare i certificati per Skype for Business Cloud Connector Edition quando sono prossimi alla scadenza o sono già scaduti. 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente vengono rinnovati i certificati per l'archivio di gestione centrale, il Mediation Server e il server perimetrale quando i certificati sono prossimi alla scadenza o sono già scaduti:
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente vengono rinnovati i certificati per Mediation Server ed Edge Server quando sono prossimi alla scadenza o sono già scaduti:
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

I certificati interni del connettore cloud emessi per l'archivio di gestione centrale, il Mediation Server e il server perimetrale sono validi per due anni dopo l'emissione da un servizio autorità di certificazione. Se i certificati sono prossimi alla scadenza o sono già scaduti, eseguire il cmdlet Update-CcServerCertificate per rinnovare i certificati. 
  
Questo comando sostituisce il cmdlet Renew-CcServerCertificate in Cloud Connector 2.0 e versioni successive.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Ruoli  <br/> |Facoltativo  <br/> |System.Array  <br/> | Array di ruoli del server Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Update-CcServerCertificate non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

