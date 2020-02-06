---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contiene gli eventi di conformità che non sono stati ancora elaborati dalla scheda conformità.
ms.openlocfilehash: f09acd44e803c629e45afa18683ac7bc863564a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814664"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="73177-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="73177-103">tblComplianceData</span></span>
 
<span data-ttu-id="73177-104">tblComplianceData contiene gli eventi di conformità che non sono stati ancora elaborati dalla scheda conformità.</span><span class="sxs-lookup"><span data-stu-id="73177-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="73177-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="73177-105">**Columns**</span></span>

|<span data-ttu-id="73177-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="73177-106">**Column**</span></span>|<span data-ttu-id="73177-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="73177-107">**Type**</span></span>|<span data-ttu-id="73177-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="73177-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73177-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="73177-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="73177-110">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="73177-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="73177-111">ID evento.</span><span class="sxs-lookup"><span data-stu-id="73177-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="73177-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="73177-112">entryDate</span></span>  <br/> |<span data-ttu-id="73177-113">smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="73177-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="73177-114">Ora di inserimento (può essere lontano in futuro per cmplType = 9 perché la voce è solo un segnaposto in questo caso).</span><span class="sxs-lookup"><span data-stu-id="73177-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="73177-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="73177-115">cmplType</span></span>  <br/> |<span data-ttu-id="73177-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="73177-116">int, not null</span></span>  <br/> | <span data-ttu-id="73177-117">Tipo di evento di conformità:</span><span class="sxs-lookup"><span data-stu-id="73177-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="73177-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="73177-118">1: Chat</span></span> <br/>  <span data-ttu-id="73177-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="73177-119">2: Backchat</span></span> <br/>  <span data-ttu-id="73177-120">3: download di file</span><span class="sxs-lookup"><span data-stu-id="73177-120">3: File download</span></span> <br/>  <span data-ttu-id="73177-121">4: caricamento di file</span><span class="sxs-lookup"><span data-stu-id="73177-121">4: File upload</span></span> <br/>  <span data-ttu-id="73177-122">9: trasferimento di file provvisorio</span><span class="sxs-lookup"><span data-stu-id="73177-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="73177-123">10: eliminazione della chat (con Sostituisci)</span><span class="sxs-lookup"><span data-stu-id="73177-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="73177-124">11: eliminazione chat</span><span class="sxs-lookup"><span data-stu-id="73177-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="73177-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="73177-125">cmplTime</span></span>  <br/> |<span data-ttu-id="73177-126">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="73177-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="73177-127">Indicatore di data e ora per l'evento.</span><span class="sxs-lookup"><span data-stu-id="73177-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="73177-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="73177-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="73177-129">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="73177-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="73177-130">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="73177-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="73177-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="73177-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="73177-132">bigint</span><span class="sxs-lookup"><span data-stu-id="73177-132">bigint</span></span>  <br/> |<span data-ttu-id="73177-133">ID chat (corrispondente alla tabella tblChat. chatId).</span><span class="sxs-lookup"><span data-stu-id="73177-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="73177-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="73177-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="73177-135">int, not null</span><span class="sxs-lookup"><span data-stu-id="73177-135">int, not null</span></span>  <br/> |<span data-ttu-id="73177-136">ID principale del poster (corrispondente alla tabella tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="73177-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="73177-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="73177-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="73177-138">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="73177-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="73177-139">URI utente.</span><span class="sxs-lookup"><span data-stu-id="73177-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="73177-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="73177-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="73177-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="73177-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="73177-142">Messaggio (la codifica dipende da cmplType).</span><span class="sxs-lookup"><span data-stu-id="73177-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="73177-143">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="73177-143">**Key**</span></span>

|<span data-ttu-id="73177-144">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="73177-144">**Column**</span></span>|<span data-ttu-id="73177-145">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="73177-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73177-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="73177-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="73177-147">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="73177-147">Primary key.</span></span>  <br/> |
   

