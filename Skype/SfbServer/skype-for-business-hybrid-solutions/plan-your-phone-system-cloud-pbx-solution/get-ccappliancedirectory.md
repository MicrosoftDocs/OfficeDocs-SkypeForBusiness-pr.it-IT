---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Il cmdlet Get-CcApplianceDirectory recupera la directory di lavoro nel server host di Skype for Business Cloud Connector Edition. Tutti i file di distribuzione sono archiviati in questa directory.
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800846"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
Il cmdlet Get-CcApplianceDirectory recupera la directory di lavoro nel server host di Skype for Business Cloud Connector Edition. Tutti i file di distribuzione sono archiviati in questa directory. 
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra la cartella corrente in cui sono archiviati i file della configurazione e della macchina virtuale dei componenti del connettore Cloud:
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Get-CcApplianceDirectory Mostra la posizione in cui vengono archiviati tutti i file di configurazione e la macchina virtuale, i registri e i certificati esterni per l'accessorio Cloud Connector.
  
Ogni accessorio Cloud Connector include quattro componenti: Mediation Server, Central Management store, Edge Server e un controller di dominio. La cartella predefinita è C:\Users\%UserProfile%\CloudConnector\ApplianceRoot. Puoi modificare questa cartella usando il cmdlet Set-CCApplianceDirectory.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Get-CCApplianceDirectory non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Il comando restituisce un percorso di file.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

