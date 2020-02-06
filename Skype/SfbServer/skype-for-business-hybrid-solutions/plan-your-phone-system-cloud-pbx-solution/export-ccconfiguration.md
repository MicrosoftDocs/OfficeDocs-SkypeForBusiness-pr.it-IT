---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Esporta la configurazione di Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition.
ms.openlocfilehash: cd0745081e3f069aaf58c9ffdbf24494bfb3ece1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801466"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Esporta la configurazione di Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition.
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente imposta il parametro Path come percorso di file completo ed Esporta le configurazioni in tale file.
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="Examples"> </a>

Il cmdlet Export-CcConfiguration consente di salvare la configurazione del connettore Cloud in un file in un percorso selezionato. Questo comando è stato introdotto in Cloud Connector Edition versione 2,0.
  
## <a name="parameters"></a>Parametri
<a name="Examples"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Percorso  <br/> |Obbligatorio  <br/> |System.String  <br/> |Percorso file completo in cui verranno archiviate le configurazioni del connettore Cloud.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="Examples"> </a>

Nessuno. Il cmdlet Export-CcConfiguration non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="Examples"> </a>

Nessuno.
  
## <a name="see-also"></a>Vedere anche
<a name="Examples"> </a>

Import-CcConfiguration
  

