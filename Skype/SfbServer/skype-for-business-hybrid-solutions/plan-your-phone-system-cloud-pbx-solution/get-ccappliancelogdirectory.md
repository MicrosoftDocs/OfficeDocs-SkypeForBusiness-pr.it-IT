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
description: Il cmdlet Get-CcApplianceLogDirectory mostra la directory corrente in cui sono archiviati i registri per Skype for Business Cloud Connector Edition appliance.
ms.openlocfilehash: 75f3ba3a5de5198456e053bd51ef567df1a0ae43461e9888e87294d3af406288
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318659"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
Il cmdlet Get-CcApplianceLogDirectory mostra la directory corrente in cui sono archiviati i registri per Skype for Business Cloud Connector Edition appliance.
  
Questo cmdlet si applica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra la cartella corrente in cui sono archiviati i registri per l'appliance corrente di Cloud Connector:
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Get-CcApplianceLogDirectory mostra la directory corrente in cui sono archiviati i registri per un'appliance Cloud Connector. La cartella predefinita è C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs. 
  
È possibile modificare la directory utilizzando il cmdlet Set-CcApplianceDirectory. 
  
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
  

