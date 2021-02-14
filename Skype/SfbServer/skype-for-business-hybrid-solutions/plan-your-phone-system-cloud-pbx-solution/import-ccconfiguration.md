---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa la configurazione di Skype for Business Cloud Connector Edition da un file locale al server host Cloud Connector.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799856"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importa la configurazione di Skype for Business Cloud Connector Edition da un file locale al server host Cloud Connector.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente il CloudConnector.ini dalla directory appliance dell'istanza di Cloud Connector alla directory %SystemDrive%\ProgramData\CloudConnector:
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="Examples"> </a>

Questo cmdlet copia il CloudConnector.ini dalla directory appliance dell'applicazione Cloud Connector alla directory %SystemDrive%\ProgramData\CloudConnector. La directory dell'appliance viene specificata utilizzando il cmdlet Set-CcApplianceDirectory locale. Il cmdlet sovrascriverà qualsiasi file esistente in %SystemDrive%\ProgramData\CloudConnector. Questo comando si applica a Cloud Connector Edition versione 2.0.1 e successive.
  
## <a name="parameters"></a>Parametri
<a name="Examples"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Sovrascrivere il file esistente in %SystemDrive%\ProgramData\CloudConnector senza notifica.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="Examples"> </a>

Nessuna. Il cmdlet Import-CcConfiguration non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="Examples"> </a>

Nessuna.
  
## <a name="see-also"></a>Vedere anche
<a name="Examples"> </a>

Export-CcConfiguration
  

