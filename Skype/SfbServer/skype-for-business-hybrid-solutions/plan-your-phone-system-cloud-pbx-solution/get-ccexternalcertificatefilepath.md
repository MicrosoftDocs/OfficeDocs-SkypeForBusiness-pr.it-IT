---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Il cmdlet Get-CcExternalCertificateFilePath restituisce il percorso del file del certificato esterno per la distribuzione di Skype for Business Cloud Connector Edition. L'utente prepara questo certificato.
ms.openlocfilehash: ed725814380741aade73166d01025650dfa78538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190778"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
Il cmdlet Get-CcExternalCertificateFilePath restituisce il percorso del file del certificato esterno per la distribuzione di Skype for Business Cloud Connector Edition. L'utente prepara questo certificato.
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra il percorso del certificato per il server perimetrale:
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente mostra il set di certificati per il Mediation Server:
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Durante la distribuzione o quando si modifica la topologia, è necessario specificare il percorso per il certificato Edge Server e, facoltativamente, per il Mediation Server. Il certificato per il Mediation Server è obbligatorio se TLS verrà usato tra i gateway e il Mediation Server. Per cambiare il percorso, usare il cmdlet Set-CcExternalCertificateFilePath.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Destinazione  <br/> |Facoltativo  <br/> | System.Management.Automation.SwitchParameter <br/> |Tipo di percorso di file richiesto. I tipi includono:  <br/> EdgeServer (impostazione predefinita)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Il cmdlet Get-CcExternalCertificateFilePath non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Il comando restituisce un percorso di file.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

