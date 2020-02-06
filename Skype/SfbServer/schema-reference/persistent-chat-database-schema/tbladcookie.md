---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814704"
---
# <a name="tbladcookie"></a><span data-ttu-id="cd7cc-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="cd7cc-103">tblADCookie</span></span>
 
<span data-ttu-id="cd7cc-104">tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="cd7cc-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cd7cc-105">**Columns**</span></span>

|<span data-ttu-id="cd7cc-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="cd7cc-106">**Column**</span></span>|<span data-ttu-id="cd7cc-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cd7cc-107">**Type**</span></span>|<span data-ttu-id="cd7cc-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cd7cc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cd7cc-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="cd7cc-109">prinGuid</span></span>  <br/> |<span data-ttu-id="cd7cc-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="cd7cc-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="cd7cc-111">GUID principale del dominio da monitorare.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="cd7cc-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="cd7cc-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="cd7cc-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="cd7cc-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="cd7cc-114">Nome di dominio completo (FQDN) del controller di dominio corrente usato per la sincronizzazione dei servizi di dominio Active Directory. Ha un valore informativo.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="cd7cc-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="cd7cc-115">adcContent</span></span>  <br/> |<span data-ttu-id="cd7cc-116">immagine (binario)</span><span class="sxs-lookup"><span data-stu-id="cd7cc-116">image (binary)</span></span>  <br/> |<span data-ttu-id="cd7cc-117">Cookie di sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="cd7cc-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="cd7cc-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="cd7cc-119">DateTime</span><span class="sxs-lookup"><span data-stu-id="cd7cc-119">datetime</span></span>  <br/> |<span data-ttu-id="cd7cc-120">Indicatore di data e ora con il tempo di aggiornamento delle righe.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="cd7cc-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="cd7cc-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="cd7cc-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="cd7cc-122">datetime</span></span>  <br/> |<span data-ttu-id="cd7cc-123">Ora fino a quando la riga non viene bloccata per le modifiche.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="cd7cc-124">Questo fa parte di un meccanismo di blocco software che garantisce che solo uno dei servizi di chat esegue la sincronizzazione di Active Directory alla volta.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="cd7cc-125">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="cd7cc-125">**Keys**</span></span>

|<span data-ttu-id="cd7cc-126">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cd7cc-126">**Column(s)**</span></span>|<span data-ttu-id="cd7cc-127">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cd7cc-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cd7cc-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="cd7cc-128">prinGuid</span></span>  <br/> |<span data-ttu-id="cd7cc-129">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="cd7cc-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="cd7cc-130">prinGuid</span></span>  <br/> |<span data-ttu-id="cd7cc-131">Chiave esterna con ricerca nella tabella Principal. prinGuid.</span><span class="sxs-lookup"><span data-stu-id="cd7cc-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

