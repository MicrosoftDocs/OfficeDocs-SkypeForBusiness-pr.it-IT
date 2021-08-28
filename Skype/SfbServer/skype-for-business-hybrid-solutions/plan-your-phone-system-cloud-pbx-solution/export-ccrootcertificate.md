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
ms.localizationpriority: medium
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Il cmdlet Export-CcRootCertificate esporta il certificato ca radice in un file locale nel server host Skype for Business Cloud Connector Edition locale.
ms.openlocfilehash: e00041088af39bf6f11abd5309ff293bd37bf38f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624998"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Il cmdlet Export-CcRootCertificate esporta il certificato ca radice in un file locale nel server host Skype for Business Cloud Connector Edition locale. 
  
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

Il cmdlet Export-CcRootCertificate consente di salvare i certificati radice e intermedi in un percorso di file. Ciò può essere utile in caso di uno scenario di ripristino di emergenza. 
  
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

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

Nessuno
  

