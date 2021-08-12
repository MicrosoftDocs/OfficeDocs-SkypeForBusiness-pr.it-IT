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
description: Il cmdlet Get-CcApplianceDirectory consente di recuperare la directory di lavoro nel server host Skype for Business Cloud Connector Edition server host. Tutti i file di distribuzione vengono archiviati in questa directory.
ms.openlocfilehash: 9be21029aaf582ce080b85af87b8d3f02be11ffea3b615f2b003bb6aeb29002d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347591"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
Il cmdlet Get-CcApplianceDirectory consente di recuperare la directory di lavoro nel server host Skype for Business Cloud Connector Edition server host. Tutti i file di distribuzione vengono archiviati in questa directory. 
  
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
  

