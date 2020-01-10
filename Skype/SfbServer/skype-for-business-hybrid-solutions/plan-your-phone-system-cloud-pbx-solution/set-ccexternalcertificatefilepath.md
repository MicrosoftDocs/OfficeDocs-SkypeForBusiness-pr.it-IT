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
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Il cmdlet Set-CcExternalCertificateFilePath specifica il percorso in cui è archiviato il certificato per il server di mediazione o il server perimetrale.
ms.openlocfilehash: e71a50f09a4ce3d085746c30f7591e8a07eb38de
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003206"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
Il cmdlet Set-CcExternalCertificateFilePath specifica il percorso in cui è archiviato il certificato per il server di mediazione o il server perimetrale.
  
Questo certificato è necessario durante la distribuzione o quando si aggiungono nuovi elettrodomestici di Skype for Business Cloud Connector Edition. Il comando consente inoltre di importare un nuovo certificato per il Mediation Server dopo la distribuzione.
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente imposta il percorso del certificato per il server perimetrale:
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente imposta il percorso del certificato per il Mediation Server:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>Esempio 3

Nell'esempio successivo viene aggiornato il certificato per il Mediation Server:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Durante la distribuzione o durante la modifica della topologia, è necessario specificare il percorso per il certificato del server perimetrale e, facoltativamente, il certificato di Mediation Server. 
  
Il certificato per il Mediation Server è obbligatorio se TLS verrà usato tra i gateway e il Mediation Server. Quando si distribuisce un'appliance di Cloud Connector e si vuole distribuire TLS, è possibile specificare solo il percorso del certificato che verrà distribuito nel Mediation Server. Tuttavia, se si vuole aggiornare il certificato di mediazione in un'appliance già distribuita, è necessario specificare il percorso e il parametro-Import. Per visualizzare il percorso, usare il cmdlet Get-CCExternalCertificateFilePath.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Destinazione <br/> | Obbligatorio <br/> |System.String  <br/> |Tipo di percorso di file richiesto. I tipi includono:  <br/> EdgeServer (impostazione predefinita)  <br/> MediationServer  <br/> |
|Importazione  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Indica che il certificato deve essere importato nel Mediation Server. Questo parametro non è necessario se si distribuisce un dispositivo per la prima volta. Il parametro è obbligatorio se si vuole modificare il certificato esistente in una versione già distribuita.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Il cmdlet Set-CcExternalCertificateFilePath non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

