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
# <a name="get-cccredential"></a><span data-ttu-id="73dac-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="73dac-103">Get-CcCredential</span></span>
 
<span data-ttu-id="73dac-104">Il cmdlet Get-CcCredential restituisce le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="73dac-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="73dac-105">Con la versione 2,0 e versioni successive, puoi anche usare il parametro-DisplayPassword per visualizzare le password per TenantAdmin, DomainAdmin e VMAdmin.</span><span class="sxs-lookup"><span data-stu-id="73dac-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="73dac-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="73dac-106">Examples</span></span>
<span data-ttu-id="73dac-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="73dac-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="73dac-108">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="73dac-108">Example 1</span></span>

<span data-ttu-id="73dac-109">L'esempio seguente restituisce le credenziali dell'amministratore del dominio del dominio della macchina virtuale di Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="73dac-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="73dac-110">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="73dac-110">Detailed Description</span></span>
<span data-ttu-id="73dac-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="73dac-111"></span></span>

<span data-ttu-id="73dac-112">Il cmdlet Get-CcCredential restituisce le informazioni sulle credenziali relative al tipo di account specificato.</span><span class="sxs-lookup"><span data-stu-id="73dac-112">The Get-CcCredential cmdlet returns the credential information about the specified account type.</span></span> <span data-ttu-id="73dac-113">Queste credenziali vengono specificate dall'amministratore che esegue i cmdlet Register-CcAppliance e install-CcAppliance durante la distribuzione dell'appliance corrente.</span><span class="sxs-lookup"><span data-stu-id="73dac-113">These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="73dac-114">Il cmdlet Get-CcCredential restituisce un'istanza dell'oggetto System. Management. Automation. PSCredential.</span><span class="sxs-lookup"><span data-stu-id="73dac-114">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span> <span data-ttu-id="73dac-115">La proprietà password dell'oggetto return è System. Security. SecureString.</span><span class="sxs-lookup"><span data-stu-id="73dac-115">The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="73dac-116">Se si vuole ottenere il testo chiaro della password di amministratore del dominio, assicurarsi che la password venga immessa dall'account di accesso corrente nel server host e quindi aprire una console di PowerShell come amministratore ed eseguire lo script seguente:</span><span class="sxs-lookup"><span data-stu-id="73dac-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="73dac-117">Parametri</span><span class="sxs-lookup"><span data-stu-id="73dac-117">Parameters</span></span>
<span data-ttu-id="73dac-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="73dac-118"></span></span>

|<span data-ttu-id="73dac-119">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="73dac-119">**Parameter**</span></span>|<span data-ttu-id="73dac-120">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="73dac-120">**Required**</span></span>|<span data-ttu-id="73dac-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="73dac-121">**Type**</span></span>|<span data-ttu-id="73dac-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="73dac-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="73dac-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="73dac-123">AccountType</span></span> <br/> |<span data-ttu-id="73dac-124">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="73dac-124">Required</span></span>  <br/> | <span data-ttu-id="73dac-125">System.String</span><span class="sxs-lookup"><span data-stu-id="73dac-125">System.String</span></span> <br/> | <span data-ttu-id="73dac-126">Il valore AccountType può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="73dac-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="73dac-127">VmAdmin: amministratore locale delle macchine virtuali di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="73dac-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="73dac-128">DomainAdmin: amministratore di dominio del dominio della macchina virtuale di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="73dac-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="73dac-129">SafeModeAdmin: SafeModeAdmin del controller di dominio della macchina virtuale di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="73dac-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="73dac-130">ExternalCert: account del certificato esterno installato nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="73dac-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="73dac-131">TenantAdmin: amministratore del tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="73dac-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="73dac-132">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="73dac-132">Input Types</span></span>
<span data-ttu-id="73dac-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="73dac-133"></span></span>

<span data-ttu-id="73dac-134">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="73dac-134">None.</span></span> <span data-ttu-id="73dac-135">Il cmdlet Get-CcCredential non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="73dac-135">The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="73dac-136">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="73dac-136">Return Types</span></span>
<span data-ttu-id="73dac-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="73dac-137"></span></span>

<span data-ttu-id="73dac-138">Il cmdlet Get-CcCredential restituisce un'istanza dell'oggetto System. Management. Automation. PSCredential.</span><span class="sxs-lookup"><span data-stu-id="73dac-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="73dac-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73dac-139">See also</span></span>
<span data-ttu-id="73dac-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="73dac-140"></span></span>

[<span data-ttu-id="73dac-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="73dac-141">Set-CcCredential</span></span>](set-cccredential.md)
  

