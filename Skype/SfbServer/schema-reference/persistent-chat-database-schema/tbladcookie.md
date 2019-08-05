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
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.
ms.openlocfilehash: d75b1dc90d36aa0535fdac62b9e1a7061694cc76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194705"
---
# <a name="tbladcookie"></a><span data-ttu-id="34f6a-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="34f6a-103">tblADCookie</span></span>
 
<span data-ttu-id="34f6a-104">tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.</span><span class="sxs-lookup"><span data-stu-id="34f6a-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="34f6a-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="34f6a-105">**Columns**</span></span>

|<span data-ttu-id="34f6a-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="34f6a-106">**Column**</span></span>|<span data-ttu-id="34f6a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="34f6a-107">**Type**</span></span>|<span data-ttu-id="34f6a-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="34f6a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34f6a-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="34f6a-109">prinGuid</span></span>  <br/> |<span data-ttu-id="34f6a-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="34f6a-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="34f6a-111">GUID principale del dominio da monitorare.</span><span class="sxs-lookup"><span data-stu-id="34f6a-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="34f6a-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="34f6a-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="34f6a-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="34f6a-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="34f6a-114">Nome di dominio completo (FQDN) del controller di dominio corrente usato per la sincronizzazione dei servizi di dominio Active Directory. Ha un valore informativo.</span><span class="sxs-lookup"><span data-stu-id="34f6a-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="34f6a-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="34f6a-115">adcContent</span></span>  <br/> |<span data-ttu-id="34f6a-116">immagine (binario)</span><span class="sxs-lookup"><span data-stu-id="34f6a-116">image (binary)</span></span>  <br/> |<span data-ttu-id="34f6a-117">Cookie di sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34f6a-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="34f6a-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="34f6a-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="34f6a-119">DateTime</span><span class="sxs-lookup"><span data-stu-id="34f6a-119">datetime</span></span>  <br/> |<span data-ttu-id="34f6a-120">Indicatore di data e ora con il tempo di aggiornamento delle righe.</span><span class="sxs-lookup"><span data-stu-id="34f6a-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="34f6a-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="34f6a-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="34f6a-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="34f6a-122">datetime</span></span>  <br/> |<span data-ttu-id="34f6a-123">Ora fino a quando la riga non viene bloccata per le modifiche.</span><span class="sxs-lookup"><span data-stu-id="34f6a-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="34f6a-124">Questo fa parte di un meccanismo di blocco software che garantisce che solo uno dei servizi di chat esegue la sincronizzazione di Active Directory alla volta.</span><span class="sxs-lookup"><span data-stu-id="34f6a-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="34f6a-125">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="34f6a-125">**Keys**</span></span>

|<span data-ttu-id="34f6a-126">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="34f6a-126">**Column(s)**</span></span>|<span data-ttu-id="34f6a-127">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="34f6a-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="34f6a-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="34f6a-128">prinGuid</span></span>  <br/> |<span data-ttu-id="34f6a-129">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="34f6a-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="34f6a-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="34f6a-130">prinGuid</span></span>  <br/> |<span data-ttu-id="34f6a-131">Chiave esterna con ricerca nella tabella Principal. prinGuid.</span><span class="sxs-lookup"><span data-stu-id="34f6a-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

