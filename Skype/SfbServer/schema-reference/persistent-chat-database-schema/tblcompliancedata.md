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
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contiene gli eventi di conformità che non sono stati ancora elaborati dalla scheda conformità.
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194699"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="7e980-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="7e980-103">tblComplianceData</span></span>
 
<span data-ttu-id="7e980-104">tblComplianceData contiene gli eventi di conformità che non sono stati ancora elaborati dalla scheda conformità.</span><span class="sxs-lookup"><span data-stu-id="7e980-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="7e980-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="7e980-105">**Columns**</span></span>

|<span data-ttu-id="7e980-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="7e980-106">**Column**</span></span>|<span data-ttu-id="7e980-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7e980-107">**Type**</span></span>|<span data-ttu-id="7e980-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7e980-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7e980-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="7e980-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="7e980-110">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="7e980-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="7e980-111">ID evento.</span><span class="sxs-lookup"><span data-stu-id="7e980-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="7e980-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="7e980-112">entryDate</span></span>  <br/> |<span data-ttu-id="7e980-113">smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="7e980-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="7e980-114">Ora di inserimento (può essere lontano in futuro per cmplType = 9 perché la voce è solo un segnaposto in questo caso).</span><span class="sxs-lookup"><span data-stu-id="7e980-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="7e980-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="7e980-115">cmplType</span></span>  <br/> |<span data-ttu-id="7e980-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="7e980-116">int, not null</span></span>  <br/> | <span data-ttu-id="7e980-117">Tipo di evento di conformità:</span><span class="sxs-lookup"><span data-stu-id="7e980-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="7e980-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="7e980-118">1: Chat</span></span> <br/>  <span data-ttu-id="7e980-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="7e980-119">2: Backchat</span></span> <br/>  <span data-ttu-id="7e980-120">3: download di file</span><span class="sxs-lookup"><span data-stu-id="7e980-120">3: File download</span></span> <br/>  <span data-ttu-id="7e980-121">4: caricamento di file</span><span class="sxs-lookup"><span data-stu-id="7e980-121">4: File upload</span></span> <br/>  <span data-ttu-id="7e980-122">9: trasferimento di file provvisorio</span><span class="sxs-lookup"><span data-stu-id="7e980-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="7e980-123">10: eliminazione della chat (con Sostituisci)</span><span class="sxs-lookup"><span data-stu-id="7e980-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="7e980-124">11: eliminazione chat</span><span class="sxs-lookup"><span data-stu-id="7e980-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="7e980-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="7e980-125">cmplTime</span></span>  <br/> |<span data-ttu-id="7e980-126">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="7e980-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="7e980-127">Indicatore di data e ora per l'evento.</span><span class="sxs-lookup"><span data-stu-id="7e980-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="7e980-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="7e980-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="7e980-129">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="7e980-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="7e980-130">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="7e980-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="7e980-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="7e980-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="7e980-132">bigint</span><span class="sxs-lookup"><span data-stu-id="7e980-132">bigint</span></span>  <br/> |<span data-ttu-id="7e980-133">ID chat (corrispondente alla tabella tblChat. chatId).</span><span class="sxs-lookup"><span data-stu-id="7e980-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="7e980-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="7e980-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="7e980-135">int, not null</span><span class="sxs-lookup"><span data-stu-id="7e980-135">int, not null</span></span>  <br/> |<span data-ttu-id="7e980-136">ID principale del poster (corrispondente alla tabella tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="7e980-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="7e980-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="7e980-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="7e980-138">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="7e980-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="7e980-139">URI utente.</span><span class="sxs-lookup"><span data-stu-id="7e980-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="7e980-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="7e980-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="7e980-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="7e980-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="7e980-142">Messaggio (la codifica dipende da cmplType).</span><span class="sxs-lookup"><span data-stu-id="7e980-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="7e980-143">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="7e980-143">**Key**</span></span>

|<span data-ttu-id="7e980-144">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="7e980-144">**Column**</span></span>|<span data-ttu-id="7e980-145">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7e980-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7e980-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="7e980-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="7e980-147">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="7e980-147">Primary key.</span></span>  <br/> |
   

