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
description: Il cmdlet Backup-CcCertificationAuthority consente di eseguire il backup del servizio Skype for Business Cloud Connector Edition autorità di certificazione in un file e di salvarlo nella cartella CA nella directory della condivisione del sito.
ms.openlocfilehash: abf94977abe2a0c3548b549ae0101ae399e124769eaaa9f05aabf203c69656a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282958"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
Il cmdlet Backup-CcCertificationAuthority consente di eseguire il backup del servizio Skype for Business Cloud Connector Edition autorità di certificazione in un file e di salvarlo nella cartella CA nella directory della condivisione del sito.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene illustrato come eseguire il backup del servizio Autorità di certificazione in un file e salvarlo nella cartella CA nella directory della condivisione del sito:
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il backup dell'Autorità di certificazione può essere utile se si prevede di ridistribuire un'appliance Cloud Connector con lo stesso certificato in caso di emergenza o se si desidera spostare l'appliance in un nuovo hardware. Il comando salva la copia del servizio Autorità di certificazione Cloud Connector dal server AD a " \<SiteRootDirectory\> \CA\SfB CCE Root.p12".
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Backup-CcCertificationAuthority non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

