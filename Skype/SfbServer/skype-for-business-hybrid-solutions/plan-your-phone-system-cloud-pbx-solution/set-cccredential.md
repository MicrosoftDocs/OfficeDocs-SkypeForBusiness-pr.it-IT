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
ms.localizationpriority: medium
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Il cmdlet Set-CcCredential consente di impostare le credenziali della distribuzione Skype for Business Cloud Connector Edition corrente.
ms.openlocfilehash: fa0d5f69e3263d273fabe17ae74ea46e0af40908
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617662"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Il cmdlet Set-CcCredential consente di impostare le credenziali della distribuzione Skype for Business Cloud Connector Edition corrente. 
  
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

Il cmdlet Set-CcCredential consente di impostare il nome account e la password per l'amministratore tenant. Per le versioni precedenti alla 2.0, questo amministratore deve essere un amministratore globale. Cloud Connector usa questo account per ottenere informazioni di configurazione, impostare i parametri di configurazione e aggiornare lo stato dell'appliance Microsoft 365 o Office 365'organizzazione. Con la versione 2.0 e successive, è anche possibile utilizzare questo cmdlet per aggiornare le password per gli account VmAdmin e DomainAdmin.
  
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

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

