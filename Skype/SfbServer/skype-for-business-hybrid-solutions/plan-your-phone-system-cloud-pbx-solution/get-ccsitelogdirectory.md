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
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Il cmdlet Get-CcSiteLogDirectory Mostra la directory corrente in cui sono archiviati i registri a livello di sito per Skype for Business Cloud Connector Edition.
ms.openlocfilehash: bc47c2ea2d81e70538305daa98f97a35cf3d9e0a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190769"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
Il cmdlet Get-CcSiteLogDirectory Mostra la directory corrente in cui sono archiviati i registri a livello di sito per Skype for Business Cloud Connector Edition. 
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra la cartella corrente in cui sono archiviati i file di log per il sito del connettore Cloud:
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

La cartella predefinita è C:\Users\%UserProfile%\CloudConnector\SiteRoot\Logs. È possibile modificare la cartella eseguendo il cmdlet Set-CcSiteDirectory. Non esiste un cmdlet distinto che modifichi solo il percorso della cartella del log senza modificare la directory del sito.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Get-CcSiteLogDirectory non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Il comando restituisce un percorso di file.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

