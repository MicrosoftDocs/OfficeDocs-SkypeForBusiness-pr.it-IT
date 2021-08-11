---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: Il cmdlet Remove-CcCertificationAuthorityFile rimuove il file di backup del servizio autorità di certificazione nella cartella CA nella directory della condivisione del sito per Skype for Business Cloud Connector Edition.
ms.openlocfilehash: aaff21023a63e8933235f4c462c1152339381ca0d9571ded57f6b43742679624
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288774"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
Il cmdlet Remove-CcCertificationAuthorityFile rimuove il file di backup del servizio autorità di certificazione " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" nella cartella CA nella directory della condivisione del sito per Skype for Business Cloud Connector Edition. 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene rimosso il file di backup del servizio Autorità di certificazione " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" nella cartella CA nella directory della condivisione del sito:
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Remove-CcCertificationAuthorityFile non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

