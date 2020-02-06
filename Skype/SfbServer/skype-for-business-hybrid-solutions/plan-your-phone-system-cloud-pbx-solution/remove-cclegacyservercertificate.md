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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Il cmdlet Remove-CcLegacyServerCertificate rimuove i certificati server legacy in Central Management store, Mediation Server e Edge Server dopo l'esecuzione dei cmdlet Renew-CcCACertificate o Renew CcServerCertificate.
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824282"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
Il cmdlet Remove-CcLegacyServerCertificate rimuove i certificati server legacy in Central Management store, Mediation Server e Edge Server dopo l'esecuzione dei cmdlet Renew-CcCACertificate o Renew CcServerCertificate.
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente consente di rimuovere i certificati legacy rilasciati per Central Management store, Mediation Server e Edge Server dopo aver rinnovato i certificati:
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente rimuove i certificati rilasciati per Mediation Server e Edge Server dopo aver rinnovato i certificati: 
  
```powershell
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
  

