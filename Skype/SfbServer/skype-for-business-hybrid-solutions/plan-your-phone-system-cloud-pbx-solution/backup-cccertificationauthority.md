---
title: Backup-CcCertificationAuthority
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
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Il cmdlet Backup-CcCertificationAuthority consente di eseguire il backup del servizio Autorità di certificazione Skype for Business Cloud Connector Edition in un file e di salvarlo nella cartella CA nella directory della condivisione del sito.
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803806"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
Il cmdlet Backup-CcCertificationAuthority consente di eseguire il backup del servizio Autorità di certificazione Skype for Business Cloud Connector Edition in un file e di salvarlo nella cartella CA nella directory della condivisione del sito.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Parametri

None
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene illustrato come eseguire il backup del servizio Autorità di certificazione in un file e salvarlo nella cartella ca nella directory della condivisione del sito:
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il backup dell'Autorità di certificazione può essere utile se si prevede di ridistribuire un'applicazione Cloud Connector con lo stesso certificato in caso di emergenza o se si desidera spostare l'applicazione in un nuovo hardware. Il comando salva la copia del servizio Autorità di certificazione Cloud Connector dal server AD in " \< SiteRootDirectory \> \CA\SfB CCE Root.p12".
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Backup-CcCertificationAuthority non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

