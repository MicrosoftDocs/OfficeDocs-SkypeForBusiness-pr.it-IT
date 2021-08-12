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
description: Importa la Skype for Business Cloud Connector Edition da un file locale al server host Cloud Connector.
ms.openlocfilehash: 4ac32f460c2c493f5d78f1a38adcdd0728763bbbcf57a67470823fb88d407d09
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349498"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importa la Skype for Business Cloud Connector Edition da un file locale al server host Cloud Connector.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente copia il CloudConnector.ini dalla directory appliance dell'istanza di Cloud Connector nella directory %SystemDrive%\ProgramData\CloudConnector:
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="Examples"> </a>

Questo cmdlet copia il CloudConnector.ini dalla directory appliance dell'appliance Cloud Connector alla directory %SystemDrive%\ProgramData\CloudConnector. La directory dell'appliance viene specificata utilizzando il cmdlet Set-CcApplianceDirectory. Il cmdlet sovrascriverà qualsiasi file esistente in %SystemDrive%\ProgramData\CloudConnector. Questo comando si applica a Cloud Connector Edition versione 2.0.1 e successive.
  
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
  

