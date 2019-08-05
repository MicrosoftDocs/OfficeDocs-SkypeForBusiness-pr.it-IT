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
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Restituisce la versione di appliance del connettore Cloud. Get-CCVersion può essere usato solo nel computer host di Cloud Connector.
ms.openlocfilehash: b002b4a9f0cae34a2cdd7b8817e86a3e4ec2eb9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190748"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Restituisce la versione di appliance del connettore Cloud. Get-CCVersion può essere usato solo nel computer host di Cloud Connector.
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Descrizione dettagliata

Restituisce la versione dell'appliance Cloud Connector in base agli script di PowerShell installati, i file nella directory appliance e le macchine virtuali distribuite nel server host.
  
## <a name="parameters"></a>Parametri

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Facoltativo  <br/> |System.String  <br/> |Tipo di versione. Il valore del parametro può essere RunningScripts, RunningBits, BackupBits o all. Il valore predefinito è RunningScripts.  <br/> |
   
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra la versione del connettore Cloud dello script attualmente in esecuzione nella console di PowerShell aperta:
  
```
Get-CcVersion
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente mostra la versione del connettore cloud dei file binari attualmente in esecuzione distribuiti nelle macchine virtuali. È possibile visualizzare la versione nei nomi delle macchine virtuali in esecuzione in gestione di Hyper-v:
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Tipi di input
<a name="Examples"> </a>

Nessuno. Il cmdlet Get-CcVersion non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="Examples"> </a>

Nessuno.
  
## <a name="see-also"></a>Vedere anche
<a name="Examples"> </a>

Nessuno.
  

