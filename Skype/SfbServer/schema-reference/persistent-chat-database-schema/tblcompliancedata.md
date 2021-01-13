---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contiene gli eventi di conformità ancora non elaborati dall'adattatore di conformità.
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809856"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="b7565-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="b7565-103">tblComplianceData</span></span>
 
<span data-ttu-id="b7565-104">tblComplianceData contiene gli eventi di conformità ancora non elaborati dall'adattatore di conformità.</span><span class="sxs-lookup"><span data-stu-id="b7565-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="b7565-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b7565-105">**Columns**</span></span>

|<span data-ttu-id="b7565-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b7565-106">**Column**</span></span>|<span data-ttu-id="b7565-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b7565-107">**Type**</span></span>|<span data-ttu-id="b7565-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b7565-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7565-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="b7565-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="b7565-110">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="b7565-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="b7565-111">ID evento.</span><span class="sxs-lookup"><span data-stu-id="b7565-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="b7565-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="b7565-112">entryDate</span></span>  <br/> |<span data-ttu-id="b7565-113">smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="b7565-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="b7565-114">Data/ora di inserimento (può essere molto lontana nel futuro per cmplType=9, poiché in tal caso la voce è solo un segnaposto).</span><span class="sxs-lookup"><span data-stu-id="b7565-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="b7565-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="b7565-115">cmplType</span></span>  <br/> |<span data-ttu-id="b7565-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="b7565-116">int, not null</span></span>  <br/> | <span data-ttu-id="b7565-117">Tipo di evento di conformità:</span><span class="sxs-lookup"><span data-stu-id="b7565-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="b7565-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="b7565-118">1: Chat</span></span> <br/>  <span data-ttu-id="b7565-119">2: dialogo della chat</span><span class="sxs-lookup"><span data-stu-id="b7565-119">2: Backchat</span></span> <br/>  <span data-ttu-id="b7565-120">3: download di file</span><span class="sxs-lookup"><span data-stu-id="b7565-120">3: File download</span></span> <br/>  <span data-ttu-id="b7565-121">4: caricamento di file</span><span class="sxs-lookup"><span data-stu-id="b7565-121">4: File upload</span></span> <br/>  <span data-ttu-id="b7565-122">9: trasferimento file provvisorio</span><span class="sxs-lookup"><span data-stu-id="b7565-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="b7565-123">10: eliminazione della chat (con sostituzione)</span><span class="sxs-lookup"><span data-stu-id="b7565-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="b7565-124">11: eliminazione della chat</span><span class="sxs-lookup"><span data-stu-id="b7565-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="b7565-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="b7565-125">cmplTime</span></span>  <br/> |<span data-ttu-id="b7565-126">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="b7565-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="b7565-127">Data e ora dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b7565-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="b7565-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="b7565-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="b7565-129">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="b7565-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="b7565-130">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="b7565-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="b7565-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="b7565-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="b7565-132">bigint</span><span class="sxs-lookup"><span data-stu-id="b7565-132">bigint</span></span>  <br/> |<span data-ttu-id="b7565-133">ID chat (corrispondente alla tabella tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="b7565-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="b7565-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="b7565-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="b7565-135">int, not null</span><span class="sxs-lookup"><span data-stu-id="b7565-135">int, not null</span></span>  <br/> |<span data-ttu-id="b7565-136">ID entità di chi effettua l'invio (corrispondente alla tabella tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="b7565-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="b7565-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="b7565-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="b7565-138">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="b7565-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="b7565-139">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b7565-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="b7565-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="b7565-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="b7565-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="b7565-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="b7565-142">Messaggio (la codifica dipende da cmplType).</span><span class="sxs-lookup"><span data-stu-id="b7565-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="b7565-143">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="b7565-143">**Key**</span></span>

|<span data-ttu-id="b7565-144">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b7565-144">**Column**</span></span>|<span data-ttu-id="b7565-145">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b7565-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b7565-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="b7565-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="b7565-147">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="b7565-147">Primary key.</span></span>  <br/> |
   

