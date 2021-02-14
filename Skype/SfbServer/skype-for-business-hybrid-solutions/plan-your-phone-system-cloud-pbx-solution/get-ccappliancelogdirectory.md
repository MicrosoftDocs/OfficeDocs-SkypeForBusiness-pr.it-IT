---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Il cmdlet Get-CcApplianceLogDirectory mostra la directory corrente in cui sono archiviati i registri per un'applicazione Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800826"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
Il cmdlet Get-CcApplianceLogDirectory mostra la directory corrente in cui sono archiviati i registri per un'applicazione Skype for Business Cloud Connector Edition.
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Parametri

None
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene mostrata la cartella corrente in cui sono archiviati i registri per l'applicazione corrente di Cloud Connector:
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Get-CcApplianceLogDirectory mostra la directory corrente in cui sono archiviati i registri per un'applicazione Cloud Connector. La cartella predefinita è C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs. 
  
È possibile modificare la directory utilizzando il cmdlet Set-CcApplianceDirectory locale. 
  
Nota: non esiste alcun cmdlet che modifica solo il percorso della cartella dei registri senza modificare la directory dell'appliance.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Get-CcApplianceLogDirectory non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Questo comando restituisce un percorso di file.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

