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
description: Il Get-CcApplianceDirectory cmdlet recupera la directory di lavoro nel server host Skype for Business Cloud Connector Edition. Tutti i file di distribuzione sono archiviati in questa directory.
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800846"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
Il Get-CcApplianceDirectory cmdlet recupera la directory di lavoro nel server host Skype for Business Cloud Connector Edition. Tutti i file di distribuzione sono archiviati in questa directory. 
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Parametri

None
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra la cartella corrente in cui sono archiviati i file di configurazione e della macchina virtuale dei componenti cloud connector:
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Get-CcApplianceDirectory mostra dove vengono archiviati tutti i file, i registri e i certificati esterni della macchina virtuale e di configurazione per l'applicazione Cloud Connector.
  
Ogni applicazione Cloud Connector dispone di quattro componenti: Mediation Server, Archivio di gestione centrale, Server perimetrale e controller di dominio. La cartella predefinita è C:\Users \% userprofile%\CloudConnector\ApplianceRoot. È possibile modificare questa cartella utilizzando il cmdlet Set-CCApplianceDirectory seguente.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Get-CCApplianceDirectory non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Il comando restituisce un percorso di file.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

