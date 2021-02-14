---
title: Set-CcExternalCertificateFilePath
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
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Il Set-CcExternalCertificateFilePath cmdlet consente di specificare il percorso in cui è archiviato il certificato per il Mediation Server o il server perimetrale.
ms.openlocfilehash: 9216b82626da7160d6e1bfa8d611757321a2683a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824200"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
Il Set-CcExternalCertificateFilePath cmdlet consente di specificare il percorso in cui è archiviato il certificato per il Mediation Server o il server perimetrale.
  
Questo certificato è necessario durante la distribuzione o quando si aggiungono nuove appliance di Skype for Business Cloud Connector Edition. Il comando consente inoltre di importare un nuovo certificato per il Mediation Server dopo la distribuzione.
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene impostato il percorso del certificato per il server perimetrale:
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente viene impostato il percorso del certificato per il Mediation Server:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>Esempio 3

Nell'esempio seguente viene aggiornato il certificato per il Mediation Server:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Durante la distribuzione o durante la modifica della topologia, è necessario specificare il percorso per il certificato del server perimetrale e, facoltativamente, per il certificato mediation server. 
  
Il certificato per il Mediation Server è obbligatorio se verrà utilizzato TLS tra il gateway (s) e il Mediation Server. Quando si distribuisce un'applicazione Cloud Connector e si desidera distribuire TLS, è possibile specificare solo il percorso del certificato che verrà distribuito nel Mediation Server. Tuttavia, se si desidera aggiornare il certificato mediation in un'applicazione già distribuita, è necessario specificare il percorso e il parametro -Import. Per visualizzare il percorso, utilizzare il cmdlet Get-CCExternalCertificateFilePath seguente.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Destinazione <br/> | Obbligatorio <br/> |System.String  <br/> |Tipo di percorso file richiesto. I tipi includono:  <br/> EdgeServer (impostazione predefinita)  <br/> MediationServer  <br/> |
|Importazione  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Indica che il certificato deve essere importato nel Mediation Server. Questo parametro non è necessario se si distribuisce un'applicazione per la prima volta. Il parametro è obbligatorio se si desidera modificare il certificato esistente in una versione già distribuita.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Il cmdlet Set-CcExternalCertificateFilePath non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

