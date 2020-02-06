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
description: Il cmdlet Set-CcCredential imposta le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: b7620a6d76415e4e2a49ea9bd628d1e1cba7f4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824210"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Il cmdlet Set-CcCredential imposta le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition. 
  
Con Cloud Connector versione 2,0 e successive, questo cmdlet può anche impostare le informazioni sull'account per l'amministratore della macchina virtuale e per l'amministratore del dominio.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente specifica il nome dell'account e la password per l'amministratore del tenant:
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Set-CcCredential imposta il nome dell'account e la password per l'amministratore del tenant. Per le versioni precedenti a 2,0, l'amministratore deve essere un amministratore globale di Office 365. Cloud Connector usa questo account per ottenere informazioni di configurazione, impostare i parametri di configurazione e aggiornare lo stato dell'appliance alla configurazione del tenant di Office 365. Con il rilascio 2,0 e versioni successive, puoi anche usare questo cmdlet per aggiornare le password per gli account VmAdmin e DomainAdmin.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Obbligatorio <br/> |System.String  <br/> | Il valore del parametro deve essere "TenantAdmin", "VmAdmin" o "DomainAdmin". <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Set-CcCredential non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

