---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Il cmdlet Export-CcRootCertificate esporta il certificato CA radice in un file locale nel server host Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800916"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Il cmdlet Export-CcRootCertificate esporta il certificato CA radice in un file locale nel server host Skype for Business Cloud Connector Edition. 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente il parametro Path viene impostato come percorso di directory e non come percorso di file. Viene generato il file c:\test\CCERootCertificates.p7b.
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il Export-CcRootCertificate consente di salvare i certificati radice e intermedi in un percorso file. Ciò può essere utile in caso di uno scenario di ripristino di emergenza. 
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Percorso  <br/> |Obbligatorio  <br/> |System.String  <br/> |Percorso del file in cui verrà archiviato il certificato.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Export-CcRootCertificate non accetta input da pipeline. 
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

Nessuno
  

