---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Il cmdlet Get-CcSiteLogDirectory mostra la directory corrente in cui sono archiviati i registri a livello di sito Skype for Business Cloud Connector Edition sito.
ms.openlocfilehash: 65d99093f6390eade15e9783bd286bc438ede23d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616362"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
Il cmdlet Get-CcSiteLogDirectory mostra la directory corrente in cui sono archiviati i registri a livello di sito Skype for Business Cloud Connector Edition sito. 
  
Questo cmdlet si applica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene mostrata la cartella corrente in cui sono archiviati i file di registro per il sito Cloud Connector:
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

La cartella predefinita è C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs. È possibile modificare la cartella eseguendo il cmdlet Set-CcSiteDirectory. Non esiste un cmdlet separato che modifica solo il percorso della cartella dei registri senza modificare la directory del sito.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Get-CcSiteLogDirectory non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Il comando restituisce un percorso di file.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

