---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Il cmdlet Remove-CcLegacyServerCertificate rimuove i certificati server legacy in Central Management store, Mediation Server e Edge Server dopo l'esecuzione dei cmdlet Renew-CcCACertificate o Renew CcServerCertificate.
ms.openlocfilehash: ab332f6f0c88de01f59342002f6387ab8a83a13b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190685"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
Il cmdlet Remove-CcLegacyServerCertificate rimuove i certificati server legacy in Central Management store, Mediation Server e Edge Server dopo l'esecuzione dei cmdlet Renew-CcCACertificate o Renew CcServerCertificate.
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente consente di rimuovere i certificati legacy rilasciati per Central Management store, Mediation Server e Edge Server dopo aver rinnovato i certificati:
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente rimuove i certificati rilasciati per Mediation Server e Edge Server dopo aver rinnovato i certificati: 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>Parametri
<a name="Examples"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Ruoli <br/> |Facoltativo  <br/> |System. Array  <br/> | Matrice di ruoli del server del connettore Cloud. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Remove-CcLegacyServerCertificate non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

