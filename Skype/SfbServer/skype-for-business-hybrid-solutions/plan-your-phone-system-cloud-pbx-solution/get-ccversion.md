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
ms.openlocfilehash: a7d50bbcd01dc80fe3e2202286c1adc1b5d5f9bd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003346"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Restituisce la versione di appliance del connettore Cloud. Get-CCVersion può essere usato solo nel computer host di Cloud Connector.
  
```powershell
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
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente mostra la versione del connettore cloud dei file binari attualmente in esecuzione distribuiti nelle macchine virtuali. È possibile visualizzare la versione nei nomi delle macchine virtuali in esecuzione in gestione di Hyper-v:
  
```powershell
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
  

