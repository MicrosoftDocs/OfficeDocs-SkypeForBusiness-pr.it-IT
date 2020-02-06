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
description: Il cmdlet Get-CcSiteDirectory Mostra la directory corrente in cui sono archiviati i file di configurazione a livello di sito. La cartella contiene i file di installazione VHD di base e Skype for Business Cloud Connector Edition. Questa cartella deve essere condivisa con tutti gli altri dispositivi di un sito del connettore Cloud.
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799866"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
Il cmdlet Get-CcSiteDirectory Mostra la directory corrente in cui sono archiviati i file di configurazione a livello di sito. La cartella contiene i file di installazione VHD di base e Skype for Business Cloud Connector Edition. Questa cartella deve essere condivisa con tutti gli altri dispositivi di un sito del connettore Cloud.
  
Questo cmdlet si applica a Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra la cartella corrente in cui sono archiviati i file di configurazione e le macchine virtuali dei componenti del connettore Cloud:
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Per consentire l'affinità dei gateway e l'elevata disponibilità, i dispositivi cloud Connector possono essere combinati nei siti. Gli utenti vengono assegnati a siti anziché a dispositivi cloud Connector. Ogni sito include una cartella condivisa in cui sono archiviati i file di installazione del VHD di base e del connettore Cloud. Gli elettrodomestici usano questa cartella durante la distribuzione. La cartella predefinita è C:\Users\%UserProfile%\CloudConnector\SiteRoot. Puoi modificare il percorso usando il cmdlet Set-CcSiteDirectory.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Get-CcSiteDirectory non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Questo comando restituisce un percorso di file.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

