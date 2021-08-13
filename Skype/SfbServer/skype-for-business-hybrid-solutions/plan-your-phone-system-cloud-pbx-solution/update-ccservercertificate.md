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
description: Il cmdlet Update-CcServerCertificate consente di rinnovare i certificati per Skype for Business Cloud Connector Edition quando sono prossimi alla scadenza o sono già scaduti.
ms.openlocfilehash: 0545f4923a4f1abd654674024313c6f22665cb7123d87d9d21c3676452bd8fcf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344525"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
Il cmdlet Update-CcServerCertificate consente di rinnovare i certificati per Skype for Business Cloud Connector Edition quando sono prossimi alla scadenza o sono già scaduti. 
  
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

Nell'esempio seguente vengono rinnovati i certificati per Mediation Server e Server perimetrale quando sono prossimi alla scadenza o sono già scaduti:
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

I certificati interni del connettore cloud rilasciati all'archivio di gestione centrale, al Mediation Server e al server perimetrale sono validi per due anni dopo l'emissione da un servizio Autorità di certificazione. Se i certificati sono prossimi alla scadenza o sono già scaduti, eseguire il cmdlet Update-CcServerCertificate per rinnovare i certificati. 
  
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

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

