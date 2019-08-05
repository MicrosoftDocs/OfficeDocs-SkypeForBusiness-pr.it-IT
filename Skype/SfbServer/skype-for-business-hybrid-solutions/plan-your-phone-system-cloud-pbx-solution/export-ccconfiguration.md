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
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Esporta la configurazione di Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 7548b2fba602364d98c7540607660ccc57710654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190823"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Esporta la configurazione di Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition.
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente imposta il parametro Path come percorso di file completo ed Esporta le configurazioni in tale file.
  
```
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
  

