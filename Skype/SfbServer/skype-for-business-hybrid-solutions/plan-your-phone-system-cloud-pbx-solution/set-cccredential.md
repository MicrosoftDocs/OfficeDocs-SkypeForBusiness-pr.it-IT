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
description: Il cmdlet Set-CcCredential imposta le credenziali della distribuzione di Skype for Business Cloud Connector Edition corrente.
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221570"
---
# <a name="set-cccredential"></a><span data-ttu-id="41a0f-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="41a0f-103">Set-CcCredential</span></span>
 
<span data-ttu-id="41a0f-104">Il cmdlet Set-CcCredential imposta le credenziali della distribuzione di Skype for Business Cloud Connector Edition corrente.</span><span class="sxs-lookup"><span data-stu-id="41a0f-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="41a0f-105">Con il connettore Cloud versione 2,0 e versioni successive, questo cmdlet può anche impostare le informazioni sull'account per l'amministratore della macchina virtuale e per l'amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="41a0f-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="41a0f-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="41a0f-106">Examples</span></span>
<span data-ttu-id="41a0f-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="41a0f-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="41a0f-108">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="41a0f-108">Example 1</span></span>

<span data-ttu-id="41a0f-109">Nell'esempio seguente viene specificato il nome e la password dell'account per l'amministratore tenant:</span><span class="sxs-lookup"><span data-stu-id="41a0f-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="41a0f-110">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="41a0f-110">Detailed Description</span></span>
<span data-ttu-id="41a0f-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="41a0f-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="41a0f-112">Il cmdlet Set-CcCredential consente di impostare il nome e la password dell'account per l'amministratore tenant.</span><span class="sxs-lookup"><span data-stu-id="41a0f-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="41a0f-113">Per le versioni precedenti all'2,0, questo amministratore deve essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="41a0f-113">For releases prior to 2.0, this administrator must be a Global Administrator.</span></span> <span data-ttu-id="41a0f-114">Il connettore cloud utilizza questo account per ottenere informazioni di configurazione, impostare parametri di configurazione e aggiornare lo stato dell'accessorio alla configurazione dell'organizzazione di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="41a0f-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="41a0f-115">Con la versione 2,0 e versioni successive, è anche possibile utilizzare questo cmdlet per aggiornare le password per gli account VmAdmin e DomainAdmin.</span><span class="sxs-lookup"><span data-stu-id="41a0f-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="41a0f-116">Parametri</span><span class="sxs-lookup"><span data-stu-id="41a0f-116">Parameters</span></span>
<span data-ttu-id="41a0f-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="41a0f-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="41a0f-118">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="41a0f-118">**Parameter**</span></span>|<span data-ttu-id="41a0f-119">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="41a0f-119">**Required**</span></span>|<span data-ttu-id="41a0f-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="41a0f-120">**Type**</span></span>|<span data-ttu-id="41a0f-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="41a0f-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="41a0f-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="41a0f-122">AccountType</span></span> <br/> | <span data-ttu-id="41a0f-123">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="41a0f-123">Required</span></span> <br/> |<span data-ttu-id="41a0f-124">System. String</span><span class="sxs-lookup"><span data-stu-id="41a0f-124">System.String</span></span>  <br/> | <span data-ttu-id="41a0f-125">Il valore del parametro deve essere "TenantAdmin", "VmAdmin" o "DomainAdmin".</span><span class="sxs-lookup"><span data-stu-id="41a0f-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="41a0f-126">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="41a0f-126">Input Types</span></span>
<span data-ttu-id="41a0f-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="41a0f-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="41a0f-128">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="41a0f-128">None.</span></span> <span data-ttu-id="41a0f-129">Il cmdlet Set-CcCredential non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="41a0f-129">The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="41a0f-130">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="41a0f-130">Return Types</span></span>
<span data-ttu-id="41a0f-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="41a0f-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="41a0f-132">Nessuno</span><span class="sxs-lookup"><span data-stu-id="41a0f-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41a0f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41a0f-133">See also</span></span>
<span data-ttu-id="41a0f-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="41a0f-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="41a0f-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="41a0f-135">Get-CcCredential</span></span>](get-cccredential.md)
  

