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
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa la configurazione di Skype for Business Cloud Connector Edition da un file locale al server host Cloud Connector.
ms.openlocfilehash: c72a72351ecb6936832bc5d6a2493c5fa8dfe324
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003336"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importa la configurazione di Skype for Business Cloud Connector Edition da un file locale al server host Cloud Connector.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente copia il CloudConnector. ini dalla directory appliance dell'istanza del connettore Cloud alla directory%SystemDrive%\ProgramData\CloudConnector:
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="Examples"> </a>

Questo cmdlet copia il CloudConnector. ini dalla directory appliance dell'appliance del connettore Cloud alla directory%SystemDrive%\ProgramData\CloudConnector. La directory Appliance viene specificata usando il cmdlet Set-CcApplianceDirectory. Il cmdlet sovrascriverà qualsiasi file esistente in%SystemDrive%\ProgramData\CloudConnector. Questo comando si applica a Cloud Connector Edition versione 2.0.1 e successive.
  
## <a name="parameters"></a>Parametri
<a name="Examples"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Sovrascrivere il file esistente in%SystemDrive%\ProgramData\CloudConnector senza notifica.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="Examples"> </a>

Nessuno. Il cmdlet Import-CcConfiguration non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="Examples"> </a>

Nessuno.
  
## <a name="see-also"></a>Vedere anche
<a name="Examples"> </a>

Export-CcConfiguration
  

