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
ms.localizationpriority: medium
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Il cmdlet Get-CcApplianceDirectory consente di recuperare la directory di lavoro nel server Skype for Business Cloud Connector Edition host. Tutti i file di distribuzione vengono archiviati in questa directory.
ms.openlocfilehash: 9b049b0227f923518ae682415df48afeb044c3c3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599861"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
Il cmdlet Get-CcApplianceDirectory consente di recuperare la directory di lavoro nel server Skype for Business Cloud Connector Edition host. Tutti i file di distribuzione vengono archiviati in questa directory. 
  
Questo cmdlet si applica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra la cartella corrente in cui sono archiviati i file di configurazione e delle macchine virtuali dei componenti del connettore cloud:
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Get-CcApplianceDirectory mostra dove vengono archiviati tutti i file di configurazione e delle macchine virtuali, i registri e i certificati esterni per l'appliance Cloud Connector.
  
Ogni appliance Cloud Connector dispone di quattro componenti: Mediation Server, Archivio di gestione centrale, Server perimetrale e controller di dominio. La cartella predefinita è C:\Users \% userprofile%\CloudConnector\ApplianceRoot. È possibile modificare questa cartella utilizzando il cmdlet Set-CCApplianceDirectory.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Get-CCApplianceDirectory non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Il comando restituisce un percorso di file.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

