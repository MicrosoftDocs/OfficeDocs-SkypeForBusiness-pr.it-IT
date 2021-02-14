---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Il Set-CcCredential cmdlet imposta le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221570"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Il Set-CcCredential cmdlet imposta le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition. 
  
Con Cloud Connector versione 2.0 e successive, questo cmdlet può anche impostare le informazioni sull'account per l'amministratore della macchina virtuale e per l'amministratore di dominio.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente vengono specificati il nome account e la password per l'amministratore tenant:
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il Set-CcCredential cmdlet imposta il nome account e la password per l'amministratore tenant. Per le versioni precedenti alla 2.0, questo amministratore deve essere un amministratore globale. Cloud Connector usa questo account per ottenere informazioni sulla configurazione, impostare i parametri di configurazione e aggiornare lo stato dell'applicazione alla configurazione dell'organizzazione di Microsoft 365 o Office 365. Con la versione 2.0 e successive, è anche possibile utilizzare questo cmdlet per aggiornare le password per gli account VmAdmin e DomainAdmin.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Obbligatorio <br/> |System.String  <br/> | Il valore del parametro deve essere "TenantAdmin", "VmAdmin" o "DomainAdmin". <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Set-CcCredential non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

