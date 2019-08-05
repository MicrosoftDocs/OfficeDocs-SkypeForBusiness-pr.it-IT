---
title: Ripristinare-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Il cmdlet Restore CC-Credentials Ripristina tutte le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: efa1bcda9af6abccd2ced0faf1e772e779a4483f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190655"
---
# <a name="restore-cccredentials"></a>Ripristinare-CcCredentials
 
Il cmdlet Restore CC-Credentials Ripristina tutte le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition. 
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 2,1.
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Descrizione dettagliata

Il cmdlet Restore-CcCredentials pulisce tutte le credenziali e chiede di immettere di nuovo tutte le credenziali usate per la distribuzione del Cloud Connector Skype for business corrente.
  
## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="input-types"></a>Tipi di input

Nessuno. Il cmdlet Restore-CcCredentials non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti

Nessuno.
  
## <a name="example"></a>Esempio

L'esempio seguente ripristina tutte le credenziali della distribuzione di Cloud Connector corrente:
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Vedere anche

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

