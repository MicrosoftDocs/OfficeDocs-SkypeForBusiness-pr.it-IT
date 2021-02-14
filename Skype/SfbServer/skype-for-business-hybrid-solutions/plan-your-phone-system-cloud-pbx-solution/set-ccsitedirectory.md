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
description: Il cmdlet Set-CcSiteDirectory imposta la directory in cui verranno archiviati i file di configurazione a livello di sito per Skype for Business Cloud Connector Edition. La cartella conterrà il disco rigido virtuale di base e i file di configurazione del connettore cloud.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824190"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Il cmdlet Set-CcSiteDirectory imposta la directory in cui verranno archiviati i file di configurazione a livello di sito per Skype for Business Cloud Connector Edition. La cartella conterrà il disco rigido virtuale di base e i file di configurazione del connettore cloud.
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
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

Per fornire affinità gateway e disponibilità elevata, le appliance Cloud Connector possono essere combinate nei siti. Gli utenti vengono assegnati ai siti anziché alle appliance cloud connector. Ogni sito dispone di una cartella condivisa in cui sono archiviati i file di installazione del disco rigido virtuale e del connettore cloud di base. Gli appliance usano questa cartella durante la distribuzione. Questa cartella deve essere condivisa con tutte le altre appliance in un sito Cloud Connector.
  
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

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

