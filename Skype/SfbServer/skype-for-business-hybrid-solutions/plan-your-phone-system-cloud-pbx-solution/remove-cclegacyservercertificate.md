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
description: Il cmdlet Remove-CcLegacyServerCertificate rimuove i certificati del server legacy nell'archivio di gestione centrale, nel Mediation Server e nel server perimetrale dopo aver eseguito i cmdlet Renew-CcCACertificate o Renew CcServerCertificate.
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824282"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
Il cmdlet Remove-CcLegacyServerCertificate rimuove i certificati del server legacy nell'archivio di gestione centrale, nel Mediation Server e nel server perimetrale dopo aver eseguito i cmdlet Renew-CcCACertificate o Renew CcServerCertificate.
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente vengono rimossi i certificati legacy emessi per l'archivio di gestione centrale, il Mediation Server e il server perimetrale dopo il rinnovo dei certificati:
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente vengono rimossi i certificati emessi per Mediation Server ed Edge Server dopo aver rinnovato i certificati: 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>Parametri
<a name="Examples"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Ruoli <br/> |Facoltativo  <br/> |System.Array  <br/> | Array di ruoli del server Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Remove-CcLegacyServerCertificate non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

