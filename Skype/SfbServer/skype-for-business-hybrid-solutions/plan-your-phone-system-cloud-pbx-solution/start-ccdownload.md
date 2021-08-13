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
description: Il cmdlet Start-CcDownload consente di scaricare Skype for Business Cloud Connector Edition bit e il file msi in modo sincrono.
ms.openlocfilehash: 0447c75ac3e6df79a20d2c87b664bfb92cf7124fc7253c839a88fad1b335eaec
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351915"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
Il cmdlet Start-CcDownload consente di scaricare Skype for Business Cloud Connector Edition bit e il file msi in modo sincrono.
  
Con Cloud Connector versione 2.0 e successive, puoi anche specificare il parametro DownloadBitsOnly.
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente i bit del connettore cloud e il file msi vengono scaricati in modo sincrono dal sito di download pubblico del connettore cloud:
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente i bit del connettore cloud e il file msi vengono scaricati in modo sincrono da un sito di download privato:
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Esempio 3

Nel terzo esempio i bit del connettore cloud e il file msi vengono scaricati in modo sincrono da un sito di download privato.
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Se nel sito di download è disponibile una nuova versione, Start-CcDownload scarica e installa il file msi dal sito di download e quindi scarica i bit del connettore cloud in modo sincrono. Se non esiste una nuova versione del file msi, Start-CcDownload solo i bit del connettore cloud. Se i bit del connettore cloud sono già stati scaricati, Start-CcDownload non viene eseguito.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Facoltativo <br/> |System.String  <br/> | URL completo di una versione specifica di Cloud Connector nel sito di download privato. Usa questo parametro con cautela: assicurati di essere a conoscenza della versione di Cloud Connector che stai scaricando. <br/> |
|DownloadBitsOnly  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Ignora il passaggio per scaricare e installare MSI dal sito di download, scarica solo i bit del connettore cloud.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Start-CcDownload non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

Nessuno
  

