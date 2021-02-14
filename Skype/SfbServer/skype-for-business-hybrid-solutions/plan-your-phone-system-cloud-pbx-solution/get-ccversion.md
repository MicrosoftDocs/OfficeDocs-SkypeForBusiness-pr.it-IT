---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Restituisce la versione dell'applicazione Cloud Connector. Get-CCVersion può essere usato solo nel computer host di Cloud Connector.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799846"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Restituisce la versione dell'applicazione Cloud Connector. Get-CCVersion può essere usato solo nel computer host di Cloud Connector.
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Descrizione dettagliata

Restituisce la versione dell'applicazione Cloud Connector in base agli script di PowerShell installati, ai file nella directory appliance e alle macchine virtuali distribuite nel server host.
  
## <a name="parameters"></a>Parametri

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Facoltativo  <br/> |System.String  <br/> |Tipo di versione. Il valore del parametro può essere RunningScripts, RunningBits, BackupBits o All. Il valore predefinito è RunningScripts.  <br/> |
   
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra la versione Cloud Connector dello script attualmente in esecuzione nella console di PowerShell aperta:
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente mostra la versione Cloud Connector dei file binari attualmente in esecuzione distribuiti alle macchine virtuali. È possibile visualizzare la versione nei nomi delle macchine virtuali in esecuzione nella console di gestione di Hyper-v:
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Tipi di input
<a name="Examples"> </a>

Nessuna. Il cmdlet Get-CcVersion non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="Examples"> </a>

Nessuna.
  
## <a name="see-also"></a>Vedere anche
<a name="Examples"> </a>

Nessuna.
  

