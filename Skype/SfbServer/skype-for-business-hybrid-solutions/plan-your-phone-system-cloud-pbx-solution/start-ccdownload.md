---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Il cmdlet Start-CcDownload Scarica in modo sincrono i bit di Skype for Business Cloud Connector Edition e il file MSI.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824180"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
Il cmdlet Start-CcDownload Scarica in modo sincrono i bit di Skype for Business Cloud Connector Edition e il file MSI.
  
Con Cloud Connector versione 2,0 e successive è anche possibile specificare il parametro DownloadBitsOnly.
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente Scarica i bit del connettore Cloud e il file MSI in modo sincrono dal sito di download pubblico di Cloud Connector:
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente Scarica i bit del connettore Cloud e il file MSI in modo sincrono da un sito di download privato:
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Esempio 3

Il terzo esempio Scarica i bit del connettore Cloud e il file MSI in modo sincrono da un sito di download privato.
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Se nel sito di download è disponibile una nuova versione, Start-CcDownload scaricherà e installerà il file MSI dal sito di download e quindi scaricherà i bit del connettore Cloud in modo sincrono. Se non è disponibile una nuova versione del file MSI, Start-CcDownload scaricherà solo i bit del connettore Cloud. Se i bit del connettore Cloud sono già scaricati, Start-CcDownload non viene eseguito.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Facoltativo <br/> |System.String  <br/> | URL completo di una versione specifica di Cloud Connector nel sito di download privato. Usa questo parametro con cautela, assicurati di essere a conoscenza della versione di Cloud Connector che stai scaricando. <br/> |
|DownloadBitsOnly  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Ignorare il passaggio per scaricare e installare MSI dal sito di download, scaricare solo i bit del connettore Cloud.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Start-CcDownload non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

Nessuno
  

