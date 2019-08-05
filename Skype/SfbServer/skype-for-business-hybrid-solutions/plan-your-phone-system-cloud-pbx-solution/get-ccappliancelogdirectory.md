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
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Il cmdlet Get-CcApplianceLogDirectory Mostra la directory corrente in cui sono archiviati i registri per un appliance di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 675e89f49c7c1384edc7cfa5944c8aee3f236c79
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190793"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
Il cmdlet Get-CcApplianceLogDirectory Mostra la directory corrente in cui sono archiviati i registri per un appliance di Skype for Business Cloud Connector Edition.
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra la cartella corrente in cui sono archiviati i registri per l'accessorio corrente di Cloud Connector:
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Get-CcApplianceLogDirectory Mostra la directory corrente in cui sono archiviati i registri per un appliance di connettori cloud. La cartella predefinita è C:\Users\%UserProfile%\CloudConnector\ApplianceRoot\Logs. 
  
È possibile modificare la directory usando il cmdlet Set-CcApplianceDirectory. 
  
Nota: non esiste alcun cmdlet che modifichi solo la posizione della cartella del log senza modificare la directory appliance.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Get-CcApplianceLogDirectory non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Questo comando restituisce un percorso di file.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

