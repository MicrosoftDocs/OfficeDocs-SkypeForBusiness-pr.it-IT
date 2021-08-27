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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Il cmdlet Get-CcCredential restituisce le credenziali della distribuzione Skype for Business Cloud Connector Edition corrente.
ms.openlocfilehash: 158f6e35f667410a0070e2f7030932bd6fc35ade
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596360"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
Il cmdlet Get-CcCredential restituisce le credenziali della distribuzione Skype for Business Cloud Connector Edition corrente. 
  
Con la versione 2.0 e successive, è anche possibile utilizzare il parametro -DisplayPassword per visualizzare le password per TenantAdmin, DomainAdmin e VMAdmin.
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente vengono restituite le credenziali dell'amministratore di dominio del dominio della macchina virtuale Cloud Connector:
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Get-CcCredential restituisce le informazioni sulle credenziali relative al tipo di account specificato. Queste credenziali vengono specificate dall'amministratore che esegue i cmdlet Register-CcAppliance e Install-CcAppliance durante la distribuzione dell'appliance corrente. 
  
Il cmdlet Get-CcCredential restituisce un'istanza dell'oggetto System.Management.Automation.PSCredential. La proprietà password dell'oggetto restituito è System.Security.SecureString.
  
Se si desidera ottenere il testo non crittografato della password dell'amministratore di dominio, assicurarsi che la password sia immessa dall'account di accesso corrente nel server host, quindi aprire una console di PowerShell come amministratore ed eseguire lo script seguente:
  
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

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |Obbligatorio  <br/> | System.String <br/> | Il valore accountType può essere uno dei seguenti: <br/>  VmAdmin: l'amministratore locale delle macchine virtuali Cloud Connector. <br/>  DomainAdmin: amministratore di dominio del dominio della macchina virtuale Cloud Connector. <br/>  SafeModeAdmin: SafeModeAdmin del controller di dominio della macchina virtuale Cloud Connector. <br/>  ExternalCert: account del certificato esterno installato nel server perimetrale. <br/>  TenantAdmin: amministratore del tenant di O365. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Get-CcCredential non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Il cmdlet Get-CcCredential restituisce un'istanza dell'oggetto System.Management.Automation.PSCredential.
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

