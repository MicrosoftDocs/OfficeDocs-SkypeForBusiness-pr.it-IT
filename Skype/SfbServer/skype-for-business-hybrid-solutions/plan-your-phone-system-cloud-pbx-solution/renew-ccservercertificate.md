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
description: Il cmdlet Renew-CcServerCertificate rinnova i certificati per Skype for Business Cloud Connector Edition quando è vicino alla scadenza o è già scaduto. Questo comando è stato modificato in Update-CcServerCertificate in Cloud Connector 2,0 e versioni successive.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824262"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
Il cmdlet Renew-CcServerCertificate rinnova i certificati per Skype for Business Cloud Connector Edition quando è vicino alla scadenza o è già scaduto. Questo comando è stato modificato in Update-CcServerCertificate in Cloud Connector 2,0 e versioni successive. 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente rinnova i certificati per l'archivio di gestione centrale, il Mediation Server e il server perimetrale quando i certificati sono a scadenza quasi scaduta o già scaduti:
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>Esempio 2

Nell'esempio successivo vengono rinnovati i certificati per Mediation Server e Edge Server quando la scadenza è prossima o è già scaduta:
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

I certificati interni del connettore Cloud rilasciati a Central Management store, Mediation Server e Edge Server sono validi per due anni dopo il rilascio da parte di un servizio autorità di certificazione. Se i certificati sono a scadenza quasi scaduta o già scaduti, eseguire il cmdlet Renew-CcServerCertificate per rinnovare i certificati. 
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Ruoli  <br/> |Facoltativo  <br/> |System. Array  <br/> | Matrice di ruoli del server del connettore Cloud. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Renew-CcServerCertificate non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

