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
# <a name="set-cccredential"></a><span data-ttu-id="96b44-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="96b44-103">Set-CcCredential</span></span>
 
<span data-ttu-id="96b44-104">Il cmdlet Set-CcCredential imposta le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="96b44-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="96b44-105">Con Cloud Connector versione 2,0 e successive, questo cmdlet può anche impostare le informazioni sull'account per l'amministratore della macchina virtuale e per l'amministratore del dominio.</span><span class="sxs-lookup"><span data-stu-id="96b44-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="96b44-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="96b44-106">Examples</span></span>
<span data-ttu-id="96b44-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="96b44-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="96b44-108">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="96b44-108">Example 1</span></span>

<span data-ttu-id="96b44-109">L'esempio seguente specifica il nome dell'account e la password per l'amministratore del tenant:</span><span class="sxs-lookup"><span data-stu-id="96b44-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="96b44-110">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="96b44-110">Detailed Description</span></span>
<span data-ttu-id="96b44-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="96b44-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="96b44-112">Il cmdlet Set-CcCredential imposta il nome dell'account e la password per l'amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="96b44-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="96b44-113">Per le versioni precedenti a 2,0, l'amministratore deve essere un amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="96b44-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="96b44-114">Cloud Connector usa questo account per ottenere informazioni di configurazione, impostare i parametri di configurazione e aggiornare lo stato dell'appliance alla configurazione del tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="96b44-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="96b44-115">Con il rilascio 2,0 e versioni successive, puoi anche usare questo cmdlet per aggiornare le password per gli account VmAdmin e DomainAdmin.</span><span class="sxs-lookup"><span data-stu-id="96b44-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="96b44-116">Parametri</span><span class="sxs-lookup"><span data-stu-id="96b44-116">Parameters</span></span>
<span data-ttu-id="96b44-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="96b44-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="96b44-118">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="96b44-118">**Parameter**</span></span>|<span data-ttu-id="96b44-119">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="96b44-119">**Required**</span></span>|<span data-ttu-id="96b44-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="96b44-120">**Type**</span></span>|<span data-ttu-id="96b44-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="96b44-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="96b44-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="96b44-122">AccountType</span></span> <br/> | <span data-ttu-id="96b44-123">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="96b44-123">Required</span></span> <br/> |<span data-ttu-id="96b44-124">System.String</span><span class="sxs-lookup"><span data-stu-id="96b44-124">System.String</span></span>  <br/> | <span data-ttu-id="96b44-125">Il valore del parametro deve essere "TenantAdmin", "VmAdmin" o "DomainAdmin".</span><span class="sxs-lookup"><span data-stu-id="96b44-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="96b44-126">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="96b44-126">Input Types</span></span>
<span data-ttu-id="96b44-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="96b44-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="96b44-128">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="96b44-128">None.</span></span> <span data-ttu-id="96b44-129">Il cmdlet Set-CcCredential non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="96b44-129">The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="96b44-130">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="96b44-130">Return Types</span></span>
<span data-ttu-id="96b44-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="96b44-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="96b44-132">Nessuno</span><span class="sxs-lookup"><span data-stu-id="96b44-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="96b44-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96b44-133">See also</span></span>
<span data-ttu-id="96b44-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="96b44-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="96b44-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="96b44-135">Get-CcCredential</span></span>](get-cccredential.md)
  

