---
title: Get-CcSiteDirectory
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
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Il cmdlet Get-CcSiteDirectory mostra la directory corrente in cui sono archiviati i file di configurazione a livello di sito. La cartella contiene il disco rigido virtuale di base e i Skype for Business Cloud Connector Edition di installazione. Questa cartella deve essere condivisa con tutte le altre appliance di un sito Cloud Connector.
ms.openlocfilehash: 279afabbb88aab162be8445007772e24d24d06d935130d5f4f27a8755a2fd25c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343190"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
Il cmdlet Get-CcSiteDirectory mostra la directory corrente in cui sono archiviati i file di configurazione a livello di sito. La cartella contiene il disco rigido virtuale di base e i Skype for Business Cloud Connector Edition di installazione. Questa cartella deve essere condivisa con tutte le altre appliance di un sito Cloud Connector.
  
Questo cmdlet si applica a Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra la cartella corrente in cui sono archiviati i file di configurazione e delle macchine virtuali dei componenti del connettore cloud:
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Per fornire affinità gateway e disponibilità elevata, le appliance Cloud Connector possono essere combinate nei siti. Gli utenti vengono assegnati ai siti anziché alle appliance Cloud Connector. Ogni sito dispone di una cartella condivisa in cui sono archiviati i file di installazione del disco rigido virtuale e del connettore cloud di base. Gli appliance usano questa cartella durante la distribuzione. La cartella predefinita è C:\Users \% userprofile%\CloudConnector\SiteRoot. È possibile modificare il percorso utilizzando il cmdlet Set-CcSiteDirectory.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Get-CcSiteDirectory non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Questo comando restituisce un percorso di file.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

