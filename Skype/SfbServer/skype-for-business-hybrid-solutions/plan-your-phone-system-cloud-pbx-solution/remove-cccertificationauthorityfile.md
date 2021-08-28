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
ms.localizationpriority: medium
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: Il cmdlet Remove-CcCertificationAuthorityFile rimuove il file di backup del servizio autorità di certificazione nella cartella CA nella directory della condivisione del sito per Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 93141fee2ab2bf5af4ac826f4926523bd26e9e45
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624988"
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
  

