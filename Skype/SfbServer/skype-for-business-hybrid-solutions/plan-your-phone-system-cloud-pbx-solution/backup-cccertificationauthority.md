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
ms.localizationpriority: medium
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Il cmdlet Backup-CcCertificationAuthority esegue il backup del servizio autorità di certificazione Skype for Business Cloud Connector Edition in un file e lo salva nella cartella CA nella directory della condivisione del sito.
ms.openlocfilehash: 4dc67fa9e1b4a9a52b3e447b09d91a74704be690
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675458"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority

Il cmdlet Backup-CcCertificationAuthority esegue il backup del servizio autorità di certificazione Skype for Business Cloud Connector Edition in un file. Il cmdlet lo salva anche nella cartella CA nella directory della condivisione del sito.

```powershell
Backup-CcCertificationAuthority
```

## <a name="parameters"></a>Parametri

Nessuno

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente esegue il backup del servizio autorità di certificazione in un file e lo salva nella cartella CA nella directory della condivisione del sito:

```powershell
Backup-CcCertificationAuthority
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il backup dell'autorità di certificazione può essere utile se si prevede di ridistribuire un'appliance Cloud Connector con lo stesso certificato. Ad esempio:

- Ripristino di emergenza.
- Spostare l'appliance in un nuovo hardware.

Il comando salva la copia del servizio autorità di certificazione Cloud Connector da AD Server a `"<SiteRootDirectory>\CA\SfB CCE Root.p12"`.

## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Backup-CcCertificationAuthority non accetta l'input tramite pipeline.

## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno

## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  