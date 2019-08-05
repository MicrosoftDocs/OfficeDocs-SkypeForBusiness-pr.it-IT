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
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Il cmdlet Set-CcCredential imposta le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 59c058f8965bbc6fc011806f383c547c1e7b6cd1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190646"
---
# <a name="set-cccredential"></a><span data-ttu-id="00a6d-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="00a6d-103">Set-CcCredential</span></span>
 
<span data-ttu-id="00a6d-104">Il cmdlet Set-CcCredential imposta le credenziali della distribuzione corrente di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="00a6d-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="00a6d-105">Con Cloud Connector versione 2,0 e successive, questo cmdlet può anche impostare le informazioni sull'account per l'amministratore della macchina virtuale e per l'amministratore del dominio.</span><span class="sxs-lookup"><span data-stu-id="00a6d-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="00a6d-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="00a6d-106">Examples</span></span>
<span data-ttu-id="00a6d-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="00a6d-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="00a6d-108">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="00a6d-108">Example 1</span></span>

<span data-ttu-id="00a6d-109">L'esempio seguente specifica il nome dell'account e la password per l'amministratore del tenant:</span><span class="sxs-lookup"><span data-stu-id="00a6d-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="00a6d-110">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="00a6d-110">Detailed Description</span></span>
<span data-ttu-id="00a6d-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="00a6d-111"></span></span>

<span data-ttu-id="00a6d-112">Il cmdlet Set-CcCredential imposta il nome dell'account e la password per l'amministratore del tenant.</span><span class="sxs-lookup"><span data-stu-id="00a6d-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="00a6d-113">Per le versioni precedenti a 2,0, l'amministratore deve essere un amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="00a6d-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="00a6d-114">Cloud Connector usa questo account per ottenere informazioni di configurazione, impostare i parametri di configurazione e aggiornare lo stato dell'appliance alla configurazione del tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="00a6d-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="00a6d-115">Con il rilascio 2,0 e versioni successive, puoi anche usare questo cmdlet per aggiornare le password per gli account VmAdmin e DomainAdmin.</span><span class="sxs-lookup"><span data-stu-id="00a6d-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="00a6d-116">Parametri</span><span class="sxs-lookup"><span data-stu-id="00a6d-116">Parameters</span></span>
<span data-ttu-id="00a6d-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="00a6d-117"></span></span>

|<span data-ttu-id="00a6d-118">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="00a6d-118">**Parameter**</span></span>|<span data-ttu-id="00a6d-119">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="00a6d-119">**Required**</span></span>|<span data-ttu-id="00a6d-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="00a6d-120">**Type**</span></span>|<span data-ttu-id="00a6d-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="00a6d-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="00a6d-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="00a6d-122">AccountType</span></span> <br/> | <span data-ttu-id="00a6d-123">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="00a6d-123">Required</span></span> <br/> |<span data-ttu-id="00a6d-124">System.String</span><span class="sxs-lookup"><span data-stu-id="00a6d-124">System.String</span></span>  <br/> | <span data-ttu-id="00a6d-125">Il valore del parametro deve essere "TenantAdmin", "VmAdmin" o "DomainAdmin".</span><span class="sxs-lookup"><span data-stu-id="00a6d-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="00a6d-126">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="00a6d-126">Input Types</span></span>
<span data-ttu-id="00a6d-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="00a6d-127"></span></span>

<span data-ttu-id="00a6d-128">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="00a6d-128">None.</span></span> <span data-ttu-id="00a6d-129">Il cmdlet Set-CcCredential non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="00a6d-129">The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="00a6d-130">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="00a6d-130">Return Types</span></span>
<span data-ttu-id="00a6d-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="00a6d-131"></span></span>

<span data-ttu-id="00a6d-132">Nessuno</span><span class="sxs-lookup"><span data-stu-id="00a6d-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00a6d-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00a6d-133">See also</span></span>
<span data-ttu-id="00a6d-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="00a6d-134"></span></span>

[<span data-ttu-id="00a6d-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="00a6d-135">Get-CcCredential</span></span>](get-cccredential.md)
  

