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
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Il cmdlet Export-CcRootCertificate Esporta il certificato della CA radice in un file locale nel server host Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 7d6d0978698b4b20b570107b51c9a89ff237b730
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190796"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Il cmdlet Export-CcRootCertificate Esporta il certificato della CA radice in un file locale nel server host Skype for Business Cloud Connector Edition. 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente imposta il parametro Path come percorso di directory, non un percorso di file. Genera il file c:\test\CCERootCertificates.p7b.
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Export-CcRootCertificate consente di salvare la radice e i certificati intermedi in un percorso di file. Può essere utile in caso di scenario di ripristino di emergenza. 
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Percorso  <br/> |Obbligatorio  <br/> |System.String  <br/> |Percorso del file in cui verrà archiviato il certificato.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Export-CcRootCertificate non accetta l'input da pipeline. 
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

Nessuno
  

