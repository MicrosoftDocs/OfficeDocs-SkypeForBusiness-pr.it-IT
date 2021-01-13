---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: LastChatId contiene l'ultimo ID chat generato (e utilizzato nella tabella tblChat) per ogni utente.
ms.openlocfilehash: 80664d6b296fce9b4909674f9d21b1aa13285826
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816006"
---
# <a name="tbllastchatid"></a><span data-ttu-id="dd759-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="dd759-103">tblLastChatId</span></span>
 
<span data-ttu-id="dd759-104">LastChatId contiene l'ultimo ID chat generato (e utilizzato nella tabella tblChat) per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="dd759-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="dd759-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="dd759-105">**Columns**</span></span>

|<span data-ttu-id="dd759-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="dd759-106">**Column**</span></span>|<span data-ttu-id="dd759-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="dd759-107">**Type**</span></span>|<span data-ttu-id="dd759-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dd759-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dd759-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="dd759-109">nodeID</span></span>  <br/> |<span data-ttu-id="dd759-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="dd759-110">int, not null</span></span>  <br/> |<span data-ttu-id="dd759-111">ID nodo (solo di tipo chat).</span><span class="sxs-lookup"><span data-stu-id="dd759-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="dd759-112">Dalla LastChatId</span><span class="sxs-lookup"><span data-stu-id="dd759-112">lastChatID</span></span>  <br/> |<span data-ttu-id="dd759-113">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="dd759-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="dd759-114">Ultimo ID chat utilizzato.</span><span class="sxs-lookup"><span data-stu-id="dd759-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="dd759-115">**Chiavi**</span><span class="sxs-lookup"><span data-stu-id="dd759-115">**Keys**</span></span>

|<span data-ttu-id="dd759-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="dd759-116">**Column**</span></span>|<span data-ttu-id="dd759-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dd759-117">**Description**</span></span>|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |<span data-ttu-id="dd759-118">Chiave primaria (solo nodeID è sufficiente per l'elaborazione).</span><span class="sxs-lookup"><span data-stu-id="dd759-118">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="dd759-119">nodeID</span><span class="sxs-lookup"><span data-stu-id="dd759-119">nodeID</span></span>  <br/> |<span data-ttu-id="dd759-120">Chiave esterna con ricerca nella tabella tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="dd759-120">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="dd759-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd759-121">See also</span></span>

[<span data-ttu-id="dd759-122">tblChat</span><span class="sxs-lookup"><span data-stu-id="dd759-122">tblChat</span></span>](tblchat.md)
