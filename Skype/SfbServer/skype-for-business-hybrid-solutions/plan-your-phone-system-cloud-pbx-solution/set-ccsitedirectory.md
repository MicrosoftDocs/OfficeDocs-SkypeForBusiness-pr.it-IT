---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Il cmdlet Set-CcSiteDirectory consente di impostare la directory in cui verranno archiviati i file di configurazione Skype for Business Cloud Connector Edition sito. La cartella conterrà il disco rigido virtuale di base e i file di configurazione del connettore cloud.
ms.openlocfilehash: 9642c91e811e62b08f2b0e219b5eaa7b9ac7359fcdb6114c028735851280da59
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286245"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Il cmdlet Set-CcSiteDirectory consente di impostare la directory in cui verranno archiviati i file di configurazione Skype for Business Cloud Connector Edition sito. La cartella conterrà il disco rigido virtuale di base e i file di configurazione del connettore cloud.
  
Questo cmdlet si applica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente la directory radice del sito viene impostata \\ su SiteShare\CloudConnector:
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Per fornire affinità gateway e disponibilità elevata, le appliance Cloud Connector possono essere combinate nei siti. Gli utenti vengono assegnati ai siti anziché alle appliance Cloud Connector. Ogni sito dispone di una cartella condivisa in cui sono archiviati i file di installazione del disco rigido virtuale e del connettore cloud di base. Gli appliance usano questa cartella durante la distribuzione. Questa cartella deve essere condivisa con tutte le altre appliance in un sito Cloud Connector.
  
La cartella predefinita è C:\Users \% userprofile%\CloudConnector\SiteRoot. Il percorso può essere visualizzato utilizzando il cmdlet Get-CcSiteDirectory.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Percorso <br/> | Obbligatorio <br/> | System.String <br/> |Specifica il percorso della cartella in cui verranno archiviati i file del sito di Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Set-CcSiteDirectory non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

