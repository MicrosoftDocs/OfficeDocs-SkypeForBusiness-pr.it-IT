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
ms.localizationpriority: medium
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Il cmdlet Get-CcExternalCertificateFilePath restituisce il percorso del file di certificato esterno per la Skype for Business Cloud Connector Edition distribuzione. L'utente prepara il certificato.
ms.openlocfilehash: 9b06958d68d73bc68fc0fda4e681af2e7b9b4f9e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622038"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
Il cmdlet Get-CcExternalCertificateFilePath restituisce il percorso del file di certificato esterno per la Skype for Business Cloud Connector Edition distribuzione. L'utente prepara il certificato.
  
Questo cmdlet si applica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra il percorso del certificato per il server perimetrale:
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente viene illustrato il set di certificati per Mediation Server:
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Durante la distribuzione o durante la modifica della topologia, è necessario specificare il percorso per il certificato del server perimetrale e, facoltativamente, per il Mediation Server. Il certificato per Mediation Server è obbligatorio se verrà utilizzato TLS tra il gateway (s) e il Mediation Server. Per modificare il percorso, utilizzare il cmdlet Set-CcExternalCertificateFilePath.
  
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
  

