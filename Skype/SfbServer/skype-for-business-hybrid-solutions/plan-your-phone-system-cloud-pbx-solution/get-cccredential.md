---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Il cmdlet Get-CcCredential restituisce le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 46c51783361ad6613d1e2971600969b324f0f350
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003386"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
Il cmdlet Get-CcCredential restituisce le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition. 
  
Con la versione 2,0 e versioni successive, puoi anche usare il parametro-DisplayPassword per visualizzare le password per TenantAdmin, DomainAdmin e VMAdmin.
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente restituisce le credenziali dell'amministratore del dominio del dominio della macchina virtuale di Cloud Connector:
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Get-CcCredential restituisce le informazioni sulle credenziali relative al tipo di account specificato. Queste credenziali vengono specificate dall'amministratore che esegue i cmdlet Register-CcAppliance e install-CcAppliance durante la distribuzione dell'appliance corrente. 
  
Il cmdlet Get-CcCredential restituisce un'istanza dell'oggetto System. Management. Automation. PSCredential. La proprietà password dell'oggetto return è System. Security. SecureString.
  
Se si vuole ottenere il testo chiaro della password di amministratore del dominio, assicurarsi che la password venga immessa dall'account di accesso corrente nel server host e quindi aprire una console di PowerShell come amministratore ed eseguire lo script seguente:
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |Obbligatorio  <br/> | System.String <br/> | Il valore AccountType può essere uno dei seguenti: <br/>  VmAdmin: amministratore locale delle macchine virtuali di Cloud Connector. <br/>  DomainAdmin: amministratore di dominio del dominio della macchina virtuale di Cloud Connector. <br/>  SafeModeAdmin: SafeModeAdmin del controller di dominio della macchina virtuale di Cloud Connector. <br/>  ExternalCert: account del certificato esterno installato nel server perimetrale. <br/>  TenantAdmin: amministratore del tenant di Office 365. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Get-CcCredential non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Il cmdlet Get-CcCredential restituisce un'istanza dell'oggetto System. Management. Automation. PSCredential.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

