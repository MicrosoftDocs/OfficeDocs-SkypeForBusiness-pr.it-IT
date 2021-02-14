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
description: Il cmdlet Restore Cc-Credentials ripristina tutte le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824242"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
Il cmdlet Restore Cc-Credentials ripristina tutte le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition. 
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 2.1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Descrizione dettagliata

Il cmdlet Restore-CcCredentials pulisce tutte le credenziali e richiede di immettere nuovamente tutte le credenziali utilizzate per la distribuzione corrente di Skype for Business Cloud Connector.
  
## <a name="parameters"></a>Parametri

None
  
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
  

