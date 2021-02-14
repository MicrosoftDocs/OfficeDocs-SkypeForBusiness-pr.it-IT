---
title: tblADCookie
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.
ms.openlocfilehash: 78a477399da811e674bb5a4493e61100acdd4782
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814756"
---
# <a name="tbladcookie"></a><span data-ttu-id="8664b-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="8664b-103">tblADCookie</span></span>
 
<span data-ttu-id="8664b-104">tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.</span><span class="sxs-lookup"><span data-stu-id="8664b-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="8664b-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8664b-105">**Columns**</span></span>

|<span data-ttu-id="8664b-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="8664b-106">**Column**</span></span>|<span data-ttu-id="8664b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8664b-107">**Type**</span></span>|<span data-ttu-id="8664b-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8664b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8664b-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="8664b-109">prinGuid</span></span>  <br/> |<span data-ttu-id="8664b-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="8664b-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="8664b-111">GUID entità del dominio da monitorare.</span><span class="sxs-lookup"><span data-stu-id="8664b-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="8664b-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="8664b-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="8664b-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="8664b-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="8664b-114">Nome di dominio completo (FQDN) del controller di dominio corrente utilizzato per la sincronizzazione di Servizi di dominio Active Directory. Ha un valore informativo.</span><span class="sxs-lookup"><span data-stu-id="8664b-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="8664b-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="8664b-115">adcContent</span></span>  <br/> |<span data-ttu-id="8664b-116">image (binary)</span><span class="sxs-lookup"><span data-stu-id="8664b-116">image (binary)</span></span>  <br/> |<span data-ttu-id="8664b-117">Cookie di sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8664b-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="8664b-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="8664b-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="8664b-119">datetime</span><span class="sxs-lookup"><span data-stu-id="8664b-119">datetime</span></span>  <br/> |<span data-ttu-id="8664b-120">Timestamp con data e ora di aggiornamento della riga</span><span class="sxs-lookup"><span data-stu-id="8664b-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="8664b-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="8664b-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="8664b-122">datetime</span><span class="sxs-lookup"><span data-stu-id="8664b-122">datetime</span></span>  <br/> |<span data-ttu-id="8664b-p101">Data e ora fino a cui la riga è bloccata in modo da impedire eventuali modifiche. Fa parte di un meccanismo di blocco software che garantisce che un solo servizio chat alla volta esegua la sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8664b-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="8664b-125">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="8664b-125">**Keys**</span></span>

|<span data-ttu-id="8664b-126">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8664b-126">**Column(s)**</span></span>|<span data-ttu-id="8664b-127">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8664b-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8664b-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="8664b-128">prinGuid</span></span>  <br/> |<span data-ttu-id="8664b-129">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="8664b-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="8664b-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="8664b-130">prinGuid</span></span>  <br/> |<span data-ttu-id="8664b-131">Chiave esterna con ricerca nella tabella Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="8664b-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

