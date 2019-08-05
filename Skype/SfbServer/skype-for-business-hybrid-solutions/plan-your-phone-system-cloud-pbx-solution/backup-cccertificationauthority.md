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
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Il cmdlet Backup-CcCertificationAuthority esegue il backup del servizio dell'autorità di certificazione di Skype for Business Cloud Connector Edition in un file e lo salva nella cartella CA nella directory della condivisione del sito.
ms.openlocfilehash: 463aab2516deec5b47e549aec67bcba6a0a80bc0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194545"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
Il cmdlet Backup-CcCertificationAuthority esegue il backup del servizio dell'autorità di certificazione di Skype for Business Cloud Connector Edition in un file e lo salva nella cartella CA nella directory della condivisione del sito.
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente consente di eseguire il backup del servizio autorità di certificazione in un file e di salvarlo nella cartella CA nella directory della condivisione del sito:
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il backup dell'autorità di certificazione può essere utile se si prevede di ridistribuire un dispositivo Cloud Connector con lo stesso certificato in caso di emergenza o se si vuole trasferire l'accessorio in un nuovo hardware. Il comando Salva la copia del servizio autorità di certificazione Cloud Connector dal server di annunci in "\<SITEROOTDIRECTORY\>\CA\SfB CCE root. p12".
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Backup-CcCertificationAuthority non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

