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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Il cmdlet Get-CcExternalCertificateFilePath restituisce il percorso del file del certificato esterno per la distribuzione di Skype for Business Cloud Connector Edition. L'utente prepara il certificato.
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799906"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
Il cmdlet Get-CcExternalCertificateFilePath restituisce il percorso del file del certificato esterno per la distribuzione di Skype for Business Cloud Connector Edition. L'utente prepara il certificato.
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene mostrato il percorso del certificato per il server perimetrale:
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente viene mostrato il set di certificati per il Mediation Server:
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Durante la distribuzione o durante la modifica della topologia, è necessario specificare il percorso per il certificato del server perimetrale e, facoltativamente, per il Mediation Server. Il certificato per il Mediation Server è obbligatorio se verrà utilizzato TLS tra il gateway (s) e il Mediation Server. Per modificare il percorso, utilizzare il cmdlet Set-CcExternalCertificateFilePath seguente.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Destinazione  <br/> |Facoltativo  <br/> | System.Management.Automation.SwitchParameter <br/> |Tipo di percorso file richiesto. I tipi includono:  <br/> EdgeServer (impostazione predefinita)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Il cmdlet Get-CcExternalCertificateFilePath non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Il comando restituisce un percorso di file.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

