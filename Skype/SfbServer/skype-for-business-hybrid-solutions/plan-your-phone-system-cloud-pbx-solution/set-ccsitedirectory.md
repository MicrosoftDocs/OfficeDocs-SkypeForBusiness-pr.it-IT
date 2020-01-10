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
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Il cmdlet Set-CcSiteDirectory imposta la directory in cui verranno archiviati i file di configurazione a livello di sito per Skype for Business Cloud Connector Edition. La cartella conterrà i file di configurazione del disco rigido virtuale e del connettore Cloud di base.
ms.openlocfilehash: d0cc8d2a66adb831ea2d85381902eb9d3df7ba6a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003196"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Il cmdlet Set-CcSiteDirectory imposta la directory in cui verranno archiviati i file di configurazione a livello di sito per Skype for Business Cloud Connector Edition. La cartella conterrà i file di configurazione del disco rigido virtuale e del connettore Cloud di base.
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente imposta la directory radice del sito \\su SiteShare\CloudConnector:
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Per consentire l'affinità dei gateway e l'elevata disponibilità, i dispositivi cloud Connector possono essere combinati nei siti. Gli utenti vengono assegnati a siti anziché a dispositivi cloud Connector. Ogni sito include una cartella condivisa in cui sono archiviati i file di installazione del VHD di base e del connettore Cloud. Gli elettrodomestici usano questa cartella durante la distribuzione. Questa cartella deve essere condivisa con tutti gli altri dispositivi in un sito del connettore Cloud.
  
La cartella predefinita è C:\Users\%UserProfile%\CloudConnector\SiteRoot. Il percorso può essere visualizzato usando il cmdlet Get-CcSiteDirectory.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Percorso <br/> | Obbligatorio <br/> | System.String <br/> |Fornisce il percorso della cartella in cui verranno archiviati i file del sito del connettore Cloud.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Set-CcSiteDirectory non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

