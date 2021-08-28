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
ms.localizationpriority: medium
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Esporta la Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition locale.
ms.openlocfilehash: b2b3ea0171b68701b47b8ae2ed239f2e0495855b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625008"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Esporta la Skype for Business Cloud Connector Edition in un file locale nel server host Skype for Business Cloud Connector Edition locale.
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente il parametro Path viene impostato come percorso completo del file ed esporta le configurazioni in tale file.
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="Examples"> </a>

Il cmdlet Export-CcConfiguration consente di salvare la configurazione del connettore cloud in un file in un percorso selezionato. Questo comando è stato introdotto in Cloud Connector Edition versione 2.0.
  
## <a name="parameters"></a>Parametri
<a name="Examples"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Percorso  <br/> |Obbligatorio  <br/> |System.String  <br/> |Percorso completo del file in cui verranno archiviate le configurazioni del connettore cloud.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="Examples"> </a>

Nessuna. Il cmdlet Export-CcConfiguration non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="Examples"> </a>

Nessuna.
  
## <a name="see-also"></a>Vedere anche
<a name="Examples"> </a>

Import-CcConfiguration
  

