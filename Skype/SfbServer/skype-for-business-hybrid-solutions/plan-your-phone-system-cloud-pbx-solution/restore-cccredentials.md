---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Il cmdlet Restore Cc-Credentials consente di ripristinare tutte le credenziali della distribuzione Skype for Business Cloud Connector Edition corrente.
ms.openlocfilehash: 95b93e28bb109c26927a940324edef20479bed8c193efea6923c74058995a5bd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340672"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
Il cmdlet Restore Cc-Credentials consente di ripristinare tutte le credenziali della distribuzione Skype for Business Cloud Connector Edition corrente. 
  
Questo cmdlet si applica Skype for Business Cloud Connector Edition 2.1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Descrizione dettagliata

Il cmdlet Restore-CcCredentials pulisce tutte le credenziali e richiede di immettere di nuovo tutte le credenziali utilizzate per la distribuzione corrente Skype for Business Cloud Connector.
  
## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="input-types"></a>Tipi di input

Nessuna. Il cmdlet Restore-CcCredentials non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti

Nessuna.
  
## <a name="example"></a>Esempio

Nell'esempio seguente vengono ripristinate tutte le credenziali della distribuzione corrente di Cloud Connector:
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Vedere anche

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

